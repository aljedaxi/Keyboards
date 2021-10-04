#Rhymestone Build Guide

## Parts list

! [img] (_image / 20181212-PC120065.jpg)

## Kit accessories

| Name | Number | Remarks |
| ---- | ---- | --- |
| PCB | 2 sheets | |
| Top plate | 2 sheets | The one with a lot of square holes |
| Bottom plate | 2 sheets | Those with only screw holes |
| OLED / Pro Micro protective plate | 2 sheets | |
| * 30 OLED / Pro Micro protective plate for key challenge * | * 2 sheets * | * Option * |
| M2 spacer 8mm | 12 pieces | |
| Plastic spacer 3mm | 8 pieces | Used in combination with M2 spacer |
| M2 screws 5mm | 20 pieces | |
| M2 black countersunk screws 4mm | 4 pcs | Screws to attach to the protective plate |
| Rubber feet | 8 | 4 large and small |
| Diodes | 40 pieces | |
| TRRS jack | 2 | |
| Tact switch | 2 | |

## What you need other than the kit

| Name | Number | Remarks |
| ---- | ---- | --- |
| 3.5mm stereo cable (3 poles) | 1 | For connection between keyboards |
| MicroUSB cable | 1 | For keyboard and PC connection |
| Key switches | 40 | MX compatible |
| Keycaps | 40 pcs | MX compatible |
| Pro Micro | 2 pieces | |
| Spring pin header 12P | 4 pieces | It is convenient to replace and check, so it is recommended to say that it is essential |
MX sockets | 40 pcs | MX switch sockets |
| * SK6812mini * | * 40 pieces * | * For backlight (optional) * |
| * OLED module * | * 1-2 pieces * | * For OLED (optional) * |
| * Pin socket 4P * | * 1-2 pieces * | * For OLED (optional) * |
| * Pin header 4P * | * 1-2 pieces * | * For OLED (optional) * |

### Supplement

#### pro micro

Most of the time, when you buy ProMicro, you don't have to buy it because it comes with a pin header, but if you use a slightly expensive spring pin header for consul,

--Recovery when the front and back of the keyboard board are soldered by mistake
--Moke micro measures
--Replacement and restoration measures for Pro Micro's brick-and-mortar (when writing abnormal data)
--Pro Micro can be reused

I highly recommend it because it has only merits. If you are an expert who wants to install OLED directly, please complete the section "PCB land short for OLED installation" first.

#### OLED and pin socket for OLED

OLED can be attached to both hands. Since the status for checking various operations is displayed on the left hand side, it works well even if you purchase only one side.

If you bought only OLED from AliExpress or Yusha Kobo, there is no pin socket, so please purchase it separately from Akizuki Denshi or Hirosugi Net. There are various types, but sockets

--2.54mm pitch
--Low profile (low profile) board mounting height 3.5 mm
--Pin socket
--1x4 (4P)

I need something.

#### SK6812mini

The SK6812mini for backlight is vulnerable to solder heat, and unless it is a soldering iron with a temperature control function, many failures will take time and parts will be damaged. A soldering iron with a temperature control function made in China is cheap, but depending on the item, the temperature may not be accurate and parts may be damaged, so as much as possible, a temperature control soldering iron produced by a Japanese manufacturer such as HAKKO Please use. Also, the solder tip (tip) is not the one on the pencil that comes as standard, but it is recommended to purchase a diagonally cut type separately as it will make a lot of progress.

## Necessary tools

| Name | Remarks |
| ---- | ---- |
| Soldering iron | When installing a backlight LED, it is essential to have something that can adjust the temperature <br /> (If the temperature cannot be adjusted, the LED damage rate is quite high) |
| Flux | If you install a backlight LED, it will be a mess, so it is essential |
| Thread solder | 0.8mm is recommended |
| Solder blotting line | For failure |
| Nippers | For cutting diode lead wires, etc. |
| Tweezers | ProMicro Used for resetting and soldering chip LEDs |
Flux remover | Although it is not essential, it can remove stickiness after soldering, and the yellow discoloration caused by solder can be wiped off for a beautiful finish.
| Masking tape | Used for marking and temporary fixing. Even with a 100-square pattern is OK |

