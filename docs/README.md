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

A) No but it is recommended to "understand" how the [`main.py`](https://github.com/javiverdu/Keensy/blob/main/main.py) works, [the KMK firmware is very well documented](https://github.com/KMKfw/kmk_firmware) and can help you to get the best configuration for you.

**Q)Why KMK?**

A) I could have used QMK but KMK is easier to install

**Q) Is the PCB also 3d printed?**

A) The PCB uses a 3d printed base that makes the handwiring cleaner and hot-swappable, it also gets rid of most of the soldering process (only the gpios of the board need to be soldered).

**Q) What is handwiring?**

A) Handwiring is the process of soldering the rows, columns and diodes of the keyboard by hand to a board (in this case the raspberry pico)

**Q) So, is the pcb printed option worth it?**

A) It depends, if you hate soldering or wants to have something solid and hotswap then go for it. The downside is that it makes the process more tedious you may end up changing some rows because the pin of a switch don't make contact.

The most robust solution will always be soldering.

**Q) Where can i buy the pieces for cheap?**

A) Aliexpress

**Q) the key next to home prints b**

A) I know :P

**Q) Why did you do this?**

A) My main purpose was to create the best budget fully customizable keyboard you can get and the most accesible proyect for beginners

**Q) What is a layout?**

A) This image will help you to understand the difference between an [ISO and an ANSI layout](https://acf.geeknetic.es/imgw/imagenes/auto/2021/6/9/sue-teclados-ansi-iso.png?f=webp)

## [Support me buying a coffee](https://www.buymeacoffee.com/javiverdu)
  

# Materials

| Quantity  | content |
| ------------- | ------------- |
| x | 3D printed files |
| x1  | rp2040 WeAct Studio  |
| x84  | 84 keycaps (ISO/ANSI) |
| x84 | Mx style switches |
| set | Costar stabilizers |
| x84 | 1N14148 diodes |
| x1  | Usb-c male connector |
| x1  | Usb-c female connector |
| x4 | 33x5x1.5mm silicone feet |
| x1 | 10 meter 22 AWG flexible cable |
| x23 (minimum) |  M2X14mm screws  |
| x19  | M2X4mm screws |

Tools needed:
- soldering iron
- hot glue
- scissors
- needle (or something pointy)

**There are 4 variables of plates but only the 3d printed PCB works with the default ISO layout. This also applies for the main.py configuration but it can be edited easily**

**If you are not into handwiring and have some free time you can check this pcb generator [here](https://github.com/50an6xy06r6n/hotswap_pcb_generator)**

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

Download and copy the [`main.py`](https://github.com/javiverdu/Keensy/blob/main/main.py) to the raspberry.

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
>If the cables won't fit in the columns you can use silver wire as long as you secure the conection between the wire and the diode.

>If you didn't understand this don't worry, it is the next step


Here is my setup:

![COLUMNS](https://user-images.githubusercontent.com/77059171/218275540-8f00776f-204b-450d-9370-33bc6547fef5.png)


## Diodes


Here comes the worst part of the build, you have been warmed.

The best way to show how the diodes are conected to the columns is with these pictures

> pointy thing and [diode bending cube](https://github.com/50an6xy06r6n/hotswap_pcb_generator/blob/main/stl/diode_bending_templates/mx_improved_diode_bending_template.stl) are needed here

the diode pins will be here

![Screenshot_1](https://user-images.githubusercontent.com/77059171/218276803-220dad54-e544-4a70-a26b-66b8f1bf7fbb.png)
![caca](https://user-images.githubusercontent.com/77059171/218276926-45109aa2-2294-4161-be2c-61f1a33dd053.png)

The connection between the column and the pin is formed by going through the cable.


Here is where the pointy thing comes in handy.

Check where the hole of the column is and prick the cable.
> The tinier the hole the less will fail the conexion

<img src="https://user-images.githubusercontent.com/77059171/197513592-ae4d662f-2725-4259-8ddc-07ca1a2fb7b5.png">
<img src="https://user-images.githubusercontent.com/77059171/197513595-618ac596-a999-4fd4-b1f6-e334db974f62.png">

Do the same with all the columns.

## Bending Diodes

You will need to do this at least 84 times 

<img src="https://user-images.githubusercontent.com/77059171/197514755-90bb6a7d-5171-4165-b815-3526b5fb4c9f.png">
<img src="https://user-images.githubusercontent.com/77059171/197514763-71bf9795-2e87-448d-b0ca-1d694bfb5139.png">
<img src="https://user-images.githubusercontent.com/77059171/197514766-f7fec248-f870-4ca9-afa1-0133285df3b7.png">
<img src="https://user-images.githubusercontent.com/77059171/197514768-1df9660b-df81-49e2-acae-0ad455548230.png">

## Mounting the Diodes

>Note: check the Diode orientation
<img width="1125" src="https://user-images.githubusercontent.com/77059171/197513597-7421e924-2184-40b1-8982-4b5453a2ace7.png">



<img width="1125" src="https://user-images.githubusercontent.com/77059171/197513599-e50b8574-73cf-4c6b-b42f-9b8525960c7e.png">
<img width="1125" src="https://user-images.githubusercontent.com/77059171/197513604-9f14fefa-2a90-467a-b6c7-1389f41f7929.png">

with all the diodes mounted to the columns you can now hot glue the raspberry to the pcb (make sure to put a layer of hot glue on the pcb 

before)
> You can also add some hot glue to the cables 

## Rows

The rows just need to solder the cables to their respective pin and good cable management.

> Note: The ISO enter is connected in the third row


## Usb-C Cable

You will need a usb c male to female cable. You can buy usb-c connectors and solder the cables or buy one.


Your printed PCB should look like this: 

![pcb11](https://user-images.githubusercontent.com/77059171/197513607-f82ca05a-25a7-458b-9c98-04b720e4c8ba.jpeg)


![pcb12](https://user-images.githubusercontent.com/77059171/197513608-b7ce56fa-b938-4343-9fe7-694ba7b8dd3d.jpeg)
>This was the first prototype of the pcb

now you can connect the pcb to the PC and check if all the keys work as it should with a keyboard tester and something to bridge the connections of the matrix

# Putting all together

> Check if all the keys are working before mounting the case

## Mounting the PCB

glue the usb adapter to the hole case (usb-c hole) place the pcb to the case, be careful not to pinch the wires.

now you can use the M2x4mm screws to secure the pcb to the case.
![case_pcb](https://user-images.githubusercontent.com/77059171/218313886-1fa5fe3e-e407-454a-ae53-a6a50f59697b.png)

## Mounting the stabilizers

![keensy_AND_NUTS_IT_2023-Feb-11_12-43-35PM-000_CustomizedView1329393190](https://user-images.githubusercontent.com/77059171/218312721-a8142374-f820-4a1f-9fc4-6806e6fa1086.png)

For the stabilizers you will need at least one for the spacebar in order to make it work properly

![costar_stab](https://user-images.githubusercontent.com/77059171/218314234-cf49fc51-e5a4-4beb-b6d2-441d05167409.png)

The stabilizers need to be installed in a specific orientation

![costar_installed](https://user-images.githubusercontent.com/77059171/218314420-5eac41b4-2aec-48bc-a5f2-4c3c1dc00ead.png)

You can put the rest of the costar pieces later 

## Mounting the case

take the plate and the case and put it upside-down. make sure the case and the plate is alined and start putting in the screws
> There should be the less gap possible between the plate and the case

![keensy_AND_NUTS_IT_2023-Feb-12_02-00-19PM-000_CustomizedView29306077820](https://user-images.githubusercontent.com/77059171/218316560-12c908d5-f0d4-4e41-b75f-df1e4895eefa.png)

You can now put the silicone feet.

## Mounting the switches

The switches are installed in a specific orientation.

It is recommended to check if the switch works before mounting the next one.
This part is where the switch tends to fail as the upper pin needs to go through the row cable


![keensy_AND_NUTS_IT_2023-Feb-12_02-06-20PM-000_CustomizedView13376214790](https://user-images.githubusercontent.com/77059171/218316576-89118b33-4bbc-4010-9749-c55eb989af59.png)

You can now mount the costar stabilizers and the keycaps.


## You're Done!

Congratulations! You can now enjoy your new finished keyboard and tweak it however you like.


# Credits

* Thanks to [50an6xy06r6n](https://github.com/50an6xy06r6n/hotswap_pcb_generator) and [stingray127](https://github.com/stingray127/handwirehotswap) for the inspiration of the PCB.

