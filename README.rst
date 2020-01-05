Raspbian64
==========

An out of the box `Raspberry Pi <http://www.raspberrypi.org/>`_ Raspbian distro with a 64bit chroot with docker. 

Where to get it?
----------------

Official mirror is `here <http://unofficialpi.org/Distros/Raspbian64>`_

Nightly builds are available `here <http://unofficialpi.org/Distros/Raspbian64/nightly/>`_ (currently built on demand)

How to use it?
--------------

#. Unzip the image and install it to an SD card `like any other Raspberry Pi image <https://www.raspberrypi.org/documentation/installation/installing-images/README.md>`_
#. Configure your WiFi by editing ``raspbian64-wpa-supplicant.txt`` at the root of the flashed card when using it like a flash drive
#. Boot the Pi from the SD card
#. Hostname is ``rasbian64`` (not ``raspberrypi`` as usual)


Requirements
------------
* Raspberry Pi 3B+, 4B
* 2A power supply

Features
--------

* Chroot with Debian Buster on 64bit aarch with all the 64bit settings enabled
* Tools to configure the network via text files /boot

Developing
----------

Requirements
~~~~~~~~~~~~

#. You need to build this distro with a Raspberrypi with the 64bit kernel mode enabled, so it can run both armf and aarch64.
#. `CustomPiOS <https://github.com/guysoft/CustomPiOS>`_ using the Docker build method
#. root privileges for chroot
#. Bash

Building Raspbian64 Variants
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Rasbian64 supports building variants, which are builds with changes from the main release build. An example and other variants are available in the folder ``src/variants/example``.

To build a variant use::

    sudo bash -x ./build_dist [Variant]
    
Usage
~~~~~

#. If needed, override existing config settings by creating a new file ``src/config.local``. You can override all settings found in ``src/config``. If you need to override the path to the Raspbian image to use for building Raspbian64, override the path to be used in ``ZIP_IMG``. By default, the most recent file matching ``*-raspbian.zip`` found in ``src/image`` will be used.
#. Run ``src/build_dist`` as root.
#. The final image will be created in ``src/workspace``

Code contribution would be appreciated!
