# Gui

One of the problems with linuxcnc is it's gui is a bit crap
The api is typically done via a protocol called NML
implemented in C++ and python

  * http://linuxcnc.org/docs/2.8/html/
  * http://linuxcnc.org/docs/2.8/html/config/python-interface.html
  * http://linuxcnc.org/docs/2.8/html/code/nml-messages.html

Ideally I'd like to wrap this with Grpc then frontend it with a .Net 6 blazor app
In addition to it's default GUI
