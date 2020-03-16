
# Table of Contents
- [*Game Boy Advance* Dumping Guide](#-game-boy-advance--dumping-guide)
  * [*Nintendo DS* Method (Normal Carts)](#-nintendo-ds--method--normal-carts-)
    + [Tools](#tools)
    + [Dumping](#dumping)
  * [*Nintendo DS* Method (Certain Video Carts)](#-nintendo-ds--method--certain-video-carts-)
  * [*GameCube* Link Cable Method](#-gamecube--link-cable-method)
    + [Tools](#tools-1)
    + [Dumping](#dumping-1)
  * [Game Boy Player Method](#game-boy-player-method)
    + [Tools](#tools-2)
    + [Dumping](#dumping-2)
  * [Gathering Dump Info](#gathering-dump-info)

# *Game Boy Advance* Dumping Guide
**todo:**

-   look into cart-to-PC hardware (e.g.  [https://www.shop01media.com/en/Nintendo-GBA/GBA-GameBoy-Flash-Carts/XG2-Slim-Loader-III-NeoFlash-SlimLoader-USB](https://www.shop01media.com/en/Nintendo-GBA/GBA-GameBoy-Flash-Carts/XG2-Slim-Loader-III-NeoFlash-SlimLoader-USB))
-   list DIY hardware methods
-   develop *DS* homebrew that dumps *GBA* ROMs over *Wi-Fi* - useful if running homebrew over *Download Play* [*endrift GBA* dumper or *GodMode9i* may add this]


## *Nintendo DS* Method (Normal Carts)

### Tools

-   A *Nintendo DS* or *Nintendo DS Lite* with a flashcart
-   [GBA Backup Tool](https://gbatemp.net/download/gba-backup-tool.3228/)

### Dumping

-   Run the .nds for *GBA Backup Tool*
-   Ensure that your *GBA* cart is inserted, then press A on the pop-up.
-   By default, *GBA Backup Tool* is in Save Backup mode. Press R twice to go to rom backup mode.
-   Press B to make a new backup, then hit A to confirm. Your rom will be dumped to your SD card.

## *Nintendo DS* Method (Certain Video Carts)

Use *duplo* ([https://github.com/endrift/duplo](https://github.com/endrift/duplo)). someone should share a build and test this out a bit more.

## *GameCube* Link Cable Method

### Tools

-   A *Game Boy Advance* or *Game Boy Advance SP*
-   A *GameCube GBA* Link Cable
-   A *Wii* or a *GameCube* with some way to load .dol files (e.g. the *Homebrew Channel* for the *Wii*).
-   The  [GBA Link Cable Dumper](https://github.com/FIX94/gba-link-cable-dumper/releases)

### Dumping

-   Load the .dol with Homebrew Launcher or via Swiss on GameCube.
-   Attach your GBA to the system in port 2  **without**  a game in, leaving your gamecube controller attached to port 1.
-   Turn on your GBA and wait for the dumper to be sent. After a moment, you should see the screen on your GBA change.
-   Insert a cartridge into your GBA. Press A on the gamecube controller to continue in the menu, then press A again to dump.
-   Remove the SD card and insert into your PC. the gba file will be placed in the dumps folder.

## Game Boy Player Method

### Tools

-   A GameCube with some way to load .dol files
-   A GameCube Memory Card to SD Adapter.
-   A Game Boy Player.
-   The Latest  [GBI](https://files.extremscorner.org/gamecube/apps/gbi/latest)  - You only need GBI.DOL, none of the others.

### Dumping

-   Load GBI.DOL with no cartridge in your game boy player. A menu should appear on screen, and some screen options will appear.
-   Press B to hide the screen options, then insert your cartridge. Navigate to "Dump ROM" and hit A.
-   Text showing progress will appear. Once done, hold reset, eject your cartridge and release. Upon the restart, you can power off.
-   Remove your SD Card. the .GBA file will be on the root of your SD, named by serial which you can find on the bottom right of your cartridge's label.

## Gathering Dump Info

-   **CRC32**: Generated from the ROM file using  [HxD](https://mh-nexus.de/en/hxd/)  or  [HashTab](http://implbits.com/products/hashtab/)  on windows, or by using crc32 in a terminal emulator for linux/mac.
-   **MD5**: As above, or by using md5 in a terminal emulator for linux/mac.
-   **SHA-1**: As above, or by using shasum -a 1 in a terminal emulator for linux/mac.
-   **SHA-256**: As above, or by using shasum -a 256 in a terminal emulator for linux/mac.
-   **Game title**: If it differs between different places (e.g. title screen, console menu banner, box, cart) then go with the one on the front of the box.
-   **Region**: The region the disc originated from like USA, Japan or Europe
-   **ROM Revision**: The revision found in the ROM data.
-   **ROM Serial**: The four-character serial found in the ROM data.
-   **Languages/Language Select**: Some games either show a language selection screen at startup or in the game options. Note that it is possible to submit a game without checking the languages, but this then needs to be stated in your submission.
    -   Tip: Using an emulator like mGBA can speed up the language checking dramatically.
-   **Cart Serial**: It is located on the label on the front of the cart the form of "**AGB-XXXX-XXX**" (where X is a letter or number), also it may have a number (Like -1 or -2) appended. For additional information on cartridge serials, see  [Understanding Serials](https://wiki.no-intro.org/index.php?title=Understanding_Serials#Nintendo_-_Game_Boy_Advance "Understanding Serials").
-   **Cart Stamp**  - imprinted letter (or number?) on the label (?) [get details]
-   **Box Barcode**: The number on the case displayed beneath the vertical lines, see  [Barcode](http://en.wikipedia.org/wiki/Barcode).
-   **Box Serial**: The serial on the case. Example: AGB P AMAE USA.
-   **Size**: The size of the ROM in bytes.
-   **PCB serial(s)**: The string of characters displayed on the front of the board inside the cart. You may need a tri-wing screwdriver to get inside the cart without damaging the screw.
-   **Chip(s) serial(s)**: The codes on the ROM chip inside the cart.
-   **Scans**: The following scans (or photos): Front and back of the following items - box, cart and PCB.