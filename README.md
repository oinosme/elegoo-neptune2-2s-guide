# Elegoo Neptune 2 and Neptune 2S Guide #

***(Note that the config files, firmware and other things here are pulled and sort of hacked together from a bunch of places. Use at own risk)***

This guide is intended to be a single place for reference, quick tips, fixes,
and configuration for both the Neptune 2 and Neptune 2S. Thank you to everyone that has shared their knowledge!

This Guide is divided into:

* [Known Issues](#Known-Issues)
  * [Guides](#Guides)
* [Tips & Mods](#Tips-&-Mods)
* [Resources & Reference](#Resources-&-Reference)
 * [Resources](#Resources)
 * [Neptune 2 References](#Neptune-2-References)
 * [Neptune 2S References](#Neptune-2S-References)
* [Configuration Ultimaker Cura](#Configuration-Ultimaker-Cura)
* [Klipper](#Klipper)



## Known Issues

u/ErbalistLLC has a thread with issues in [here](https://www.reddit.com/r/elegooneptune2/comments/pewptd/known_issues_solved_look_here_before_posting/)
* Deformed Base: Elegoo has a video addressing this issue [here](https://www.youtube.com/watch?v=u7M30iAS3O4)


### Guides
* Calibration. To insure everything is working it is highly advisable to follow this [calibration guide](https://teachingtechyt.github.io/calibration.html).

* Assemble your Neptune 2/2S [Elegoo's Youtube](https://www.youtube.com/watch?v=pdOi12rG08A)
* How to level the platform [Elegoo's Youtube](https://www.youtube.com/watch?v=GXGQjd9bT5w)
* How to adjust the Z axis limit switch to help leveling [Elegoo's Youtube](https://www.youtube.com/watch?v=ZcQDblh1iZ)
* How to print via USB [Elegoo's Youtube](https://www.youtube.com/watch?v=giIJnxnbHpA)
* How to replace the Nozzle [Elegoo's Youtube](https://www.youtube.com/watch?v=b2yatiLZ8SI)
* How to replace the Nozzle Assembly [Elegoo's Youtube](https://www.youtube.com/watch?v=HyVCvbpgO_E)
* How to replace the Hotend & 20pin line parts [Elegoo's Youtube](https://www.youtube.com/watch?v=IdRtmuHf9eM)
* How to update the Firmware: [Elegoo's Youtube](https://www.youtube.com/watch?v=ppeqmjdcTNE)
* BLTouch Firmware and Instructions [Elegoo's Youtube](http://69.195.111.207/tutorial-download/?t=FDM_Auto_leveling)



## Tips & Mods

## Resources & Reference

### Resources
Elegoo has posted many resources, from the wiring, the PCB, the materials etc.
Make sure you check there first: https://www.elegoo.com/pages/3d-printing-user-support

It contains:

  * Motherboard and machine structure diagram open source file
  * Autoleveling Firmware & Instructions (BLTouch)
  * Slicing Software and Tutorials
  * User Guides

#### Firmware
There are two motherboards depending on your model.

* Neptune 2 & 2D use ZNP Robin Nano V1.2 and ZNP Robin Nano V1.3 (Due to shortage of chips it seems it's mostly V1.3)
* Neptune 2S uses ZNP Robin Nano V1.3
* Neptune X Neptune X V1.0

Note that the main control chips are different and so is their firmware.

Because of the confusion and lack of clear instructions, after consulting with Elegoo, they suggested if I could remove links to other firmware so they can publish it with clear guides to avoid the issues some have experienced while flashing.
If you need firmware for your printer, for the time being you can send an email to 3dp@elegoo.com which they have been very responsive to.

On this subject I encountered some difficulties (observed by lack of icons and scrambled Elegoo logo on boot) flashing the correct stock firmware due to some or a combination of the following issues:

* On mac, it seems that extracting zips provided by Elegoo caused issues for some weird reason.
* Windows also had issues but I managed to get the uncorrupted files with 7z.
* Formatting is important and apparently the way macOS was formatting didn't quite did it. Try on windows with allocation size of 32 or via command line.
* Sometimes SD Cards have weird issues after flashing, if you are reflashing reformat the card.
* When nothing happens, check if windows really copied the files. It happened to me that sometimes it seemed like it had copied the files to the SD card, but in reality it was empty. Not sure if this was due to it running as a virtual machine.

TL;DR format on windows or command line, unzip in windows, confirm you copied the files.

#### Neptune 2 References
* STM32F103 28 KiB Bootloader

#### Neptune 2S References
* STM32F407 32 KiB Bootloader
* Firmware "stock" (not official/usable yet) [Firmware/Neptune2S Folder](Firmware/Neptune2S)

## Configuration Ultimaker Cura
The Elegoo Version of Cura, is just an older version of Ultimaker Cura with some parameters and Elegoo logo. Furthermore, on the macOS version, in order to be able to install it you have to disable security protections. You don't have to do this, and the best way is to just download Ultimaker Cura and set those parameters yourself.

1. Download Ultimaker Cura [here](https://ultimaker.com/software/ultimaker-cura)
1. Select add _non-networked_ > _Custom FFF printer_
1. On the _"Printer Settings"_ tab:
  * x = 235mm
  * y = 235mm
  * z = 260mm
  * Build plate shape = Rectangle
  * Origin center = **NOT** selected
1. Enable Heated bed
1. Go to the _"Extruder 1"_ tab
  * Compatible material diameter = 1.75mm
1. Click next
1. In printer settings (it’s the box on your right over the bed grid)
  * Profiles = 0.2
  * Support = Disabled
  * Adhesion= Disabled

And that's it!

## Klipper

### BLTouch

I have place a printer.cfg file named [Firmware/Klipper/Neptune2S/Printer_Neptune2S_withBLTouch.cfg](Firmware/Klipper/Neptune2S/Printer_Neptune2S_withBLTouch.cfg) that has my current configuration for the Neptune 2S. Mesh still does not work.
