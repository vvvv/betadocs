---
uid: "contribution/enttec-dmx-usb-pro-mkii-module"
uid-meta: "contribution/enttec-dmx-usb-pro-mkii-module-meta"
comments: 
 items: 
  - uid: "216362"
  - uid: "277758"
  - uid: "279160"
uid-files: "contribution/enttec-dmx-usb-pro-mkii-module-files"
title: "Enttec DMX USB Pro MkII module"
image: "enttec usb pro mkII.jpg"
contribution: "true"
---

A module to make full use of Enttec's DMX USB Pro MkII. Backward compatible to the DMX USB Pro.

This module was created after forum discussion [how-to-access-second-universe-on-usb-dmx-pro-mk-2](https://discourse.vvvv.org/t/how-to-access-second-universe-on-usb-dmx-pro-mk-2) and in consultation with Enttec's support staff.
It's based on [west" "west](http://vvvv.org/users/west%22+%22west)'s implementation for the Enttec DMX USB Pro.

The module initially activates DMX USB Pro MkII's API, then requests DMX-sending for both ports (both universes) and from that point on enables sending DMX data.

The module's Reset pin allows hot-plugging. No restart of vvvv after i.e. accidental unplugging of the usb device is needed anymore. Simply hit Reset.

