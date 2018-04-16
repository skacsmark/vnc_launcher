# vnc_launcher
  A wrapper around `xvncviewer` and it's kin to handle RFC-7869 style URIs

  vnc_launcher will will process a vnc:// style URI, and launch a vnc-client
  based upon it. Notably, it will handle login credentials in the URI, a
  feature lacking in many VNC clients.

  The VNC protocol itself doesn't have a username, if vnc_launcher encounters
  a username in the URI it will be ignored.

# Requirements
* [Python 2.6+ or Python 3.6+](https://www.python.org)
* [PyCrypto](https://pypi.python.org/pypi/pycrypto)
* An Xvnc compatible vncviewer program

# Installing
```sh
cp vnc_launcher /somewhere/in/your/path
chmod a+x /somewhere/in/your/path
```

If you're missing the PyCrypto library run
```sh
pip install pycrypto
```

Most modern desktop environments can be configured for automatic handling of the
VNC protocol by running the commands below.
```sh
cp vnc_launcher.desktop ~/.local/share/applications
update-desktop-database ~/.local/share/applications
xdg-mime default vnc_launcher.desktop x-scheme-handler/vnc

# Thanks
Thanks to James Cuzella, and his vncpasswd.py project which provided insight
into the password encoding mechanism used here.
```
# Bugs
Probably.

# References
* [RFC-7869](https://tools.ietf.org/html/rfc7869)
* [vncpasswd.py](https://github.com/trinitronx/vncpasswd.py/)

Copyright (c) 2018 Stephen Kacsmark
