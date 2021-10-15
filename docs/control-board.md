# Control Board

I suspect machinekit might be a bit dead compared to linuxcnc
So linuxcnc might be the way to go

  * https://forum.linuxcnc.org/18-computer/43145-beaglebone-black-and-pru-driver-for-linuxcnc-or-switch-to-rp-4-mesa?start=0
  * https://www.youtube.com/watch?v=ZNuemEAM1tI
  * https://www.youtube.com/watch?v=1dy8Dgzcgq4
  * https://www.youtube.com/watch?v=15_qysmeLD0

## Hardware

A Mesa board in combination with an Rpi4 seems to be the favourite for linuxcnc
the mesa boards are a fpga, they act as a IO breakout and provide syncronised timing of the axis at the same time

With desktop PC's these replace a parallel port with a IO breakout via a PCI Card
With a Rpi4 this hooks up via the Ethernet port

  * 7I76E - http://store.mesanet.com/index.php?route=product/product&product_id=290
  * 7I92M - http://store.mesanet.com/index.php?route=product/product&product_id=302

The printnc uses a 7I76E in combo with a rpi
With this setup we'd have to configure the servoce for simple step / direction via a couple of pins input

  * Rpi4 Setup - https://wiki.printnc.info/en/controllers/linuxcnc/rpi4mesa7i76e




### CAN Bus

Typically these servos work in something called Interpolated Position mode via the CAN bus
unfortunatley this isn't supported by linuxcnc as far as I can see

  * https://sourceforge.net/p/canopennode/discussion/387151/thread/246eaa49/?limit=25
  * http://wiki.linuxcnc.org/cgi-bin/wiki.pl?LinuxCNC_Supported_Hardware
  * https://forum.linuxcnc.org/38-general-linuxcnc-questions/43652-hardware-recommendations-for-a-xyyzacuw-machine#220703


### GUI API

One of the problems with linuxcnc is it's gui is a bit crap
The api is typically done via a protocol called NML
implemented in C++ and python

  * http://linuxcnc.org/docs/2.8/html/
  * http://linuxcnc.org/docs/2.8/html/config/python-interface.html
  * http://linuxcnc.org/docs/2.8/html/code/nml-messages.html

Ideally I'd like to wrap this with Grpc then frontend it with a .Net 6 blazor app
In addition to it's default GUI


### TODO

one question is can we pass the encoder feedback back to linuxcnc via the digital outputs on the servo driver?
Marco Reps seems to do this with his own setup
This would allow for more fine tuning of the motor control

Also we may want to check linear axis feedback, although I'm not sure how to wire that to linuxcnc yet
https://www.banggood.com/2-or-3-Axis-Grating-CNC-Milling-Digital-Readout-Display-or-50-1000mm-Electronic-Linear-Scale-Lathe-Tool-p-1340326.html?imageAb=2&utm_campaign=BestToolLocker_August&utm_content=2635&p=KR28032004379201507P&akmClientCountry=GB&cur_warehouse=CN&ID=49642

