---
title: "DVD (DiscImageCreator Command Line Interface version"
---

**Note: This guide is for the Command Line Interface version of Disc
Image Creator, if you have no idea what that means, please use the GUI
version (as it's much simpler): [Disc Dumping Guide
(DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").**

The purpose of this [dumping guide](Dumping-Guides "wikilink") is create
perfect copies of DVD-based discs using a Windows computer with Disc
Image Creator app. For additional questions, support, and reference, use
the forum thread
[here](http://forum.redump.org/topic/10483/discimagecreator/). Do not be
shy if you need help\! For copy-protected DVD-Video (standard movies)
see this guide: [DVD-Video Dumping
Guide](DVD-Video_Dumping_Guide "wikilink").

Compatible disc drives: Any DVD compatible computer disc drive.

## Disc Compatibility

This dumping guide encompasses the following DVD disc types:

  - **PlayStation 2 (DVD)**. Most PS2 discs were released in DVD disc
    format (white/clear data-side color), however some were released in
    CD-ROM format (indigo data-side color). This guide covers only the
    DVD discs, for CD-ROM discs see the guide [CD Dumping
    Guide](CD_Dumping_Guide_\(Disc_Image_Creator\) "wikilink").
  - **Computer Games (DVD)**, including Windows (IBM PC Compatible),
    Macintosh, or Windows/Mac hybrid discs. Many older computer games
    were released in DVD or CD-ROM format. This guide covers only DVD
    games. For CD-ROM discs see the guide [CD Dumping
    Guide](CD_Dumping_Guide_\(Disc_Image_Creator\) "wikilink").

## First Time Setup / Tools

  - **Disc Image Creator**: [Download the latest
    version](https://github.com/saramibreak/DiscImageCreator/releases)
    (should be named similar to: "DiscImageCreator_20180127.zip"), then
    unzip it. Wherever you put the unzipped folder will affect where
    your roms are written to when you dump the discs.
  - **Install these Microsoft Packages**:
    [1](https://www.microsoft.com/en-us/download/details.aspx?id=49981)
    [2](https://www.microsoft.com/en-us/download/details.aspx?id=52685)

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
    For example: **DiscImageCreator.exe dvd
    <span style="color:red">d</span> MyGameTitle_Dump1.iso
    <span style="color:#0000FF">8</span>** This command should be
    changed for your specifics, "<span style="color:red">d</span>" is
    the dvd disc drive location, and
    "<span style="color:#0000FF">8</span>" is the max read speed on the
    example DVD drive model. You can Google your DVD drive model to find
    out it's max read speed, but 8 should be safe otherwise. Dump the
    game twice, "MyGameTitle_Dump1.iso" and "MyGameTitle_Dump2.iso",
    changing the title to suit your needs.

## Submitting your Dump

Time to have your disc added to redump's database\! If it is your first
submission, do so via the forum. [Forum sign-up
here](http://forum.redump.org/topic/12228/want-to-register-please-read-first/).
Forum disc info submission
[here](http://forum.redump.org/forum/11/dumps/).

  - **Game title**: Most obvious, is located everywhere. Please include
    subtitle.
  - **Disc title**: Some games stored on multiple discs may have discs
    with titles. Examples: [Armored Core: Nexus (Disc 1)
    (Evolution)](http://redump.org/disc/15041/) and [(Disc 2)
    (Revolution)](http://redump.org/disc/15042/).
  - **Game languages**: Start the game and look for "Language" menu in
    options.
  - **Version**:
      - For PS2 games, find the file on your disc named "SYSTEM.CNF" and
        open in Notepad app, "VER" = version number.
      - For PC games, the game version is either located in files like
        INI, CONFIG, README and or can (only) be obtained from in-game
        main menu.
  - **Edition**: Some games were re-released in different packages, for
    example, "Platinum", "Greatest Hits", "PlayStation 2 the Best"
    series. If game was released in original package, post edition as
    "Original".
  - **Media**: If the DVD is greater than 4.7 GB and up to 8.5 GB, the
    DVD is DVD-9. Otherwise most of the time, it is DVD-5.
  - **Barcode**: Submit the numbers from the barcode:
    [EAN](http://en.wikipedia.org/wiki/European_Article_Number) /
    [UPC](http://en.wikipedia.org/wiki/Universal_Product_Code) code,
    usually printed on the back cover of the packaging or disc case.
  - **Serial number**: Usually printed on disc itself.
  - **Ring code info**: stamped on the inner ring. Check both sides for
    any ringcodes (small stamps may require magnifying glass to see).
    Report whatever ring codes are readable.
  - **.dat and .txt files**: DiscImageCreator will generate .dat and
    .txt files. Attach these files to your post when submitting.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")