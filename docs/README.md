# Intro

Keensy is a 3D printed 75% mechanical keyboard that uses KMK firmware 



  
 ![keensy_AND_NUTS_IT_2023-Feb-11_10-58-57AM-000_CustomizedView52401355376](https://user-images.githubusercontent.com/77059171/218270925-da948f2e-8f14-4177-8bd7-bf39c40e3c5f.jpg)
![keensy_AND_NUTS_IT_2023-Feb-11_11-13-40AM-000_CustomizedView2487390429](https://user-images.githubusercontent.com/77059171/218270934-9f58ebad-08a8-40f8-88e4-2aa93de455f2.jpg)
![keensy_AND_NUTS_IT_2023-Feb-11_11-40-58AM-000_CustomizedView38916644806](https://user-images.githubusercontent.com/77059171/218270943-a1067d05-0e76-4f87-b945-1ca89e01d9b2.png)
</p>



## FAQ

**Q) Are the 3d printed pieces strong enough?**

A) Yes

**Q) Do I need to know how to program?**

A) No but it is recommended to "understand" how the main.py works, [the KMK firmware is very well documented](https://github.com/KMKfw/kmk_firmware) and can help you to get the best configuration for you.

**Q)Why KMK?**

A) I could have used QMK but KMK is easier to install

**Q) Is the PCB also 3d printed?**

A) The PCB uses a 3d printed base that makes the handwiring cleaner and hot-swappable, it also gets rid of most of the soldering process (only the gpios of the board need to be soldered).

**Q) What is handwiring?**

A) Handwiring is the process of soldering the rows, columns and diodes of the keyboard by hand to a board (in this case the raspberry pico)

**Q) So, is the pcb printed option worth it?**

A) It depends, if you hate soldering or wants to have something solid and hotswap then go for it. The downside is it makes the process more tedious you may end up changing some rows because the pin of a switch don't make contact.

**Q) Where can i buy the pieces for cheap?**

A) Aliexpress

**Q) the key next to home prints b**

A) I know :P

**Q) Why did you do this?**

A) My main purpose was to create the best budget fully customizable keyboard you can get

**Q) What is a layout?**

