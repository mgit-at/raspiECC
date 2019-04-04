raspiECC
========

A small raspi compatible PCB for the [ATECC608A](https://www.microchip.com/wwwproducts/en/ATECC608A) Security Chip.

![raspiECCv1](https://raw.githubusercontent.com/mgit-at/raspiECC/master/raspiECCv1.png)

Preperations
------------

First you have to enable the I²C interface on the RaspberryPI. On Raspbian you can do this by adding or uncommenting the line `dtparam=i2c_arm=on` inside the file `/boot/config.txt`. You then have to enable to `i2c-dev` module either using `raspi-config` or by adding the line `i2c-dev` to `/etc/modules`. After doing this you have to reboot.
If you want to access the I²C inteface using a non-root user you also need to add the user to the group `i2c` by running the command `adduser <username> i2c`.

Testing
-------

On Raspbian you can use python to test whether the chip works:

```
# apt install build-essential python python-pip cmake libudev-dev libusb-1.0-0-dev libffi-dev libssl-dev git
# git clone https://github.com/MicrochipTech/cryptoauthtools.git
# cd cryptoauthtools/python/examples
# pip pip install -r requirements.txt
# python info.py -i i2c
```


License
-------

raspiECC is licensed under CERN OHL v.1.2 or later.
See LICENSE for details.

> Copyright CERN 2013.
>
> This documentation describes Open Hardware and is licensed under the
> CERN OHL v. 1.2.
>
> You may redistribute and modify this documentation under the terms of the
> CERN OHL v.1.2. (http://ohwr.org/cernohl). This documentation is distributed
> WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF
> MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A
> PARTICULAR PURPOSE. Please see the CERN OHL v.1.2 for applicable
> conditions
