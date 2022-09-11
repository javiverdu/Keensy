# Build Guide

## Things you need

- 3d printed files
- rp2040 WeAct Studio
- Soldering Iron 
- 48 4x2mm magnets 
- 84 1N14148 diodes
- 84 keycaps 
- 22 AWG flexible cable 
- scizzors
- a pin (yes, a pin)

## Getting started

First download [CircuitPython](https://circuitpython.org/board/weact_studio_pico/)

get the raspberry in boot mode

hold down the boot buttom and plug the raspberry into the computer

The computer should detect a new external storage

Drag the downloaded UF2 file to the Pico. The storage will reset and appear with the name CIRCUITPY

Now we have to install the KMK firmware


Grab the latest version of [KMK](https://github.com/KMKfw/kmk_firmware) and extract all the files from the .zip

Copy the kmk folder and the boot.py to the raspberry

download and copy the code.py to the raspberry

you're done!





It will download a .zip file. Extract all the files.

In the folder find the KMK folder and the boot.py file.

Copy those items from the folder and pasted them in the Pico

That should be all the setup on the Pico
