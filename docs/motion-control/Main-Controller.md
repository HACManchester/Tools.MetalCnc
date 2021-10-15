# Control Board

## Overview

So far I've been looking at different ways to control the servo control boards
For duet boards the max step rate is around 180kHz
With the mesa boards we can get into the Mhz

  * https://forum.duet3d.com/topic/328/max-speed-at-different-microsteppings/2

I suspect machinekit might be a bit dead compared to linuxcnc
So linuxcnc might be the way to go using a Pi4 in combination with a Mesa board

  * https://forum.linuxcnc.org/10-advanced-configuration/33371-mesa-7i76e-and-step-rates-and-latency

Another advantage to linuxcnc is it's backlash compensation and support for feedback with encoders

  * https://forum.linuxcnc.org/18-computer/43145-beaglebone-black-and-pru-driver-for-linuxcnc-or-switch-to-rp-4-mesa?start=0
  * https://www.youtube.com/watch?v=ZNuemEAM1tI
  * https://www.youtube.com/watch?v=1dy8Dgzcgq4
  * https://www.youtube.com/watch?v=15_qysmeLD0


## Hardware

A Mesa board in combination with an Rpi4 seems to be the favourite for linuxcnc
the mesa boards are a fpga, they act as a IO breakout and provide syncronised timing of the axis at the same time
As well as the ability to pulse / syncronise at a high rate

With desktop PC's these replace a parallel port with a IO breakout via a PCI Card
With a Rpi4 this hooks up via the Ethernet port.

  * 7I76E - http://store.mesanet.com/index.php?route=product/product&product_id=290
  * 7I92M - http://store.mesanet.com/index.php?route=product/product&product_id=302

The printnc uses a 7I76E in combo with a rpi
With this setup we'd have to configure the servoce for simple step / direction via a couple of pins input

  * Rpi4 Setup - https://wiki.printnc.info/en/controllers/linuxcnc/rpi4mesa7i76e
  * https://forum.linuxcnc.org/38-general-linuxcnc-questions/33969-7i76e-quick-setup
  * https://gnipsel.com/linuxcnc/uspace/
  * https://www.youtube.com/watch?v=LKjNOVHhHio
  * https://www.youtube.com/watch?v=LKjNOVHhHio


## Drivers

Typically with LinuxCNC the way this works is

  * LinuxCNC HAL -> HostMot2 Driver -> HostMot2 Ethernet driver -> Mesa Board
  * http://linuxcnc.org/docs/html/man/man9/hostmot2.9.html

HostMot2 is the type of firmware typically used on the Mesa FPGA Boards
