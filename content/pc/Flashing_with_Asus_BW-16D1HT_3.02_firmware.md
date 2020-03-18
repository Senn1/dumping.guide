---
title: "Flashing with Asus BW-16D1HT"
---

This page will one day be populated with instructions to flash with this
firmware - if anyone ACTUALLY wants people to test it out.

[Possibly
related?](https://www.makemkv.com/forum/viewtopic.php?f=16&t=17058)

Work has began and is under construction by olofolleola4.

The reason (as of 2020-Mar-15) why LG/Asus BD ODDs needs to be flashed
into Asus BW-16D1HT 3.02 (DE - Downgrade Enable) (most probably ODDs
using PCB: **JB8 2015.05.08**) is because that firmware supports Lead-in
and the OpCode
0xf1[1](http://forum.redump.org/post/72629/#p72629)[2](https://github.com/saramibreak/DiscImageCreator/commit/0eaf36944a1fc8531b303d1168c82fe8d6a04ec4)
(normally used by Plextors to read the EEPROM, but in the case with Asus
BW-16D1HT 3.02, it reads the cache) to read 1
sector[3](http://forum.redump.org/post/72760/#p72760) of Lead-out
through cache.

**Requirements**:

  - Microsoft Windows or GNU/Linux(-libre)
  - SATA controller in IDE mode(?) or USB to SATA Controller
    (olofolleola4 tested this with JMicron
    [JM20337](https://usb-ids.gowdy.us/read/UD/152d/2338))
  - A stable power source for both the ODD and computer.

**Some notes before you begin**:

  - After each file have been sucessfully flashed, it's a good idea to
    power cycle the ODD, either by disconnecting the SATA Power cable or
    by restarting the computer.
  - Specific instruction for GNU/Linux(-libre):

` sudo wine  `**`ASUS_ODD_FW_Changer_-_`**`FIRMWARE.exe`

**ODDs**

  - Asus BW-16D1HT with firmware 3.00 --\> 3.10:

First flash [3.10MK](https://anonymousfiles.io/SDz2wcbp/) (SHA1:
70762635c4bbd324c4f2095dc336acb3b0764919), then flash [ASUS
BW-16D1HT 3.02 (DE)](https://anonymousfiles.io/nsMLaA5u/) (SHA1:
4130578520c024218a1d99f86311525a05bccb60).

  - LG (HL-DT-ST) WH14NS40 (SVC CODE: NS50) 1.02:

First flash [3.10MK](https://anonymousfiles.io/SDz2wcbp/) (SHA1:
70762635c4bbd324c4f2095dc336acb3b0764919), then flash [ASUS
BW-16D1HT 3.02 (DE)](https://anonymousfiles.io/nsMLaA5u/) (SHA1:
4130578520c024218a1d99f86311525a05bccb60).

To-Do:

  - Provide compressed archive with all the ASUS_ODD_FW_Changer files
    in the near future\!

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")