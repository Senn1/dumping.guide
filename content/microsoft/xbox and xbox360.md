This is a dumping guide for the **original Xbox** and **Xbox 360**
systems.

**Note about Preproduction DVD-Rs:** Windows may not recognize the
filesystem, dump with [DICUI](Disc_Dumping_Guide_\(DICUI\) "wikilink")
with settings for IBM PC DVD-Rom.

Forum discussion on original Xbox and Xbox 360 dumping
[here](http://forum.redump.org/topic/6073/xbox-1-360-dumping-instructions/).

## Two Hardware Setups to Dumping

There are two methods of dumping Xbox games (choose one of them). The
only benefit to the more complex/expensive 0800 method, is that it's
better at retrieving security sector info on some Xbox 360 discs (XDG3).

  - **Method \#1**: Kreon disc drives:
      - SATA models:
          - SH-D163A aka TS-H353A
          - SH-D163B aka TS-H353B (won't work externally with an
            adapter, must mount in a pc tower)
      - IDE models:
          - SH-162C aka TS-H352C aka SD-M2012C(?)
          - SH-D162D/TS-H352D

<!-- end list -->

  - **Method \#2** [0800 drive flashed with custom firmware + Team
    Xecuter X360USB PRO](0800 "wikilink")

## Kreon drive Setup & Dumping

