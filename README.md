# i3lock-blank-screen

# About i3lock-blank-screen
* Only the blank screen appears. If you press your password correctly and press enter, the lock will be unlocked.

- i3lock forks, so you can combine it with an alias to suspend to RAM
  (run "i3lock && echo mem > /sys/power/state" to get a locked screen
   after waking up your computer from suspend to RAM)

- i3lock uses PAM and therefore is compatible with LDAP etc.
  On OpenBSD i3lock uses the bsd_auth(3) framework.

Install
-------

See [the i3lock home page](https://i3wm.org/i3lock/).

Requirements
------------
- pkg-config
- libxcb
- libxcb-util
- libpam-dev
- libcairo-dev
- libxcb-xinerama
- libxcb-randr
- libev
- libx11-dev
- libx11-xcb-dev
- libxkbcommon >= 0.5.0
- libxkbcommon-x11 >= 0.5.0
- libxcb-image
- libxcb-xrm

Running i3lock
-------------
Simply invoke the 'i3lock' command. To get out of it, enter your password and
press enter.

On OpenBSD the `i3lock` binary needs to be setgid `auth` to call the
authentication helpers, e.g. `/usr/libexec/auth/login_passwd`.

Building i3lock
---------------
We recommend you use the provided package from your distribution. Do not build
i3lock unless you have a reason to do so.

First install the dependencies listed in requirements section, then run these
commands (might need to be adapted to your OS):
```
autoreconf --force --install

rm -rf build/
mkdir -p build && cd build/

../configure \
  --prefix=/usr \
  --sysconfdir=/etc \
  --disable-sanitizers

make
```

Upstream
--------
Please submit pull requests to https://github.com/i3/i3lock
