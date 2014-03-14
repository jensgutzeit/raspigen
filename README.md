# raspigen - A Gentoo disk image creator for the Raspberry Pi

raspigen is a Ruby script for automatically generating a rather minimal
Gentoo disk image for a Raspberry Pi.

## Requirements

It assumes that you are running a Linux with the following tools installed:

* Ruby (>= 2.0)
* Various command line utilities
   * truncate
   * losetup
   * parted
   * mkfs.msdos
   * mkfs.ext4
   * mkswap
   * wget
   * gpg
   * sha512sum
   * tar
   * git
   * mkpasswd
   * sed
* Root access with sudo

## How to use

Determine the size of your SD card and run the script:

   `raspigen -s <size of your SD card in bytes> --hostname <rpi's hostname>`

The script will download various files (stage3, latest portage, firmware for
the Raspberry Pi) and install it on a disk image, named gentoo.img by default.
Depending on the speed of your internet connection it will take around 20
minutes to create it. Copy the disk image to your SD card after the script
is done:

   `dd if=gentoo.img of=/dev/<SD card device>`

The installation assumes that a DHCP server is running. Log into your new
Gentoo on the Raspberry Pi with:

   `ssh root@<rpi's hostname>`

Use the default password `gentoo`.

Make sure to secure your new Gentoo installation right after the login!

## License

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>

