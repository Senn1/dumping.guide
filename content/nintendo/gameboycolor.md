
# Table of Contents
- [Transfer Pack Method](#transfer-pack-method)
  * [Tools](#tools)
  * [Dumping](#dumping)
- [Link Cable-Raspberry Pi Method](#link-cable-raspberry-pi-method)
- [Link Cable-Adapter-PC Method](#link-cable-adapter-pc-method)
- [Audio Cable Method](#audio-cable-method)
- [Gathering Dump Info](#gathering-dump-info)

## Transfer Pack Method

### Tools

-   *Nintendo 64*
-   *Nintendo 64 Transfer Pack*
-   Flashcart
-   [todo] homebrew (e.g.  [http://lacklustre.net/n64/agbd](http://lacklustre.net/n64/agbd), maybe others)

### Dumping

[todo]

## Link Cable-Raspberry Pi Method

[todo:  [https://github.com/Palmr/cart-dumper](https://github.com/Palmr/cart-dumper)]

## Link Cable-Adapter-PC Method

[todo:  [https://github.com/endrift/gblinkdx](https://github.com/endrift/gblinkdx)]

## Audio Cable Method

[todo:  [https://github.com/FIX94/gameboy-audio-dumper](https://github.com/FIX94/gameboy-audio-dumper)]

## Gathering Dump Info

Don't worry if you can't get all of the "physical metadata" (photos, serials and such) as the dump may still be accepted.

-   **CRC32**: Generated from the ROM file using  [HxD](https://mh-nexus.de/en/hxd/)  or  [HashTab](http://implbits.com/products/hashtab/)  on windows, or by using crc32 in a terminal emulator for linux/mac.
-   **MD5**: As above, or by using md5 in a terminal emulator for linux/mac.
-   **SHA-1**: As above, or by using shasum -a 1 in a terminal emulator for linux/mac.
-   **SHA-256**: As above, or by using shasum -a 256 in a terminal emulator for linux/mac.
-   **Game title**: If it differs between different places (e.g. title screen, console menu banner, box, cart) then go with the one on the front of the box.
-   **ROM Region**: The region found in the ROM data.
-   **ROM Revision**: The revision found in the ROM data.
-   **ROM Serial**: The four-character serial found in the ROM data, but seemingly only in newer GBC games.
-   **Languages/Language Select**: Some games either show a language selection screen at startup or in the game options. Note that it is possible to submit a game without checking the languages, but this then needs to be stated in your submission.
    -   Tip: Using an emulator like bgb can speed up the language checking dramatically.
-   **Cart Serial**: It is located on the label on the front of the cart the form of "**DMG-XX-XXX**" (where X is a letter or number), also it may have a number (Like -1 or -2) appended. For additional information on cartridge serials, see  [Understanding Serials](https://wiki.no-intro.org/index.php?title=Understanding_Serials#Nintendo_-_Game_Boy_.28Color.29 "Understanding Serials").
-   **Box Barcode**: The number on the case displayed beneath the vertical lines, see  [Barcode](http://en.wikipedia.org/wiki/Barcode).
-   **Box Serial**: The serial on the case. Example: [todo].
-   **Size**: The size of the ROM in bytes.
-   **PCB serial(s)**: The string of characters displayed on the front of the board inside the cart. You may need a tri-wing screwdriver to get inside the cart without damaging the screw.
-   **Chip(s) serial(s)**: The codes on the ROM chip inside the cart.
-   **Scans**: The following scans (or photos): Front and back of the following items - box, cart and PCB.