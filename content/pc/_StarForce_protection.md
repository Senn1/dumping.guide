---
title: "SecuROM and StarForce"
---

This guide will help you understand, identify and properly dump
**SecuROM** and **StarForce** protected discs.

**Work In Progress**

## Information & Features

**SecuROM** is a CD/DVD copy protection and digital rights management
product developed by Sony DADC. SecuROM aims to resist home media
duplication devices, professional duplicators, and attempts at reverse
engineering software. It is most often used for commercial computer
games running under the Microsoft Windows platform.

**StarForce** is a software copy protection mechanism developed by
Protection Technology.

**Physical Measurements:** SecuROM and StarForce are called *Physical
Protections* because they perform measurements, like calculating sector
distances, in CDs and DVDs. Both install a rootkit upon installation of
the game and can only be removed by using official uninstallers.

**Twin Sectors:** In SecuROM discs The 4th sector from the end is a twin
sector which means it exists twice in the CD. It is usually skiped
(corrected by drive) by common software and cannot be burned as it
breaks the standard. CDMage will detect the twin sector, as arrorenous,
if the CD is dumped correctly.

## Detection

  - For SecuROM you need [ProtectionID
    download](https://web.archive.org/web/20180101183850/https://pid.gamecopyworld.com/dl.php?f=ProtectionId.690.December.2017.rar)
    or [BurnOut](http://sourceforge.net/projects/burnout/).
  - For StarForce you need [StarForce
    Helper](http://www.star-force.com/support/sfhelper/)

**Alternate method:** These tools don't always specify the exact version
number. The version number of SecuROM can be found after AddD string in
the protected executable using a HEX Editor or Viewer. It always appears
at 98% of the file. For StarForce find the protect.dll file in the
protected application folder (the file can have another name, but it
always has the .dll extension), right-click it and select Properties.
Select Version tab then. The protection version number is in the
BuildSignature (or BuildInfo) section.

## Dumping

The data track of physical protection discs is dumped normally with
Isobuster, follow the main CD dumping guide for details. If any errors
appear in the process you must abort, clean the disc and try again.

To properly save the measurements you will need to use Alcohol 52% or
120%. Dump the disc with Alcohol and select **Data Position
Measurement**, when asked choose **High** precision and **Low** speed.
The .MDS file that will be created is important for your personal
backup. Unfortunately the database does not support adding those files.

For SecuROM discs you will need to double check. Open the .BIN file with
CDmage and scan for errors. If no errors showed during dumping yet your
image has 1 error, then it is correct.

**MDS Settings:**

  - CDs: Enable (1) Skip reading errors, (2) Sub-Channel Data from
    current disc, and (3) Data Position Management
  - DVDs: Enable (1) Data Position Management, and set it to "high"
    precision.
  - SPEED: 8x is generally accepted as a reasonable speed for generating
    MDS files.

## Subs & CCDs (Optional)

Subchannels and CCD data can be extremely useful in disc replication and
emulation. While redump does not presently archive this information, it
is generally a good idea to capture this data for personal preservation
purposes. Additional steps may be required for mixed-mode discs (i.e.
discs containing CDDA). Search the forums or ask one of the MODs for
help if you get stuck.

  - Use [CloneCD](http://www.slysoft.com/en/clonecd.html) to generate a
    valid CCD file. Be sure to use this [custom
    profile](http://wiki.redump.org/index.php?title=Setting_Up#CloneCD).
  - Use Subdump to capture highly accurate subchannel data from the
    disc. Subdump is an internal development tool, and is presently only
    available upon request. Ask a Moderator if you have interest in
    using it.

## Examples

  - [Unreal Tournament 2003 (Europe) (En,Fr,De,Es,It)
    (Disc 1)](http://redump.org/disc/9600/) (SecuROM)
  - [Cold War - On Your Own Behind the Iron Curtain (USA)
    (Disc 1)](http://redump.org/disc/10573/) (StarForce)
  - [Still Life (USA) (Disc 2)](http://redump.org/disc/11864/)
    (StarForce)

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")