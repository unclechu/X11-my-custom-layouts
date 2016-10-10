My customized keyboard layouts
==============================

It supposed to be used with
[xlib-keys-hack](https://github.com/unclechu/xlib-keys-hack/) tool.

Provides these layouts:
* `mine(us)`
* `mine(ru)`

Usage
-----

1. Copy `mine` xkb symbols file to system directory:

  ```bash
  $ sudo ./copy-to-system.sh
  ```

2. Apply these layouts (put these commands to your session autostart script):

  ```bash
  $ setxkbmap -layout 'mine(us),mine(ru)'
  $ "./xmodmaps.sh" # hack the caps lock for the xlib-keys-hack
  ```

  It would be a good idea to replace `./` before `xmodmaps.sh` to path to
  directory of this cloned repo, especially if you add this command to your
  session autostart script.

  Since these hacked layouts supposed to be used with the `xlib-keys-hack` you
  usually use these commands in your session autostart script:

  ```bash
  setxkbmap -layout 'mine(us),mine(ru)'
  "foo/xmodmaps.sh"
  (killall xlib-keys-hack ; "bar/xlib-keys-hack") \
    0</dev/null 1>/dev/null 2>/dev/null &
  ```

  Where `foo/` is path to this cloned repo and `bar/` is path to directory
  that contains `xlib-keys-hack` built binary file.

  Executing `xmodmaps.sh` here is very important, because we need mapped real
  `Caps Lock` key to let `xlib-keys-hack` tool detect this key number to
  trigger real `Caps Lock` pressing.

Author
------

[Viacheslav Lotsmanov](https://github.com/unclechu)

License
-------

Public domain. You able to use it and distribute any way you can imagine
without any limitations.
