# Elegoo Neptune 2 and Neptune 2S Guide #

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

u/ErbalistLLC has a thread with issues in here https://www.reddit.com/r/elegooneptune2/comments/pewptd/known_issues_solved_look_here_before_posting/
* Deformed Base: Elegoo has a video addressing this issue: https://www.youtube.com/watch?v=u7M30iAS3O4


### Guides
* Assemble your Neptune 2/2S: https://www.youtube.com/watch?v=pdOi12rG08A
* How to level the platform: https://www.youtube.com/watch?v=GXGQjd9bT5w
* How to adjust the Z axis limit switch to help leveling: https://www.youtube.com/watch?v=ZcQDblh1iZ
* How to print via USB: https://www.youtube.com/watch?v=giIJnxnbHpA
* How to replace the Nozzle: https://www.youtube.com/watch?v=b2yatiLZ8SI
* How to replace the Nozzle Assembly https://www.youtube.com/watch?v=HyVCvbpgO_E
* How to replace the Hotend & 20pin line parts https://www.youtube.com/watch?v=IdRtmuHf9eM
* How to update the Firmware: https://www.youtube.com/watch?v=ppeqmjdcTNE
* BLTouch Firmware and Instructions: http://69.195.111.207/tutorial-download/?t=FDM_Auto_leveling



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


#### Neptune 2 References
* STM32F103 28 KiB Bootloader

#### Neptune 2S References
* STM32F407 32 KiB Bootloader

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
