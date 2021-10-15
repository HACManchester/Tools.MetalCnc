# TODO

## Encoder

one question is can we pass the encoder feedback back to linuxcnc via the digital outputs on the servo driver?
Marco Reps seems to do this with his own setup
This would allow for more fine tuning of the motor control

Also we may want to check linear axis feedback, although I'm not sure how to wire that to linuxcnc yet
https://www.banggood.com/2-or-3-Axis-Grating-CNC-Milling-Digital-Readout-Display-or-50-1000mm-Electronic-Linear-Scale-Lathe-Tool-p-1340326.html?imageAb=2&utm_campaign=BestToolLocker_August&utm_content=2635&p=KR28032004379201507P&akmClientCountry=GB&cur_warehouse=CN&ID=49642

  * http://linuxcnc.org/docs/html/man/man9/encoder.9.html
  * https://forum.linuxcnc.org/27-driver-boards/37129-mesa-card-and-absolute-encoders

I think linuxcnc can read the SSI protocol