### Tools / First Time Setup

  - [Kreon disc
    drive](DiscImageCreator:_Optical_Disc_Drive_Compatibility#Xbox_original_.26_Xbox_360 "wikilink").
  - Flash your Kreon disc drive's firmware:
      - Download the appropriate firmware for your model:
          - [SH-D163A /
            TS-H353A](https://archive.org/download/xbox-tools/SH-D163A_SB01_KREON_V100.zip)
          - [SH-D163B /
            TS-H353B](https://archive.org/download/xbox-tools/SH-D163B_SB01_KREON_V100.zip)
          - [SH-162C / TS-H352C /
            SD-M2012C(?)](https://archive.org/download/xbox-tools/SH-D162C_TS05_KREON_V100.zip)
          - [SH-D162D /
            TS-H352D](https://archive.org/download/xbox-tools/SH-D162D_SB00_KREON_V100.zip)
      - Unzip the firmware software, open up the command line and **cd**
        (change directory) to it's location.
      - Run the command: **sfdnwin.exe -nocheck**
      - You'll get a pop up that says "-Nocheck Use\!\!\!", click "OK"
        beneath it. This will open the SFDNWIN app.
      - In the app, select your "Drive".
      - Click the light-blue Folder icon in the upper left part of the
        app, then select the ".bin" file that came with the app.
      - Click the green Folder icon.
      - If successful you will be asked to restart your computer, do
        this.

### Dumping

**Dump with this guide: [Disc Dumping Guide
(DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink"). For newer Xbox 360
discs if you have trouble getting DICUI to read them, you can use the
below guide**:

  - Download the following app pack: [Xbox Original and 360 Dumping
    Kit](https://archive.org/download/xboxoriginaland360dumpingkit/Xbox%20Original%20and%20360%20Dumping%20Kit.7z)
  - Xbox Backup Creator:
      - Open the Xbox Backup Creator app by double clicking on "Xbox
        Backup Creator.exe".
      - Navigate to the "Drive Tools" tab then click "Security Sector".
        Save this file ("SS.bin") to the "Xbox Original and 360 Dumping
        Kit" folder.
      - Click on "PFI Sector" ("PFI.bin") and "DMI Sector" ("DMI.bin")
        to save these as well.
      - Close Xbox Backup Creator app.
  - Press the eject button on your drive twice so that it will open and
    close your drive (remounting the Xbox partitions). DO NOT SKIP THIS
    STEP.
  - In the "Xbox Original and 360 Dumping Kit" folder:
      - Open "dump.bat" with Notepad app by right-click -\> Edit
      - Change the drive letter ("H" by default) to the drive letter of
        your Kreon.
      - Double click on the "dump.bat" file and wait until dumping is
        complete (reaches 100%).
      - Now the Xbox game will be dumped to "Track 01.iso" and security
        sectors will be extracted.
  - Include the following files in your redump submission: DMI.bin,
    PFI.bin, sectors.txt, and SS.bin.

Note: Some stubborn discs may not read with FreeCell, as it lacks
thorough error logic and read speed control. If you have a stubborn
disc, you may be able to use an 0800 drive and Xbox Backup Creator to
successfully dump it.

## Dumping with 0800 drives

  - Software: [Xbox Backup
    Creator 2.9.0.425](https://archive.org/download/xbox-tools/Xbox_Backup_Creator-v2.9.0.425.zip)
  - Open the app Xbox Backup Creator 2.9.0.425
  - On the Options tab, check "Build Clean ISO".
  - On the Read tab, uncheck "Use Sector Mapper (Xbox One)" (this can
    only be checked/unchecked with an original Xbox disc inserted - may
    not affect X360 dumps, needs testing).
  - Click the Start button on the Read tab.
  - A read error should occur shortly after starting the dump. This is
    normal. Check the box "Apply zero fill to all remaining sector
    errors." and click the "Zero-Fill Sector(s)" button.
  - When the dump is complete, make sure that the log window reports
    exactly 65536 unrecoverable sectors. These are the security sectors.
    If the number is higher, this means there were actual read errors
    and your dump is likely bad. Some games can still be read at a
    slower speed and with more attempts at reading bad sectors. On the
    Options tab, choose your drive under the "Drive Specific" section,
    then choose "Xbox One" in the dropdown beneath. Then set Block Retry
    Limit and Sector Retry Limit to 20, and Set Speed to 1x. The dump
    will take a bit longer, but dumpers have managed to save otherwise
    bad discs by reading them in this manner.

## Submitting Dump Info: original Xbox

  - **Game Title**: Most obvious, is located everywhere. Please include
    subtitle if any.
  - **Region**: The region the disc originated from like USA, Japan or
    Europe
  - **Languages/Language Select**: Some games either show a language
    selection screen at startup or in the game options. Many games will
    boot with different languages depending on the active language
    selected in the BIOS. Booting the game with each language selected
    in the bios is necessary to identify the supported languages for
    these games. Note that it is possible to submit a game without
    checking the languages, but this then needs to be stated in your
    submission.
  - **Serial & Version**: Open the DMI.bin file with Windows' Notepad
    app and you'll find a string like MS00402A. This string contains
    valuable information: in this case, MS004 is the disc serial
    (MS-004). 02 is the version (1.02). A is the region code (NTSC).
      - Region Codes: W = Region Free, A = NTSC, J = NTSC-J, E = PAL, K
        = (NTSC, NTSC-J), L = (NTSC, PAL)
  - **Edition**: some games were rereleased in different packages or
    bundled with extra hardware, for example, **Classics**/**Platinum
    Hits**. If the game was released in original package, post edition
    as "Original".
  - **Case Barcode**: The number on the case displayed beneath the
    vertical lines, see [Barcode](http://en.wikipedia.org/wiki/Barcode).
  - **Ring codes**: The string of characters displayed on the inner
    rings of the disc. Check older submissions to make sure that you
    report everything that is needed. Make sure you have good lighting
    conditions and/or a magnifying glass if you have problems reading
    the text. For more information about the (mould) SID codes see [this
    link](http://www.ifpi.org/content/library/sid-code-implementation-guide.pdf).
  - **DMI/PFI/SS Info**: Use a hash program like HashCalc to get the
    CRC32 hash for the DMI.bin, PFI.bin, and SS.bin files. You should
    store the CRCs as shown below.
      - DMI: hash
      - PFI: hash
      - SS: hash
  - **Security Sector Ranges**: The contents of the sectors.txt file.
  - **Size**: The size of the dumped iso file. Xbox discs are always
    7,825,162,240 bytes.
  - **CRC32/MD5/SHA1**: Use a hash program like HashCalc to get the
    CRC32, MD5, and SHA1 hashes of the dumped iso file.

## Submitting Dump Info: Xbox 360

  - **Game Title**: Most obvious, is located everywhere. Please include
    subtitle if any.
  - **Region**: The region the disc originated from like USA, Japan or
    Europe
  - **Languages/Language Select**: Some games either show a language
    selection screen at startup or in the game options. Many games will
    boot with different languages depending on the active language
    selected in the BIOS. Booting the game with each language selected
    in the bios is necessary to identify the supported languages for
    these games. Note that it is possible to submit a game without
    checking the languages, but this then needs to be stated in your
    submission.
      - Note: You may have to change your Xbox 360 system locale in
        order to access languages not supported by the dashboard, such
        as Czech, Danish, Dutch, Norwegian, and Swedish (locale = Czech
        Republic/Slovakia, Denmark, Netherlands, Norway, Sweden). Using
        the Image Browser in Xbox Backup Creator may help to identify if
        the game uses any of these languages.
  - **Serial & Version**: Open the DMI.bin file with Windows' Notepad
    app and you'll find a string like AV202202E0X11. This string
    contains valuable information: in this case, AV2022 is the disc
    serial (AV-2022). 02 is the version (1.02). E is the region code
    (PAL). Finally, the last two bytes tell you that it's Disc 1 of 1.
      - Region Codes: W = Region Free, A = NTSC, J = NTSC-J, E = PAL, K
        = (NTSC, NTSC-J), L = (NTSC, PAL), H = (NTSC-J, PAL)
  - **Edition**: some games were rereleased in different packages or
    bundled with extra hardware, for example, **Classics**/**Platinum
    Hits**. If the game was released in original package, post edition
    as "Original".
  - **Case Barcode**: The number on the case displayed beneath the
    vertical lines, see [Barcode](http://en.wikipedia.org/wiki/Barcode).
  - **Ring codes**: The string of characters displayed on the inner
    rings of the disc. Check older submissions to make sure that you
    report everything that is needed. Make sure you have good lighting
    conditions and/or a magnifying glass if you have problems reading
    the text. For more information about the (mould) SID codes see [this
    link](http://www.ifpi.org/content/library/sid-code-implementation-guide.pdf).
  - **DMI/PFI/SS Info**: Use a hash program like HashCalc to get the
    CRC32 hash for the DMI.bin, PFI.bin, and SS.bin files. You should
    store the CRCs along with the DMI string as shown below.
      - AV202202E0X11
      - DMI: hash
      - PFI: hash
      - SSv1: hash
          - If you dumped with the Kreon method, submit the SS as
            "SSv1".
          - If you dumped with the 0800 method, submit the SS for XGD3
            discs as SSv2 and SS for XGD2 discs as SSv1.
            (ss_sector_range will convert/downgrade original XGD2 SSv2
            files to SSv1, so that 0800 drive SS files will match Kreon
            drive SS files).
  - **Primary Volume Descriptor (PVD)**: Open the iso file with
    IsoBuster. Right click on Track 1 \> Sector View \> type "16" in at
    the top, then copy the data at 0320 - 0370 (full six rows) and paste
    it into your dump info document.
  - **Security Sector Ranges**: The contents of the sectors.txt file.
  - **Size**: The size of the dumped iso file. Provide the size in
    bytes.
  - **CRC32/MD5/SHA1**: Use a hash program like HashCalc to get the
    CRC32, MD5, and SHA1 hashes of the dumped iso file.

### Verification

In case you're verifying a dump that is already in the database, don't
worry if your DMI's and SS's CRCs don't match. They often differ between
various regions, even if the actual image checksums match. The PFI, on
the other hand, should be identical for all games of a certain WAVE.
Known PFI CRCs so far are:

  - WAVE1: 739CEAB3
  - WAVE2: A4CFB59C
  - WAVE3: 2A4CCBD3
  - WAVE4: 05C6C409
  - WAVE5: 05C6C409
  - WAVE6: 05C6C409
  - WAVE7: ????????
  - WAVE8: 0441D6A5
  - WAVE9: 0441D6A5
  - WAVE10: E18BC70B
  - WAVE11: E18BC70B
  - WAVE12: E18BC70B
  - WAVE13: 40DCB18F
  - WAVE14: ????????
  - WAVE15: 23A198FC
  - WAVE16: AB25DB47
  - WAVE17: ????????
  - WAVE18: 169EF597
  - WAVE19: 032CCF37
  - XDG3: 26AF4C58

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")