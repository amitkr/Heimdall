# Heimdall

Heimdall is a cross-platform open-source tool suite used to flash firmware (aka ROMs) onto Samsung mobile devices.

## Supported Platforms

Officially, AMD64/x86-64 (64-bit) or x86 (32-bit) computers running:

 * Linux
 * macOS
 * Windows (XP, Vista, 7 etc.)

However, several third-parties have reported success running Heimdall on ARM chipsets
(in particular Raspberry Pi), as well as additional operating systems such as FreeBSD.

## How does Heimdall work?

Heimdall connects to a mobile device over USB and interacts with low-level software
running on the device, known as Loke. Loke and Heimdall communicate via the custom
Samsung-developed protocol typically referred to as the 'Odin 3 protocol'.

USB communication in Heimdall is handled by the popular open-source USB library, [libusb](http://libusb.info).

## Free & Open Source

Heimdall is both free and open source. It is licensed under the MIT license (see LICENSE).

Heimdall is maintained and predominantly developed by [Glass Echidna](http://glassechidna.com.au/),
a _tiny_ independent software development company. If you appreciate our work and would like
to support future development please consider making a [donation](http://glassechidna.com.au/donate/).

## Documentation

For more details about how to compile and install Heimdall please refer to the
appropriate platform specific README:

#### Linux

 - Linux/README ([online](https://raw.githubusercontent.com/Benjamin-Dobell/Heimdall/master/Linux/README))
 ```sh
( [ -d build ] || mkdir build ) && cd build && cmake -DCMAKE_BUILD_TYPE=Release .. && make && cd -

sudo ./build/bin/heimdall flash --verbose --usb-log-level debug --no-reboot --resume --PIT t0.pit --BOOTLOADER+RW sboot.bin --TZSW tz.img --BOOT boot.img --RECOVERY recovery.img --RADIO modem.bin --CACHE cache.img --SYSTEM system.img --HIDDEN hidden.img 

```

#### OS X

 - OSX/README.txt ([online](https://raw.githubusercontent.com/Benjamin-Dobell/Heimdall/master/OSX/README.txt))

#### Windows

 - Win32/README.txt ([online](https://raw.githubusercontent.com/Benjamin-Dobell/Heimdall/master/Win32/README.txt))
