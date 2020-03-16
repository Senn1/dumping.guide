
# Table of Contents
- [*Nintendo DS(i)* Dumping Guide](#-nintendo-ds-i---dumping-guide)
  * [*Nintendo 3DS* *GodMode9* Method (Recommended)](#-nintendo-3ds---godmode9--method--recommended-)
    + [Tools](#tools)
    + [Dumping](#dumping)
  * [*Nintendo DS* *Wooddumper Slot-2* Method](#-nintendo-ds---wooddumper-slot-2--method)
    + [Tools](#tools-1)
    + [Dumping](#dumping-1)
  * [*Nintendo DS Wooddumper* Wi-Fi Method](#-nintendo-ds-wooddumper--wi-fi-method)
    + [Tools](#tools-2)
    + [Dumping](#dumping-2)
  * [*Nintendo DSi Wooddumper* Method](#-nintendo-dsi-wooddumper--method)
    + [Tools](#tools-3)
    + [Dumping](#dumping-3)
  * [Nintendo 3DS Wooddumper Method](#nintendo-3ds-wooddumper-method)
    + [Tools](#tools-4)
    + [Dumping](#dumping-4)
  * [Gathering Dump Info](#gathering-dump-info)

# *Nintendo DS(i)* Dumping Guide
**todo:**

 - Develop a DS ROM dumper homebrew that works via Download Play -OR- DS firmware flasher that works over Download Play that flashes a firmware with built in (and up-to-date) ROM dumper tool


## *Nintendo 3DS* *GodMode9* Method (Recommended)

### Tools

-   A Nintendo (New) {2/3}DS with  [custom firmware](https://3ds.hacks.guide/)
-   [*GodMode9*](https://github.com/d0k3/GodMode9)  (use  [the latest build](https://d0k3.secretalgorithm.com/GodMode9/GodMode9-v1.7.1-30-g75a23a15-20181105013008.zip)  as of 2018-12-03 so you can dump the Cart ID)

### Dumping

-   Run *GodMode9*
-   Note down the Cart ID (eight digit hex number) displayed beside "GAMECART".
-   Navigate into "GAMECART"
-   Copy the .nds file without "trim" in the name to the SD card

## *Nintendo DS* *Wooddumper Slot-2* Method

### Tools

-   A *Nintendo DS* or *Nintendo DS* Lite with a slot-1 flashcart
-   A slot-2 flashcart compatible with your slot-1 flashcart.
-   [Wooddumper](https://gbatemp.net/download/wooddumper.33406/)

### Dumping

-   Run *Wooddumper*
-   Follow the on-screen instructions

## *Nintendo DS Wooddumper* Wi-Fi Method

### Tools

-   A *Nintendo DS* or *Nintendo DS Lite* with a way to boot homebrew, for example
    -   A flashcart (or similar unlicensed cart) that works with the console and can boot NDS homebrew
    -   A *Wii* (or *Wii U*) that can boot *Wii* homebrew or another *3/DS/i* that can boot *DS* homebrew, to send homebrew over *DS Download Play* using *Haxxstation*
-   A way to create an unsecured or WEP-secured Wi-Fi network (e.g. using a wireless router, or PC/tablet/smartphone hotspot software)
-   A computer (PC/tablet/smartphone) connected to said network
-   An FTP client on said computer (many operating systems, browsers and file managers have basic FTP support)
-   The  [*Wooddumper*](https://gbatemp.net/download/wooddumper.33406/)  homebrew

### Dumping

-   Setup your *DS* to connect to the Wi-Fi network using a *DS* game with Wi-Fi support (the *DSOrganise* homebrew may also work)
-   Run *Wooddumper*
-   Follow the on-screen instructions
-   Open the on-screen ip address in your FTP client
-   Copy the .nds and .txt file to your computer. The .txt file contains the Cart ID.

## *Nintendo DSi Wooddumper* Method

This does not work with *DSi* carts, these will need to be dumped using *GodMode9* on a *{2/3}DS*.

### Tools

-   A *Nintendo DSi* with  [custom firmware](https://dsi.cfw.guide/)
-   A copy of the  [DSi version of *Wooddumper*](https://gbatemp.net/attachments/wooddumper4hiya-7z.124629/)

### Dumping

-   Run WoodDumper.
-   Follow the on-screen instructions.
-   You may need to restart your DSi after each game due to the cartridge reader turning off once a game is ejected.

## Nintendo 3DS Wooddumper Method

This probably won't work with DSi carts, and will definitely not work with 3DS carts.

### Tools

-   A Nintendo (New) {2/3}DS with  [custom firmware](https://3ds.hacks.guide/)
-   [Wooddumper 3ds](https://gbatemp.net/threads/wooddumper-3ds-a-way-to-dump-original-ds-games-to-3ds-sd-card.436998/)

### Dumping

-   Open WoodDumper 3DS
-   Follow the on-screen instructions

## Gathering Dump Info

**Only needed for new dumps**

-   **Encrypted CRC32**: Generated from the ROM file using GameHeader.
-   **Encrypted MD5**: Ditto: Generated from the ROM file using GameHeader.
-   **Encrypted SHA-1**: Ditto: Generated from the ROM file using GameHeader.
-   **Game title**: Most obvious, is located everywhere. Please include subtitle if any.
-   **ROM Region**: The region the disc originated from like USA, Japan or Europe
-   **ROM Revision**: The revision found in the ROM data.
-   **ROM Serial**: The four-character serial found in the ROM data.
-   **Languages/Language Select**: Some games either show a language selection screen at startup or in the game options. Many games will boot with different languages depending on the active language selected in the BIOS. Booting the game with each language selected in the bios is necessary to identify the supported languages for these games. Note that it is possible to submit a game without checking the languages, but this then needs to be stated in your submission.
    -   Tip: Using an emulator like Desmume can speed up the language checking dramatically since you can switch the BIOS language in the emulator settings much faster than on a real DS.
    -   You can hold down the tab key to speed up emulation.

**Needed for new dumps and redumps**

-   **CRC32**: Generated from the ROM file using  [HxD](https://mh-nexus.de/en/hxd/)  or  [HashTab](http://implbits.com/products/hashtab/)  on windows, or by using crc32 in a terminal emulator for linux/mac.
-   **MD5**: As above, or by using md5 in a terminal emulator for linux/mac.
-   **SHA-1**: As above, or by using shasum -a 1 in a terminal emulator for linux/mac.
-   **SHA-256**: As above, or by using shasum -a 256 in a terminal emulator for linux/mac.
-   **Size**: The size of the ROM in bytes.
-   **Cart Serial**: It is located on the label on the front of the cart the form of "**XXX-XXXX-XXX**" (where X is a letter or number), also it may have a number (Like -1 or -2) appended.
-   **Additional Cart Serial**: The serial printed on the back of the cart. Example: A2DPN0J08.
-   **Box Barcode**: The number on the case displayed beneath the vertical lines, see  [Barcode](http://en.wikipedia.org/wiki/Barcode).
-   **Box Serials**: The serial on the case. Example: NTR P A2DP, NTR-A2DP-UKV
-   **PCB serial(s)**: The string of characters displayed on the part of the board inside the cart that is visible from outside the cart.
-   **Chip(s) serial(s) (optional)**: The codes on the ROM chip inside the cart. You would need to break open the cart to see these.
-   **Scans**: The following scans (or photos) would be good to have: Front and back of the following items - box, cart and PCB. For Nintendo DS a photo of the  _top_  of the cart would also be useful.
-   **Cart ID**: This is an eight digit hex number that your dumping tool should display and/or log. This may be shortened to four digits by the tool and a prefix of "NTR" may be added. Make sure to add the extra zeroes to the front of the number and remove the NTR prefix.