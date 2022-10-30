# Keensy

![WhatsApp Image 2022-10-21 at 19 35 23](https://user-images.githubusercontent.com/77059171/197512268-a7b74ede-3ab1-4034-8dd3-eba26b38534c.jpeg)

Keensy is a 3d printed custom mechanical keyboard with a 75% format with KMK firmware. The goal of this project is to create a cheap keyboard with good quality
### Note: the keyboard has ISO layout, ANSI layout coming soon. 

The main features of the keyboard are:
- Usb-C connector
- 3d printed pcb plate and case
- hotswap PCB
- effortless soldering (only the FC!)
- KMK firmware


# Materials 

- 3d printed files (make sure the plates are printed in a good bed level)
- rp2040 WeAct Studio
- 84 keycaps 
- Costar stabilizers
- short usb-c male to female (tutorial soon)
- 33x5x1.5mm silicone feet
- 84 1N14148 diodes
- 22 AWG flexible cable 
- M2X14mm screws
- Soldering Iron 
- Hot glue 
- scizzors
- a pin (or something pointy)


# Preparing the Raspberry firmware

### NOTE: The model of the raspberry has to be from WeAct Studio. If not, search the firmware of your raspberry [here](https://circuitpython.org/downloads)

First download [CircuitPython](https://circuitpython.org/board/weact_studio_pico/)

Get the raspberry in boot mode: Hold down the boot buttom and plug the raspberry into the computer

<img width="438" alt="Screen Shot 2022-10-24 at 13 27 35" src="https://user-images.githubusercontent.com/77059171/197515886-c6149de8-bc5b-4a58-924d-d362ccd863eb.png">


The computer should detect a new external storage

Drag the downloaded UF2 file to the Pico. The storage will reset and appear with the name CIRCUITPY

Now we have to install the KMK firmware


Grab the latest version of [KMK](https://github.com/KMKfw/kmk_firmware) and extract all the files from the .zip

Copy the kmk folder and the boot.py to the raspberry

Download and copy the code.py to the raspberry

You're done!


# PCB Assembly

### This is the most tedious part of the build, it will take you some time to finish it
![pcb1](https://user-images.githubusercontent.com/77059171/197512673-89415271-1898-42db-8045-a4a546871fb2.jpeg)

### Pro tip: place the raspberry in a position and cut the cables measuring its length to the pin
![pcb2](https://user-images.githubusercontent.com/77059171/197513583-98787abe-5e95-45ab-9ab7-ecd54d1df790.jpeg)
![pcb3](https://user-images.githubusercontent.com/77059171/197513585-7050d4f7-cc5f-48e4-8468-59da6b93305a.jpeg)
![pcb4](https://user-images.githubusercontent.com/77059171/197513589-f252d623-6e82-480e-9f8b-c4e5365b481e.jpeg)

### Do the same with the rows.
![pcb5](https://user-images.githubusercontent.com/77059171/197513590-bc3b014f-c4d3-4b2d-8021-793761283644.jpeg)
<img width="1125" alt="pcb6" src="https://user-images.githubusercontent.com/77059171/197513592-ae4d662f-2725-4259-8ddc-07ca1a2fb7b5.png">
<img width="1125" alt="Screen Shot 2022-10-24 at 13 13 09" src="https://user-images.githubusercontent.com/77059171/197513595-618ac596-a999-4fd4-b1f6-e334db974f62.png">

## Bonus step: bending diodes

<img width="1022" alt="Screen Shot 2022-10-24 at 13 20 59" src="https://user-images.githubusercontent.com/77059171/197514755-90bb6a7d-5171-4165-b815-3526b5fb4c9f.png">
<img width="1022" alt="Screen Shot 2022-10-24 at 13 21 10" src="https://user-images.githubusercontent.com/77059171/197514763-71bf9795-2e87-448d-b0ca-1d694bfb5139.png">
<img width="1022" alt="Screen Shot 2022-10-24 at 13 21 18" src="https://user-images.githubusercontent.com/77059171/197514766-f7fec248-f870-4ca9-afa1-0133285df3b7.png">
<img width="1022" alt="Screen Shot 2022-10-24 at 13 21 31" src="https://user-images.githubusercontent.com/77059171/197514768-1df9660b-df81-49e2-acae-0ad455548230.png">



<img width="1125" alt="Screen Shot 2022-10-24 at 13 13 33" src="https://user-images.githubusercontent.com/77059171/197513597-7421e924-2184-40b1-8982-4b5453a2ace7.png">
<img width="1125" alt="Screen Shot 2022-10-24 at 13 13 47" src="https://user-images.githubusercontent.com/77059171/197513599-e50b8574-73cf-4c6b-b42f-9b8525960c7e.png">
<img width="1125" alt="Screen Shot 2022-10-24 at 13 14 00" src="https://user-images.githubusercontent.com/77059171/197513604-9f14fefa-2a90-467a-b6c7-1389f41f7929.png">

![pcb11](https://user-images.githubusercontent.com/77059171/197513607-f82ca05a-25a7-458b-9c98-04b720e4c8ba.jpeg)

### Note: if you didn't put the cables in the same order as me you must modify the order of the pins in the [code.py](https://github.com/kebab-mixto/Keensy/blob/main/code.py)
![pcb12](https://user-images.githubusercontent.com/77059171/197513608-b7ce56fa-b938-4343-9fe7-694ba7b8dd3d.jpeg)

## Thanks

* Credits [50an6xy06r6n](https://github.com/50an6xy06r6n/hotswap_pcb_generator) and [stingray127](https://github.com/stingray127/handwirehotswap) for the inspiration of the PCB

