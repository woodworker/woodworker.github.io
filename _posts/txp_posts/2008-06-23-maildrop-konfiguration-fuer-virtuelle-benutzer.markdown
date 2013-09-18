---
layout: post
title: "Maildrop Konfiguration für Virtuelle Benutzer"
date: 2008-06-23 09:39:45
comments: true
categories: Linux
---

Meine *Maildrop Konfiguration* für die Verwendung mit *Virtuellen Benutzern* und Eigene Filter für jeden der Virtuellen Benutzer.

Wie die Filter der einzelnen Benutzer erstellt werden überlasse ich ganz euch. Möglich wäre z.B: ein Webinterface das die Filterdateien schreibt. Oder bei nur wenigen Benutzern ein Admin der sie von Hand aktuell hält.

Ich habe hier *Spamassassin* als xfilter in Maildrop eingebaut und Prüfe dort dann auch gleich auf den Spamstatus udn verschiebe gegebenenfalls in den Spam Ordner

{% highlight bash %}
###########################
# Datei: ~vmail/.mailfilter
#
# Einbindung in Postfix
# maildrop  unix  -       n       n       -       -       pipe
#  flags=DRhu user=vmail argv=/usr/bin/maildrop -d vmail ${extension} ${recipient} ${user} ${nexthop} ${sender}
#
###########################

#logfile "/var/log/maildrop.log"
LOGNAME=tolower("$LOGNAME")
EXTENSION="$1"
RECIPIENT=tolower("$2")
USER="$3"
HOST="$4"
SENDER="$5"

DEFAULT="/var/mail/kunden/$HOST/$USER"
DOMAINFOLDER="/var/mail/kunden/$HOST"

# test if domain folder exists
`test -e /var/mail/kunden/$HOST`
if( $RETURNCODE != 0 )
{
    # Create Domain Folder if does not exists
    #   `mkdir -p /var/mail/kunden/$HOST`
    #   `chown vmail:vmail -R /var/mail/kunden/$HOST`
    #   `chmod 0700 /var/mail/kunden/$HOST`

    # If Domain Folder doest not exists send mail to postmaster
    xfilter "makemime -c message/rfc822 -e quoted-printable -a 'Mime-Version: 1.0' -a $SUBJECT -"
    to "jon.doe@example.org"
}

# Used in User and Domain Filter (and for sa-learn)
SPAMDIR="Spam"
SPAMDIRFULL="$DEFAULT/.Spam"
TRASHDIR="Trash"
TRASHDIRFULL="$DEFAULT/.Trash"


# test if mailbox exists if no create
`test -e $DEFAULT`
if ( $RETURNCODE != 0 )
{
    `maildirmake $DEFAULT`
    `chown vmail:vmail -R $DEFAULT`
    `chmod 0700 $DEFAULT`
}

# if mail smaller then 26144 Bytes (10kByte) check for spam
if ( $SIZE < 26144 )
{
    exception {
        # for spamc use spamd must be run
        xfilter "/usr/bin/spamc -f "
    }
}

if ( /^X-Spam-Flag: YES$/ )
{
    log "found SPAM"
    exception {

        `test -e $SPAMDIRFULL`
        if ( $RETURNCODE != 0 )
        {
            `maildirmake -f $SPAMDIR $DEFAULT`
            `chown vmail:vmail -R $SPAMDIRFULL`
            `chmod 0700 $SPAMDIRFULL`
            `echo INBOX.$SPAMDIR >> $DEFAULT/courierimapsubscribed`
        }
        to "$SPAMDIRFULL/"
    }
}
else
{

    # include domain rules
    `test -f $DOMAINFOLDER/mailrules`
    if ( $RETURNCODE == 0 )
    {
        exception {
            include $DOMAINFOLDER/mailrules
        }
    }

    # include userrules
    `test -f $DEFAULT/mailrules`
    if ( $RETURNCODE == 0 )
    {
        exception {
            include $DEFAULT/mailrules
        }
    }

    exception {
        to "$DEFAULT/"
    }
}
{% endhighlight %}


So weit so gut
