---
layout: post
title: "Never use Doctrine in the Controller"
date: 2013-03-11 17:47
comments: true
categories: PHP
---

You may have read [this post of anne at easybib](http://drafts.easybib.com/post/44139111915/taiming-repository-classes-in-doctrine-with-the)
and the [answer of benjamin of doctrine](http://www.whitewashing.de/2013/03/04/doctrine_repositories.html) about how to build
your self a proper api to "build querys".

At first i want to say - read them if you did not read them now - i like what they written about the abstraction from
the querybuilder.

But one small point i want to say - if you are in your Symfony2 or Silex or what ever project. If you use/see Doctrine in
your controller you are dooing it wrong.
In Symfony2 and Silex there are Services. __Write Services for your stuff.__ Push the Doctrine to this service and use the
services. This has one main advantage: you (can and should) decouple your app from doctrine.

And by decouple i mean hide everything what says Doctrine. Doctrine Entities are basicly plain objects and most of the
time no problem to decoupling. What is screaming Doctrine is the Repository class, the QueryBuilder and the 
Entity/Object Manager. You __never__ want to see Doctrine in your Controller, because there is just plumbing action, right?
Services should deliver you arrays of objects or even your own Repo class that may or may not take a Doctrine Repository as
argument.
This has the advantage that you can implement data specific methods to this repository and get rid of all the api clutter
that is coming from Doctrine.

Now you ask why i should decouple me from something that already decouples me from the Database.

Some reasons for this:

* you switch from ORM (aka SQL) to ODM (aka NoSQL)
* you will have a search over your data that is not using your database/doctrine but is logical coupled to your data
* you want to add caching layers
* you want to grow
* you want to write good code
* you want to write UnitTests
