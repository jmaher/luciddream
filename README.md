Luciddream is a test harness for running tests between a Firefox browser and another device, such as a Firefox OS emulator.

Mozilla is passionate about making developer tools easier to use on all our systems.  This project helps put automation around our developer tools so we can make working with a Firefox OS application or issue much more streamlined.

Milestones
==========
* Get this running in CI (probably travis or buildbot) - goal by end of March 2015
* Find a more descriptive name and move it to mozilla-central or other central repository

To get involved:
* ping :ted or :ochameau on irc

Installation and Configuration
==============================

Currently running Luciddream is only supported on Linux, as the Firefox OS emulator is only well-supported there.

Install this module and its Python prerequisites in a virtualenv:
```
  virtualenv ./ve
  . ./ve/bin/activate
  python setup.py develop
```

[Download a Firefox build](http://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-central/) (if you don't already have one).


Download one of:
* [A Firefox OS emulator build](http://pvtbuilds.pvt.build.mozilla.org/pub/mozilla.org/b2g/tinderbox-builds/mozilla-central-emulator/) (if you don't already have one, this link requires Mozilla VPN access).
* [A B2G desktop build](http://ftp.mozilla.org/pub/mozilla.org/b2g/nightly/latest-mozilla-central/)


Unzip both your Firefox and your Firefox OS emulator/B2G desktop somewhere.

If you're on a 64-bit Ubuntu, you may need to do some fiddling to ensure you have the 32-bit OpenGL libraries available. See the "Solution : have both 32bit and 64bit OpenGL libs installed, with the right symlinks" section [in this blog post](http://rishav006.wordpress.com/2014/05/19/how-to-build-b2g-emulator-in-linux-environment/).


Running Tests
=============

To run with a Firefox OS emulator:
```
runluciddream --b2gpath /path/to/b2g-distro/ --browser-path /path/to/firefox/firefox example-tests/luciddream.ini
```

To run with B2G desktop:
```
runluciddream --b2g-desktop-path /path/to/b2g/b2g --browser-path /path/to/firefox/firefox example-tests/luciddream.ini
```
