# VimBox

## Models

### Lid

<script src="https://embed.github.com/view/3d/ObjectsCountries/VimBox/blob/main/VimBoxLid.stl"></script>

### Box

> [!NOTE]
> The below box has two changes from my version:
> 
> * The USB cable output has been increased from 6 mm × 10 mm to 8 mm × 14 mm.
> * The Raspberry Pi Pico screw holes have been decreased from a diameter of 3.66 mm to a diameter of 3 mm.
> 
> The original version is available for archival purposes, but I advise using the new version (titled VimBoxAdjusted.stl).

<script src="https://embed.github.com/view/3d/ObjectsCountries/VimBox/blob/main/VimBoxAdjusted.stl"></script>

## Assembly

Any item, tool or step marked with an asterisk is optional, unless you intend on using your VimBox on PlayStations.

### Items

* [Eight Crown/Samducksa SDB-202 MX 24mm Screwbutton Green](https://focusattack.com/crown-samducksa-sdb-202-mx-24mm-screwbutton-green/) (for the face buttons)
* Four Cherry MX keyboard switches (can be ordered as extras with 24mm buttons)
* [Five Sanwa SDM 18mm Pushbutton - White](https://focusattack.com/sanwa-sdm-18mm-pushbutton-white/) (for the side buttons)
* [Tai-Hao Neon Green Row 2 Blank 4 Key OEM Profile TPR Rubber Keycap Set](https://mechanicalkeyboards.com/products/tai-hao-4-key-tpr-blank-rubber-keycap-set-neon-green-row-2) (for the keys)
* [Raspberry Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) (I used a Pico W, but you won't need wireless capabilities)
* USB-A to Micro-USB Cable that can transfer data (this can be tested during step 1)
* \*[USB Type A Female Breakout](https://www.sparkfun.com/sparkfun-usb-type-a-female-breakout.html)
* \*PS5 Adapter such as [this one by Mayflash](https://www.amazon.com/dp/B01N66G4HE) or [the Brook Wingman](https://www.brookaccessory.com/products/wingmanfgc/index.html)
* Four M3 6mm Heat Set Inserts
* [Four M3 12mm screws](https://www.homedepot.com/p/321071710) (these have extra length to accomodate for the lid)
* Four M2 4mm Heat Set Inserts
* [Four M2-0.4×4mm Screws](https://www.homedepot.com/p/310723420)
* [Vim sticker](https://www.redbubble.com/i/sticker/VIM-by-arthurreeder/16789391.O9UDB) for garnish

### Tools

* Soldering workstation
* Tool to insert heat set inserts
* Lots of solder
* One long wire for ground
* 17 female-to-male wires
* \*4 female-to-female wires
* 2 sets of header pins (unless you get a Pico with headers)
* \*1 set of 4 header pins
* Breadboard (to solder header pins)

### Steps

You will need experience soldering, or to ask a friend for help.

1. Flash the appropriate image from [here](https://gp2040-ce.info/downloads/) using [these instructions](https://gp2040-ce.info/installation/).
2. Attach the keycaps onto the switches, preferably all in matching orientation using the pins on the bottom as a point of reference.
3. 3D print the two models. I used green PLA filament, and the lid took ~2 hours whereas the box took ~4.5 hours.
4. Lay the lid face down behind the box with the switch holes on the right.
5. Lay the box face up with the USB output facing away from you.
6. Insert the buttons and switches into the appropriate holes before soldering, preferably all in matching orientation. The 24 mm buttons will have plastic nuts on the bottom to keep them in place.
7. Insert the heat set inserts. Put the M3 ones in the top holes of the box, and the M2 ones in the smaller holes close to the USB output. A tutorial is available [here](https://www.youtube.com/watch?v=hwq15qH-4x4).
8. If not already present, solder on header pins to the Raspberry Pi.
9. If room is available, screw the Raspberry Pi into the M2 heat set insert holes. If not, plug in the USB cable from outside to keep it in place.
10. \*Use the breadboard to solder the 4 header pins onto the USB breakout board.
11. \*Attach the female-to-female wires between the pins of the USB breakout board and the Raspberry Pi using [this](https://gp2040-ce.info/controller-build/usb-host) as a point of reference.
12. Cut, strip and solder the ground wire repeatedly, and attach it to one pin of each button. The 24 mm buttons will have an indication of which pin is negative, and either pin can be used for the switches and 18mm buttons. Make sure that the wires form a chain between the buttons, and that all 17 buttons are accounted for.
13. For each of your female-to-male wires:
  * Cut off the male end, making sure it's long enough for the connection between the Raspberry Pi and each button.
  * Strip the male end enough to expose the wire (~1 cm).
  * Solder the male end onto the appropriate button.
  * Attach the female end onto the appropriate header of the Raspberry Pi.
14. Attach a female-to-male wire to the last ground wire with the same method as above.
15. \*Plug in your Brook converter/Mayflash adapter/etc. to the USB breakout board.

I have SOCD set to left + right = neutral, and up + down = up. My buttons are laid out like this (reading order):

| Physical Button | Button   | Pin Number |
|-----------------|----------|------------|
| 24 mm 1         | L2/LT    | GP09       |
| 24 mm 2         | R2/RT    | GP08       |
| 24 mm 3         | B3/X     | GP10       |
| 24 mm 4         | B4/Y     | GP11       |
| 24 mm 5         | L1/LB    | GP13       |
| 24 mm 6         | R1/RB    | GP12       |
| 24 mm 7         | B1/A     | GP06       |
| 24 mm 8         | B2/B     | GP07       |
| Switch 1        | LEFT     | GP05       |
| Switch 2        | DOWN     | GP03       |
| Switch 3        | UP       | GP02       |
| Switch 4        | RIGHT    | GP04       |
| 18 mm 1         | S1/Back  | GP16       |
| 18 mm 2         | S2/Start | GP17       |
| 18 mm 3         | L3/LS    | GP18       |
| 18 mm 4         | R3/RS    | GP19       |
| 18 mm 5         | Guide/A1 | GP20       |

If dissatisfied with this layout, it can be changed either through the GP2040-CE settings or by physically re-arranging the pins.
