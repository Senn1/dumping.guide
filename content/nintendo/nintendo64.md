
# Table of Contents
- [*GameShark Pro* / *Action Replay Pro*](#-gameshark-pro-----action-replay-pro-)
- [*Retrode* with *N64* plugin](#-retrode--with--n64--plugin)
- [*Sanni*'s Cart Reader](#-sanni--s-cart-reader)
- [*64drive + UltraSave*](#-64drive---ultrasave-)
- [Note on Development Cartridges](#note-on-development-cartridges)
- [Gathering Dump Info](#gathering-dump-info)

## *GameShark Pro* / *Action Replay Pro*

Follow the *NES World*  [guide](http://www.nesworld.com/article.php?system=n64&data=n64-howtodumproms). It has been reported that parallel port adapters don't work for this, so you'll need to find an old desktop computer. You may also want to read this article by  [*Nintendo Player*](http://www.nintendoplayer.com/feature/n64/).

## *Retrode* with *N64* plugin
[todo]
## *Sanni*'s Cart Reader
[todo]

## *64drive + UltraSave*

Assemble the *UltraSave* unit and insert your *64drive* and game cartridge into either slot. Download the dumping software from the  [*64drive* website](http://64drive.retroactive.be/support.php)  and dump the game.

## Note on Development Cartridges

Because the *Retrode* and *sanni*'s reader lack the PIF chip, development carts  **cannot**  be dumped with them. The only option is to use a *GameShark* or *UltraSave*.

## Gathering Dump Info

**Needed for new dumps and redumps**

-   **CRC32**: Generated from the ROM file using  [HxD](https://mh-nexus.de/en/hxd/)  or  [HashTab](http://implbits.com/products/hashtab/)  on windows, or by using crc32 in a terminal emulator for linux/mac.
-   **MD5**: As above, or by using md5 in a terminal emulator for linux/mac.
-   **SHA-1**: As above, or by using shasum -a 1 in a terminal emulator for linux/mac.
-   **SHA-256**: As above, or by using shasum -a 256 in a terminal emulator for linux/mac.
-   **Cart Serial**: Located on the label on the front of the cart in the form of "**NUS-XXXX-XXX**" (where X is a letter or number), also it may have a number (Like -1 or -2) appended.
-   **Cart Stamp**  - Two numbers imprinted on the back label, possibly followed by an A or B. May need to view under a light source.
-   **PCB serial(s)**: The string of characters displayed on the front of the board inside the cart. You will need a 4.5 mm security bit to get inside the cart without damaging it.
-   **Chip(s) serial(s)**: The serial on the ROM chip inside the cart in the form of "**NUS-XXXX-#**"
-   **Photos**: The following photos (or scans) would be good to have: Front and back of the following items - box, cart and PCB.

**If you own the box**

-   **Box Barcode**: The numbers on the box displayed beneath the vertical lines, see  [Barcode](http://en.wikipedia.org/wiki/Barcode).
-   **Box Serial**: The serial on the inside flap of the box. Example:  [NUS-NSME-USA](https://i.imgur.com/GExdnIR.jpg)

**Only needed for new dumps**

-   **Game title**: Most obvious, is located everywhere. Please include subtitle if any.
-   **ROM Serial**: The four-character serial found in the ROM data.
-   **ROM Revision**: The revision found in the ROM data.
-   **Languages/Language Select**: Some games either show a language selection screen at startup or in the game options. Note that it is possible to submit a game without checking the languages, but this then needs to be stated in your submission.