A) This image will help you to understand the difference between an [ISO and an ANSI layout](https://acf.geeknetic.es/imgw/imagenes/auto/2021/6/9/sue-teclados-ansi-iso.png?f=webp)



# Materials

| Quantity  | content |
| ------------- | ------------- |
| x | 3D printed files |
| x1  | rp2040 WeAct Studio  |
| x84  | 84 keycaps (ISO/ANSI) |
| x84 | Mx style switches |
| x84 | 1N14148 diodes |
| x1  | Usb-c male connector |
| x1  | Usb-c female connector |
| x4 | 33x5x1.5mm silicone feet |
| x1 | 10 meter 22 AWG flexible cable |
| x23 (minimum) |  M2X14mm screws  |

Tools needed:
- soldering iron
- hot glue
- scissors
- something pointy

**There are 4 variables of plates but only the 3d printed PCB works with the default ISO layout. This also applies for the main.py configuration but it can be edited easily**

**If are not into handwiring and have some free time you can check this pcb generator [here](https://github.com/50an6xy06r6n/hotswap_pcb_generator)**

# Preparing firmware

The model of the raspberry has to be from WeAct Studio. If not, search the firmware of your raspberry [here](https://circuitpython.org/downloads).

First download [CircuitPython](https://circuitpython.org/board/weact_studio_pico/).

After that, Get the raspberry in **boot mode**: 

> Hold down the boot buttom and plug the raspberry into the computer.
  <img width="50%" src="https://user-images.githubusercontent.com/77059171/218272883-652900b1-0b6d-4e69-815d-08e58389cdb1.png">

Now, the computer should detect a new external storage.

Drag the downloaded UF2 file to the Pico. The storage will reset and appear with the name CIRCUITPY.

Now we have to install the KMK firmware.

Grab the latest version of [KMK](https://github.com/KMKfw/kmk_firmware) and extract all the files from the zip.

Copy the kmk folder and the boot.py to the raspberry.

Download and copy the `main.py` to the raspberry.

You're done!

# PCB assembly

This is the most tedious part of the build, it will take you some time to finish it.


You will need [this diode bending cube](https://github.com/50an6xy06r6n/hotswap_pcb_generator/blob/main/stl/diode_bending_templates/mx_improved_diode_bending_template.stl):

this is the 3d printed pcb:
![pcb_front](https://user-images.githubusercontent.com/77059171/218271015-1a5cc7f7-a20f-43bd-9953-fb5b0d73933a.png)

We will start at the back of the board with the columns of the matrix.

## Columns

![pcb_back](https://user-images.githubusercontent.com/77059171/218271016-5bd20b9a-7bfe-466c-975b-f2e9d2b81f7b.png)

For better cable management mark the position where the raspberry board will be. This will help you to know 
the length of the cables.
> Be careful with the holes of the screws!
> Do NOT glue the board into the pcb (yet)

![pcb_back](https://user-images.githubusercontent.com/77059171/218273965-b49f7c9c-ab78-425b-bef8-e3f9dda4a9fe.png)

This is is the diagram of the weact studio rp2040, the GPX pins will be used for the matrix of the keyboard.

The order of the pins can be specified in the `main.py` which means that you can solder the cables wherever you want as long as you modify the file.
>Note: GND are not GPIO pins, do not use them.

<img width="40%" src="https://user-images.githubusercontent.com/77059171/218274319-28368ab4-c421-4ff6-bc2f-a8e217b59c9d.jpeg">

Put the cables in the columns and cut them with the enough length to join their respective pin.
>If the cables won't fit in the columns you can use silver wire as long as you secure the conection between the wire and the diode AND.

>If you didn't understand this don't worry, it is the next step


Here is my setup:

![COLUMNS](https://user-images.githubusercontent.com/77059171/218275540-8f00776f-204b-450d-9370-33bc6547fef5.png)


## Diodes


not yet !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
After that, solder the wire the a cable that goes to the FC  (this will prevent problems when touching the columns):



<img src="https://user-images.githubusercontent.com/77059171/197513592-ae4d662f-2725-4259-8ddc-07ca1a2fb7b5.png">
<img src="https://user-images.githubusercontent.com/77059171/197513595-618ac596-a999-4fd4-b1f6-e334db974f62.png">

Additionally, you can bending diodes:

<img src="https://user-images.githubusercontent.com/77059171/197514755-90bb6a7d-5171-4165-b815-3526b5fb4c9f.png">
<img src="https://user-images.githubusercontent.com/77059171/197514763-71bf9795-2e87-448d-b0ca-1d694bfb5139.png">
<img src="https://user-images.githubusercontent.com/77059171/197514766-f7fec248-f870-4ca9-afa1-0133285df3b7.png">
<img src="https://user-images.githubusercontent.com/77059171/197514768-1df9660b-df81-49e2-acae-0ad455548230.png">

<img width="1125" src="https://user-images.githubusercontent.com/77059171/197513597-7421e924-2184-40b1-8982-4b5453a2ace7.png">
<img width="1125" src="https://user-images.githubusercontent.com/77059171/197513599-e50b8574-73cf-4c6b-b42f-9b8525960c7e.png">
<img width="1125" src="https://user-images.githubusercontent.com/77059171/197513604-9f14fefa-2a90-467a-b6c7-1389f41f7929.png">

![pcb11](https://user-images.githubusercontent.com/77059171/197513607-f82ca05a-25a7-458b-9c98-04b720e4c8ba.jpeg)

If you didn't put the cables in the same order as me you must modify the order of the pins in the [main.py](https://github.com/javierverdu/Keensy/blob/main/main.py):


![pcb12](https://user-images.githubusercontent.com/77059171/197513608-b7ce56fa-b938-4343-9fe7-694ba7b8dd3d.jpeg)

# Credits

* Thanks to [50an6xy06r6n](https://github.com/50an6xy06r6n/hotswap_pcb_generator) and [stingray127](https://github.com/stingray127/handwirehotswap) for the inspiration of the PCB.

