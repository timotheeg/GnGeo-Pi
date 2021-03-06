GnGeo-Pi
==============

General Usage
-------------

GnGeo-Pi is a portable NeoGeo emulator optimized for Raspberry Pi (TM)

This emulator is tested with the RetroPie distribution (based on Raspian).

Currently, there is no official release, but you can download the source and put in /home/pi/RetroPie/emulators/gngeo-0.85/.


```shell
wget -O gngeo-pi-0.85.tar.gz https://github.com/ymartel06/GnGeo-Pi/blob/master/releases/sources/gngeo-pi-0.85.tar.gz?raw=true
rm -rf /home/pi/RetroPie/emulators/gngeo-pi-0.85
tar xvfz gngeo-pi-0.85.tar.gz -C /home/pi/RetroPie/emulators/
pushd "/home/pi/RetroPie/emulators/gngeo-pi-0.85"
./configure --host=arm-linux --target=arm-linux --disable-i386asm --prefix="/home/pi/RetroPie/emulators/gngeo-pi-0.85/installdir"
make
make install
popd
mv /home/pi/RetroPie/emulators/gngeo-pi-0.85/installdir/bin/arm-linux-gngeo /home/pi/RetroPie/emulators/gngeo-pi-0.85/installdir/bin/gngeo
mv /home/pi/RetroPie/emulators/gngeo-pi-0.85/installdir/share/man/man1/arm-linux-gngeo.1 /home/pi/RetroPie/emulators/gngeo-pi-0.85/installdir/share/man/man1/gngeo.1
```

Wiki
----

The wiki is open at this url: https://github.com/ymartel06/GnGeo-Pi/wiki

Thanks
------

Many thanks to Mathieu Peponas, the original author of GnGeo.

Fork History and Motivations
----------------------------
This repo is a manual merge of 2 repos:
* https://github.com/pepone42/gngeo - Original project with commit history!
* https://github.com/ymartel06/GnGeo-Pi - Pi/Retropie Port of the above, but not from history, from a static dump

I have applied the commits from GnGeo-Pi onto gngneo after the following was done to make the commit cherry-pick correctly:
1. move all original source to folder gngeo
2. did DOS->UNIX EOL conversion on src/drz80/DrZ80.s

This repo will be a playground to see if it is possible to port gngeo to libretro.
