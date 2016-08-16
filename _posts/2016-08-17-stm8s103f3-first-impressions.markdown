---
layout: post
title: "The 0.70 € STM8S103F3 Board"
date: 2016-08-17 00:45
comments: true
categories: microcontroller
---

# The 0.70 € Board
So you ordered your super cheap stm8 dev board from aliexpress oder eBay and now you want to
do at least a blinking LED, then this Mini Tutorial is exactly for you

## Hardware

### The STM8S103F3 dev board

Just in case you do not have your board yet, search for "STM8S103F3 board" on you favorite china shopping page.
You should see a plethora of listings from anything between 70 cents and 10 EUR, if some of them say ARM do not let
them confuse you as the STM8 is very far away from an ARM cpu.

And yes they all show a MicroUSB port on them, but this is for nothing more then to power this board.
For Programming you need something called an STLink

### The STLink v2

The STLink v2 is a small stm32 based Programmer for STM8 and also STM32, they are all based on the Reference design 
by ST but way cheaper. And as the Design and Firmware was made opensource china created these cheap USB Sticks so you
do not need to buy a 50 EUR STLink Original.

Again, if you don't have one search for "stlink v2" and you should see listings starting at 2 EUR.

## Software

### sdcc
First you need some software, on a Ubuntu >=15.04 you just need to install `sdcc`, the [small device
c compiler](http://sdcc.sourceforge.net/), a compiler that supports the old 8051, zilog z80, PIC16, a lot more and for this tutorial
most important the STM8

```
sudo apt-get install sdcc
```

Just to be sure that your installed version of sdcc supports the stm8 you can check the version string which should contain stm8

```
sdcc --version
 SDCC : mcs51/z80/z180/r2k/r3ka/gbz80/tlcs90/ds390/TININative/ds400/hc08/s08/stm8 3.4.0 #8981 (Jul 12 2014) (Linux)
 published under GNU General Public License (GPL)
```

### stm8flash

The next software you need is the [stm8flash](https://github.com/vdudouyt/stm8flash) software that you need to fetch from github

```
git clone https://github.com/vdudouyt/stm8flash.git
cd stm8flash
make
```

If you want to install the stm8flash software globally to you system just run `sudo make install` after `make` finished.
This will save you from typing the full path to stm8flash over and over again.

## The first steps (and what you will most probably stumble upon)

When you get your fresh STM8S103F3 Board from China, they are most probably
in a "locked mode"
This will show up when you want to program them as an error message

### Is it locked?

```
sudo stm8flash -c stlinkv2 -p "stm8s103f3" -w blinky.ihx
 Determine FLASH area
 Writing Intel hex file 182 bytes at 0x8000... Tries exceeded
```

There is a pretty simple fix for this found in the [stm8flash issues](https://github.com/vdudouyt/stm8flash/issues/38#issuecomment-213712893)
Thos who are interested in what all the 00 and ff mean, can go to the [datasheet](http://www.st.com/content/ccc/resource/technical/document/datasheet/ce/13/13/03/a9/a4/42/8f/CD00226640.pdf/files/CD00226640.pdf/jcr:content/translations/en.CD00226640.pdf) page 45 and read about the "option bytes"

```
echo "00 00 ff 00 ff 00 ff 00 ff 00 ff" | xxd -r -p > factory_defaults.bin
stm8flash -c stlinkv2 -p stm8s103f3 -s opt -w factory_defaults.bin
```


### Blink the LED

And now the minimal code needed to blink an LED on your super cheap development board.
The LED is connected to Pin B5, which means Port B, pin 5

ledblink.c

```
// Port B data output latch register, for setting pins HIGH or LOW)
#define PB_ODR *(unsigned char*)0x5005

// Port B data direction register, for setting pins as INPUT or OUTPUT 
#define PB_DDR *(unsigned char*)0x5007

// Port B control register 1, 
#define PB_CR1 *(unsigned char*)0x5008

int main() {
	int d;
	// Configure pins
	PB_DDR = 0x20; // 0x20(00100000) pin 5 set to 1 -> setting it as OUTPUT 
	PB_CR1 = 0x20; // 0x20(00100000) pin 5 set to 1 -> setting it as PUSH-PULL Mode (only when configured as output)
	// Loop
	do {
		PB_ODR ^= 0x20; // 0x20(00100000) pin 5 XOR/toggle between HIGH and LOW
		for(d = 0; d < 29000; d++) {
        }
	} while(1);
}
```

[Push–pull output](https://en.wikipedia.org/wiki/Push%E2%80%93pull_output)

Now we need to compile this file

```
sdcc -lstm8 -mstm8 --out-fmt-ihx ledblink.c
```

SDCC has no compiled our C code into a "ledblink.ihx" file that can be uploaded to our devboard.

```
sudo stm8flash -c stlinkv2 -p stm8s103f3 -w ledblink.ihx
 Determine FLASH area
 Writing Intel hex file 189 bytes at 0x8000... OK
 Bytes written: 189
```

Tada, now you have a blinking LED on your STM8 dev board.

## Links

* [small device c compiler](http://sdcc.sourceforge.net/)
* [stm8flash](https://github.com/vdudouyt/stm8flash)
* [Simple GPIO – The Way of the Register](http://blog.mark-stevens.co.uk/2012/07/simple-gpio-the-way-of-the-register/)
* [Getting started with STM8 development using free software](http://www.colecovision.eu/stm8/HCDVBD0017%20LED.shtml)
* [How to Program STMicro STM8S $1 Board in Linux](http://www.cnx-software.com/2015/04/13/how-to-program-stm8s-1-board-in-linux/)
* [Meet STMicro STM8S Based One Dollar Development Board](http://www.cnx-software.com/2015/01/18/one-dollar-development-board/)
