# flipperzero-espwroom32

An ESP-WROOM-32 Guide as an WiFi Module - an alternative to the official WiFi Devboard by Flipper Devices.

<img src="https://github.com/snsational/flipperzero-espwroom32/blob/main/Assets/Pictures/FZ_ESP32_01.jpeg" title="ESP32" alt="ESP32" width="662" height="496"/>&nbsp;


## Where to buy:
<a href="https://www.amazon.com/Teyleten-Robot-ESP-WROOM-32-Development-Microcontroller/dp/B08246MCL5/?th=1" target="_blank">Amazon</a>&nbsp;
<a href="https://mauser.pt/catalog/product_info.php?products_id=096-7620" target="_blank">MAUSER</a>

## Introduction:
The purpose of this project is to catalogue what I had to make in order to get <a href="https://github.com/justcallmekoko" target="_blank">justcallmekoko</a>'s Marauder Companion by <a href="https://github.com/0xchocolate" target="_blank">0xchocolate</a>: <a href="https://github.com/justcallmekoko/flipperzero-wifi-marauder" target="_blank">WiFi Marauder Companion App</a> running on my Flipper Zero using an ESP-WROOM-32. It is also to streamline the process, so anyone that has this board or wants to use this board as an alternative, like I did, can have all the information needed in one guide.

## How to get WiFi Marauder:
If you don't already have the WiFi Marauder App, the easiest way to get the app on your flipper is to install the <a href="https://github.com/DarkFlippers/unleashed-firmware" target="_blank">Unleashed Firmware</a> on the FlipperZero. You can follow the guide in their GitHub page <a href="https://github.com/DarkFlippers/unleashed-firmware/blob/dev/documentation/HowToInstall.md" target="_blank">here</a>. It is as easy as to download a release version, open the <a href="https://flipperzero.one/update" target="_blank">qFlipper App</a> and choosing the file you just downloaded. Be sure to use the 'e' version from their <a href="https://github.com/DarkFlippers/unleashed-firmware/releases/latest" target="_blank">releases</a>, as it is the version that has Marauder pre-installed. 

## Hardware that you will need:
You can pick one of the following combination of items, depending on how pretty you want your finished module to end up:
#### I just want to wire the connections:
- Female to male jumper cables (4x needed);
- Micro-USB cable to whatever USB port your PC has;
#### I want a more sturdy finished product:
- Female to anything jumper cables (4x needed) (You will strip the other end of the wire, so it does not matter what other end you get);
- Micro-USB cable to whatever USB port your PC has;
- A set of 10 pin bar (You can buy a bigger bar and cut the excess pins).
- Hot glue and hot glue gun (I used black glue sticks to go with the board);
- Soldering iron and solder (and minimal experience with it - you won't be soldering directly to the board, but at least see a soldering tutorial to be safe);

## Flashing the board:
I used the <a href="https://github.com/SkeletonMan03/FZEasyMarauderFlash" target="_blank">FZEasyMarauderFlash</a> tool to flash this board with Marauder. It is very straight-forward, you can follow the instructions on how to do it on their GitHub page. Just like many other developers, I already had python installed on my machine, but I know many of Flipper Zero users are not developers, and in order to run this tool you have to have <a href="https://www.python.org/downloads/" target="_blank">Python</a> installed on your machine. In order to connect your ESP to your PC to flash it, you will need the Micro-USB cable.

## Wiring with just the Jumper Connectors:
After flashing Marauder to your ESP board, if you don't want to solder anything, you can just have the wires plugged directly with jumper cables to the GPIO female connectors of the FlipperZero and because the board already has male jumper connectors soldered, you just have to plug it in with the correct connections. For that, you will need the 4x Female to Male jumper cables.

This is the layout for the connection:

| ESP-WROOM-32     | Flipper Zero     |
| ---------------- | ---------------- |
| (Pin28) TX0      | (Pin14) RX       |
| (Pin27) RX0      | (Pin13) TX       |
| (Pin17) GND      | (Pin18) GND      |
| (Pin16) 3V3      | (Pin9)  3V3      |

<img src="https://github.com/snsational/flipperzero-espwroom32/blob/main/Assets/Pictures/Pinout.jpg" title="Pinout" alt="Pinout" width="500" height="450"/>&nbsp;

Note that the TX connection in the ESP32 is connected to the RX connection in the FlipperZero and the same happens with the RX in the ESP32 and TX in the FlipperZero. This is intentional, as the TX pins transmit data and on the other device, there needs to be an RX pin to receive it.

When the device receives power, the red LED should light up, and you can test a successful connection opening the Marauder app on the Flipper Zero, by going to 'Apps'>'GPIO'>'[ESP32]WiFi Marauder' and trying to scan some 'AP's.

## A more sturdier module as a final product:
As I don't have a 3D printer and prefer to show the board on the GPIO Modules, I opted for the following solution:

I used a Raspberry Pi Pico bar set that I already had lying around and cut it at 10 pins (you can use any pin bar that has at least 10 pins and cut the excess). I prefer to cut all 10 pins instead of using only what I need for the connection, as it gives a more sturdy structure to the module when attached to the Flipper Zero.

<img src="https://github.com/snsational/flipperzero-espwroom32/blob/main/Assets/Pictures/Pin_bar.png" title="Pinbar" alt="Pinbar" width="150" height="120"/>&nbsp;

I used the same connection as <a href="https://github.com/snsational/flipperzero-espwroom32#wiring-with-just-the-jumper-connectors">above</a> to wire everything, except I had to strip the ends of the wires that were supposed to connect to the flipper, and solder it to the pin bar, respecting the same order. I cut the wires (depending on its position on the bar) with between 2 to 3cm to avoid having excess wire loops and to make it more compact.

I then hot glued the soldered pin bar to the board to give it structure, and clipped the pins on the other side of the board that were not being used and here's the final product:

<img src="https://github.com/snsational/flipperzero-espwroom32/blob/main/Assets/Pictures/FZ_ESP32_02.jpeg" title="ESP32" alt="ESP32" width="662" height="496"/>&nbsp;
<img src="https://github.com/snsational/flipperzero-espwroom32/blob/main/Assets/Pictures/FZ_ESP32_03.jpeg" title="ESP32" alt="ESP32" width="662" height="496"/>&nbsp;