Mtei's [Tool memo required to make Helix keyboard kit] (https://gist.github.com/mtei/6957107a676ddfa85bde0ae41f8fa849)
And hdbx's [Tools to prepare for starting your own keyboard] (https://hdbx.hateblo.jp/entry/2018/06/01/215401) is also helpful.

! [img] (_image / 20181212-PC120070.jpg)
! [img] (_image / 20181213-PC130102.jpg)

## Preparation of pro micro

Reinforce the promicro connector and solder the conthrough pin.
For promicro, attach the conthrough so that the surface on which it is mounted faces the keyboard board.
 --Promicro connector reinforcement: [Write QMK_Firmware while preventing ProMicro mog] (https://qiita.com/hdbx/items/2f3e4ddfcadda2a5578e)
 --Soldering Consul Pins: [Helix Beta Build Guide] (https://github.com/MakotoKurauchi/helix/blob/master/Doc/buildguide_jp.md)

! [img] (_image / 20190131-P1310235.jpg)

### Prepare QMK

This keyboard is programmed to work with keyboard software called QMK. The default keymap registered in advance is the one actually used by the author, and it is devised so that it can be used almost without any inconvenience.

1. Install QMK Toolbox linked below
2. Select rhymestone from the list under "Keyboard from qmk.fm" in QMK Toolbox
   1. (If you can't find it, download the default hex file from the link below and select it in "Local File")
3. Connect the promicro (board in the case of direct mounting) to the PC and press the reset button to write.
   1. (Some patterns cannot be written without double-clicking the reset button)

For the writing method, refer to the article [(Beginner) Write firmware to your own keyboard] (https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox) by Salicylic Acid.

[Default hex file] (https://qmk.fm/compiled/marksard_rhymestone_default.hex)
[QMK Toolbox] (https://github.com/qmk/qmk_toolbox/releases)

#### Make the keymap your own

If you are new to programming, using QMK Configurator will be faster.

[QMK Configurator] (https://docs.qmk.fm/#/ja/newbs_building_firmware_configurator)

#### Create a build environment

If you can build from the source by yourself, you can freely customize the keys one by one to the detailed operation.

[Prepare QMK build environment] (https://docs.qmk.fm/#/ja/newbs_getting_started)

The default keymap for rhymestone is
`` `qmk compile -kb marksard / rhymestone -km default```
It is possible with. When writing
`` `qmk flash -kb marksard / rhymestone -km default```
Then, as soon as the compilation is completed, it will wait for writing, so in that state, click the reset button on the board or double-click to start writing.

## About the back and front of the board

The key switch is on, the side facing up during normal use is the front side, and the reverse side is the back side.

## Determine the left and right of the board

! [img] (_image / 20181212-PC120073.jpg)

The attached board is a reversible board that can be used on either the left or right side. You don't have to hesitate if you write left and right on the mast so that you don't forget the left and right during the creation, and decide that the pasted gawa is the front (the one with the key switch).

## Solder the diode

### Bend the diode legs

Before attaching to the board, all the legs of the diode will be bent. Try to find a jig to bend the holes in the board. I think it's okay to use disposable chopsticks while they are still connected.

! [img] (_image / 20181212-PC120071.jpg)

I was able to use the USB-C to USB-A conversion connector just right, so I bent a few diodes at once.

! [img] (_image / 20181212-PC120072.jpg)

### Soldering diodes

The diode mounting direction is the same for each board, so if you check one and mount it, all the rest will be mounted in the same direction. Install the diode with the black band side facing the square side of the diode mounting hole on the board.

! [img] (_image / diode.png)

! [img] (_image / 20181212-PC120074_2.jpg)

Insert the diode from the back side of the left hand side board. After inserting, twist the legs of the diode and temporarily fasten them. You can easily and quickly insert it in a row and solder it all together. After soldering, cut your legs from the root.

! [img] (_image / 20181212-PC120074.jpg)
! [img] (_image / 20181212-PC120075.jpg)

Insert one row at a time, solder and cut repeatedly. Do the same for the right-hand side board.

! [img] (_image / 20181212-PC120077.jpg)

## * (Optional) Solder the LED *

We will attach a full-color chip LED to the back of the key switch.

### LED mechanism and connection order

This chip LED has 4 terminals (lands), which are VCC, GND, DIN, and DOUT, respectively. Did you do VCC and GND in junior high school? I think it's okay to recognize each as a battery +. DIN and DOUT are lines that control the LED lighting pattern, with DIN as the input and DOUT as the output. Multiple LEDs are controlled by connecting these DIN and DOUT in a row.

Rhymestone is connected in a spiral shape from the outside to the inside, starting from the end where the reset button is installed. It is more reliable and faster to install several pieces → check lighting → install several pieces, so install them in this order.

! [img] (_image / ledmap.png)

### Orient

Install so that the front side of the LED faces the front side of the board.
The mounting direction is fixed for each board, so if you attach the first one without making a mistake, you can imitate it.

Left hand side
! [img] (_image / 20181212-PC120088_2.jpg)
! [img] (_image / led_leftback.png)

Right hand side
! [img] (_image / 20181213-PC130103_2.jpg)
! [img] (_image / led_rightback.png)

### Pinch the chip LED with tweezers with your left hand and fit it into the hole in the PCB for alignment.

! [img] (_image / 20181212-PC120087.jpg)

### Apply flux with your right hand while pinching

The photo is not pinched for shooting, but please apply the flux while pinching it and proceed to the next work.

! [img] (_image / 20181212-PC120091.jpg)

### Add a little solder to the tip of the soldering iron set around 220 degrees

The iron tip should be around 220 degrees. 270 degrees is high.
Put a little solder on the soldering iron.
Rubbing the lands with a little solder to connect the lands.
First, attach one of the four lands so that the land of the board and the land of the chip LED are as horizontal as possible. After attaching, release the tweezers and attach the remaining three in the same way.

! [img] (_image / 20181212-PC120092.jpg)

### LED lighting confirmation

I think that the LED operation check firmware is written on the pro micro in advance, so attach the pro micro by aligning the pins with the white frame on the front of the board (the one with the mast attached).
I think that the LED will shine if installed. Of the four pins that shine, VCC, GND, and VIN can be soldered to each other. If it is not lit, the main reason is that the LED VCC, GND, and VIN solders you just attached are not soldered, or the VOUT solder you just attached is not attached.

### Solder to the remaining lands in the same way

After that, let's repeat this and attach 20 pieces with one hand and 40 pieces in total with both hands. I'm pretty happy because I can see the progress if I check it from time to time, and it's easy to understand where and what happened when it didn't light up, so please try it steadily.

After installing all of them, the soldered tokoro becomes dirty with flux and becomes sticky, so if you are concerned, wipe it off with a flux remover.

! [img] (_image / 20181213-PC130102.jpg)
! [img] (_image / 20181213-PC130104.jpg)
! [img] (_image / 20181213-PC130101.jpg)

## * (Optional) OLED installation *

### PCB land shorts for OLED mounting

I think there are 4 sets of 8 small ■ on the front side of the board, on the lower side where Pro Micro is attached. Please short each pair with solder. The trick is to apply flux to the solder surface of the board, apply a small amount of solder to the soldering iron, apply it to the board, and then quickly remove it from the board after applying it for about 4 to 7 seconds. If you think it won't stick, remove the solder on the soldering iron and try again.

! [img] (_image / 20181213-PC130110.jpg)

### Solder pin sockets and pin headers for OLEDs

For easy straight mounting, temporarily press it with masking tape so that it sticks straight, then turn it over and solder it.

## Solder TRRS connector and tact switch

For easy straight mounting, temporarily press it with masking tape so that it sticks straight, then turn it over and solder it.
The tact switch is snapped in and turned inside out for soldering.

! [img] (_image / 20181213-PC130111.jpg)

## Fit the switch on the top plate

You can solder the socket first, but it is faster and cleaner to fit all the switches on the top plate first, insert the socket into the terminal, and then solder.
Insert the switch of your choice into the top plate.

! [img] (_image / 20181213-PC130105.jpg)

## Solder the MX socket

First, match the top plate and PCB. Align the central protrusion on the back of the switch with the hole in the PCB and attach it.

! [img] (_image / 20181213-PC130107.jpg)

Align the MX socket with the white silk mark on the PCB and attach it. Make sure that the pins of the switch are properly stuck in the MX socket, and attach all of them with crackling.

! [img] (_image / 20181213-PC130109.jpg)

The rest is soldering. When the MX socket is installed, the switch can be replaced, but since the socket and board are held by solder, soldering defects such as the switch not working after replacement may occur. However, it doesn't make sense to pile it thick, so pour the solder firmly between the PCB and the socket.
Solder the tip of the soldering iron with a generous amount of solder, and pour it while applying heat as if you were trying to pry open the gap in the socket with the feeling of attaching it to the PCB that can be seen in the gap between the metal fittings of the socket.

## Installing spacers

Peel off one side of the protective paper on the bottom plate, and attach the rubber legs to the peeled side. Large and small ones are included so that they can be tilted as standard, so attach the two smaller ones to the front and the two larger ones to the back.

! [img] (_image / 20181213-PC130114.jpg)

Peel off the remaining protective paper and screw it to the bottom plate using 4 8mm spacers and 4 5mm screws.
After screwing, insert the 3mm resin spacer into the 8mm spacer. This resin spacer works to prevent the PCB from falling when the switch is replaced.

! [img] (_image / 20181213-PC130116.jpg)

## Installation of protective panel

Attach the blindfold around the Pro Micro and the plate to protect the OLED. Attach two 8mm spacers to the PCB (yellow circles in the photo) with 5mm screws.
Peel off both protective papers on the plate and attach them to the spacer attached to the PCB with black 4mm screws.
There is a little play, so if it interferes with the keycap when it is attached, shift it a little.

! [img] (_image / 20181213-PC130112.jpg)

## Installation of keycap

Please attach your favorite keycap.

## Writing keyboard firmware

If you were writing led_test for LED backlight test, please go back and write the default keymap.

## Test

First, connect to the PC one by one and test. If you attach one by one, it will always be recognized by your left hand, so check if the keys are recognized by the keyboard tester app. If you have an OLED installed, the fourth OLED display is the switch status. It's okay if something has changed.

Remove ProMicro and USB.
Connect the left and right with a TRRS cable, connect the Pro Micro on the left hand side and USB, and let the PC recognize it.
Check if communication is possible on the left and right.

## Complete!

Check it and if there seems to be no problem, it is complete! Please finish it as your own!

! [img] (_image / 20181214-PC140118.jpg)

## How to replace the key switch

Since it is difficult to remove by hand, replace it using a key switch extraction tool sold by Amazon.

## How to use OLED / Pro Micro protective plate for 30 key challenge

Remove the key switch for the top 1 step, remove the normal protective plate, and attach the protective plate for the 30 key challenge.
The explanation about the keymap is [here] (https://github.com/marksard/qmk_firmware/blob/my_customize/keyboards/rhymestone/keymaps/like_jis_30keys/readme_jp.md)
! [img] (_image / 30key.png)
At first, I don't know where my thumb is, but it's interesting once I get used to it! Please try it.

## trouble shooting

Please refer to the [Troubleshooting] (../../troubleshooting.md) page.

