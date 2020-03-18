---
title: "PlayStation Portable UMD Discs"
---

This guide is for dumping UMD discs with movie partitions. Known discs
include Stealth movie with WipeOut Pure demo, and "Demo Disc for PSP
Vol. 1". For dumping UMD games without a movie partition (MOST), please
use this guide instead: [PlayStation Portable Dumping
Guide](PlayStation_Portable_Dumping_Guide "wikilink").

For further discussion, see these Redump forum threads:
[1](http://forum.redump.org/post/45825/#p45825)
[2](http://forum.redump.org/topic/18432/umdimagecreator/)

Movie partitions are region-locked and must be dumped with PSPs from the
region of the disc.

## Required Hardware

  - Sony PSP with the latest [CFW
    installed](https://revive.today/psp/cfw/).
  - Memory Stick with at least 2 GB of free space.

## Tools & Setup

  - [UMDKiller
    V1.2](https://archive.org/download/UMDKillerV1.2REPACK/UMDKiller_V1.2-REPACK.zip):
    Copy the "UMDKiller" folder to: ms0:/PSP/GAME/
  - [UMDKillerPRX
    V1.5](https://archive.org/download/UMDKillerV1.2REPACK/UMDKillerPRX_V1.5.zip):
    Copy the "UMDKiller.prx" and "VSH.TXT" files to: ms0:/seplugins/

## Dumping

Note: UMD_DATA.BIN of each ISO has the partition number, 0001 & 0002.

  - In your PSP, navigate in the menu to Games \> Memory Stick and
    choose UMDKiller V1.2 to dump the first partition. It will be saved
    to ms0:/ISO/UCJB-98306.iso.
  - Connect your PSP to a PC and rename the dumped ISO as
    "UCJB-98306_0001.iso" and then move it onto the PC.
  - With your UMD in the PSP, use UMDKillerPRX V1.5 to dump the second
    partition by pressing the "♪" button. It will be saved to
    ms0:/ISO/UCJB-98306.iso.
  - Connect your PSP to a PC and rename the dumped ISO as
    "UCJB-98306_0002.iso" and then move it onto the PC.
  - Open Notepad and type the text below, make sure to modify the
    filenames to match your ISOs: **copy /b UCJB-98306_0001.iso +
    UCJB-98306_0002.iso UCJB-98306_merged.iso**
  - Save the file as Merge.bat and move it to the same location as the
    two ISO dumps.
  - Double-click the Merge.bat to merge the ISOs into one file,
    "UCJB-98306_merged.iso" is created.
  - Use clrmamepro's Dir2Dat function and uncheck everything except Add
    MD5+SHA1, create the .dat file to save the three ISO hashes.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")