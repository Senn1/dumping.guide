---
title: "CD (DiscImageCreator Command Line Interface version)"
---

**Note: This guide is for the Command Line Interface version of Disc
Image Creator, if you have no idea what that means, please use the GUI
version (as it's much simpler): [Disc Dumping Guide
(DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").**

The purpose of this [dumping guide](Dumping-Guides "wikilink") is create
perfect copies of CD-based discs using a Windows computer with Disc
Image Creator app. For additional questions, support, and reference, use
the forum thread
[here](http://forum.redump.org/topic/10483/discimagecreator/). Do not be
shy if you need help\!

Disc compatibility: Any CD based disc: PlayStation 1, CD Audio, PC Game,
Sega Saturn, Sega CD, Playstation 2 (CDs only with indigo bottom), etc.
This guide covers only CD games. For DVD discs see the guide [DVD
Dumping Guide](DVD_Dumping_Guide_\(Disc_Image_Creator\) "wikilink").

## Drive Compatibility

Disc drives verified to be compatible:

  - Brand: Plextor
      - IDE Models
          - PX-760 series: PX-760A, PX-760SA
          - PX-755 series: PX-755A, PX-755SA, PX-755UF
          - PX-716 series: PX-716A, PX-716SA, PX-716AL, PX-716UF
          - PX-714 series:
          - PX-712 series: PX-712A, PX-712SA
          - PX-708 series: PX-708A, PX-708UF
          - PX-704 series:
          - Premium2 series:
          - Premium series: Premium, PremiumU (good drives to dump with,
            but expensive)
          - PX-W5224 series: PX-W5224A, PX-W5224TA, PX-W5224TU (Second
            best drive to dump with, doesn't have problems with
            SecuROM/SafeDisc)
          - PX-4824 series: PX-W4824A, PX-W4824TA, PX-W4824U, PX-W4824TU
            (Can't dump SecuROM nor illegal ToC)
          - PX-4012 series: PX-W4012A, PX-W4012TA, PX-W4012S,
            PX-W4012TS, PX-W4012U, PX-W4012TU (Best drive to dump with,
            reads errors better)
      - SCSI Models: PX-W4220T, PX-32TS/CS, PX-83CS/85CS, PX-63CS/65CS,
        PX-43CS 43CE 43CH/45CS 45CE 45CH, DM-3028/5028, DM-3024/5024,
        DM-3021/5021, DM-3020/5020
  - Note: IDE models can be used on a Laptop with a USB Adapter (search
    "UGREEN USB to IDE Converter, USB 3.0 to IDE, or Vantec USB to IDE
    Converter" on Amazon - do NOT buy a cheap crappy Chinese adapter) or
    a Desktop tower with a cheap card, or an older desktop with IDE
    natively. Be aware there are no working PCI Express IDE cards.
  - SCSI models can only be used with a Desktop tower with a cheap card
    (no laptops).
  - Your drive should have the latest firmware installed (you can find
    these linked to the appropriate Plextor models
    [here](#CD-Rom_.2F_CD-Audio "wikilink")).
  - Be aware the PX-W4824 series is unsuitable for dumping discs with
    SecuROM (ecc/edc of the mode 2 sector doesn't match), CDS100,
    CDS200, Label Gate, and XCP (Doesn't read TOC correctly).
  - Be aware that the PX-716 series (possibly other DVD drives) is
    unsuitable for dumping some discs, SafeDisc in particular (Illegal
    MSF).

The Plextors in the 700 range that can read DVDs have firmware bugs and
the lasers can go bad easily.

## First Time Setup / Tools

  - **Disc Image Creator**: [Download the latest
    version](https://github.com/saramibreak/DiscImageCreator/releases)
    (should be named similar to: "DiscImageCreator_20180127.zip", then
    unzip it. Wherever you put the unzipped folder will affect where
    your roms are written to when you dump the discs.
  - **Install these Microsoft Packages**:
    [1](https://www.microsoft.com/en-us/download/details.aspx?id=49981)
    [2](https://www.microsoft.com/en-us/download/details.aspx?id=52685)
  - **edccchk.exe**:
    [Download](http://redump.org/download/edccchk-1.26.rar). Place this
    file into your unzipped Disc Image Creator subfolder "Release_ANSI"
    (doing this will help keep all dumping apps in the same folder so
    you don't have to **cd** out).
  - **psxt001z.exe**:
    [Download](http://redump.org/download/psxt001z-0.21b1.7z). Place
    this file into your unzipped Disc Image Creator subfolder
    "Release_ANSI" (doing this will help keep all dumping apps in the
    same folder so you don't have to **cd** out). This is used for PS1
    discs only.

## Dumping

Now you have all the tools, are all setup and ready to begin dumping.
Launch the native Windows app "Command Prompt" (Start menu \> Windows
System \> Command Prompt).

  - Open the Disc Image Creator folder you downloaded and unzipped
    (note: in the example "DiscImageCreator_20180127" is the name of
    the example folder / release version, please update according to the
    version you have), go into the "Release_ANSI" subfolder, and copy
    the directory location. For example
    "C:\\Users\\YOUR_COMPUTER_USERNAME\\Downloads\\DiscImageCreator_20180127\\Release_ANSI"
  - It's time to navigate to this directory inside of the Command Prompt
    app. Type in "cd" followed by your Release_ANSI directory location
    in quotes, for example:

**cd
"C:\\Users\\YOUR_COMPUTER_USERNAME\\Downloads\\DiscImageCreator_20180127\\Release_ANSI"**

  - Now you will type the code in the Command Prompt to dump the disc.
    For example: **DiscImageCreator.exe cd
    <span style="color:red">d</span> MyGameTitle.bin
    <span style="color:#0000FF">8</span> /c2 /nl** This command should
    be changed for your specifics, "<span style="color:red">d</span>" is
    the cd disc drive location, and
    "<span style="color:#0000FF">8</span>" is the max read speed on the
    example disc drive model. 8 should be a read speed supported by most
    drives, but check [this list](Disc_Drive_Read_Speeds "wikilink") for
    your drive's maximum read speed to dump much faster. Change the
    title of "MyGameTitle.bin" to suit your needs.
  - Note: Discs with CD-Audio tracks will create multiple .bin files.
  - Run edccchk.exe with the following command **edccchk
    "MyGameTitle.bin"**. For discs with multiple tracks you will need to
    adjust the command to **edccchk "MyGameTitle (Track 1).bin"** or
    **edccchk "MyGameTitle (Track 01).bin"**. Copy the text output from
    the terminal into a txt file to be submitted with the logs. This
    command checks for EDC. Some discs with irregular exe's (such as
    GameShark discs) will require a [different
    method](PSX_Date_and_EDC_Check_on_Discs_with_Non-Standard_EXE "wikilink").
  - For PS1 discs only, run psxt001z.exe with the following command
    **psxt001z "MyGameTitle.bin"**. For discs with multiple tracks you
    will need to adjust the command to **psxt001z "MyGameTitle (Track
    1).bin"** or **psxt001z "MyGameTitle (Track 01).bin"**. Copy the
    text output from the terminal into a txt file to be submitted with
    the logs. This command checks for the EXE Date. Some discs with
    irregular exe's (such as GameShark discs) will require a [different
    method](PSX_Date_and_EDC_Check_on_Discs_with_Non-Standard_EXE "wikilink").
  - For PS1 PAL discs only, run the following command to check for
    libcrypt copy protection **psxt001z --libcrypt "MyGameTitle.sub" \>
    libcrypt.txt**, then **psxt001z --libcryptdrvfast
    <span style="color:red">d</span> \> libcryptdrv.log** where
    <span style="color:red">d</span> is the disc drive letter.

## Game Copy Protection

Some (mostly PC computer) games use copyright protection that requires
additional commands at the end. If you are unsure when to use these,
[Scan for Copy
Protection](Scanning_for_Copy_Protection_Guide "wikilink") or consult
this thread[3](http://forum.redump.org/topic/10483/discimagecreator/).

  - /nl is for LibCrypt (some PSX PAL discs, just run on all PSX discs
    to keep it simple)
  - /ns for SecuROM (some PC games)
  - /sf for for PC copy protections that can be detected. This can also
    be used for reading unlicensed PS2 discs, but use with caution since
    it can cause excessive read times.
  - /ss for other PC protections with c2 errors.
  - Do not mix the modes, use the correct one for the disc you are
    dumping.

SecuROM data is in the subintention .txt (when /ns parameter is used and
the disc is in fact SecuROM-protected) and should be included with
submitted dump info when this protection is used.

## Submitting your Dump

Time to have your disc added to redump's database\! If it is your first
submission, do so via the forum. [Forum sign-up
here](http://forum.redump.org/topic/12228/want-to-register-please-read-first/).
Submit disc info [here](http://forum.redump.org/forum/11/dumps/).

  - **Game title**: Most obvious, is located everywhere. Please include
    subtitle.
  - **Disc title**: Some games stored on multiple discs may have discs
    with titles. Examples: [Armored Core: Nexus (Disc 1)
    (Evolution)](http://redump.org/disc/15041/) and [(Disc 2)
    (Revolution)](http://redump.org/disc/15042/).
  - **Game languages**: Start the game and look for "Language" menu in
    options.
  - **Version**:
      - For PlayStation 1 games, leave this blank.
      - For PlayStation 2 (CD) games, find the file on your disc named
        "SYSTEM.CNF" and open in Notepad app, "VER" = version number.
      - For PC games, the game version is either located in files like
        INI, CONFIG, README and or can (only) be obtained from in-game
        main menu.
  - **Edition**: Some games were re-released in different packages, for
    example, "Platinum", "Greatest Hits", "PlayStation 2 the Best"
    series. If game was released in original package, post edition as
    "Original".
  - **Media**: Should be "CD" for all dumps. Prototypes would likely be
    "CD-R".
  - **Barcode**: Submit the numbers from the barcode:
    [EAN](http://en.wikipedia.org/wiki/European_Article_Number) /
    [UPC](http://en.wikipedia.org/wiki/Universal_Product_Code) code,
    usually printed on the back cover of the packaging or disc case.
  - **log files**: DiscImageCreator will generate .txt, .dat, .cue, .c2,
    .ccd, .sub files. psxt001z and edccchk output text copied from the
    terminal should be submitted as well. Attach these files to your
    post when submitting. Also generated, but should NOT be submitted to
    redump are .bin, .img, .scm files. The .bin files are your game.
    Files .scm and .img files are another copy of your game in
    deprecated formats - these can be deleted.
  - **Serial number**: Usually printed on disc itself.
  - **Ring code info**: stamped on the inner ring. Check both sides for
    any ringcodes (small stamps may require magnifying glass to see).
    For PlayStation discs with black dye, use
    [this](http://forum.redump.org/post/56100/#p56100) method to obtain
    any hidden ringcodes if possible.
  - PC CD-ROM GAMES ONLY: It's possible when dumping a PC Game that
    DICUI will out put a file ending in "_SubIntention.txt". Copy and
    paste the contents of this file into your submission. If it doesn't
    exist, then do nothing.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")