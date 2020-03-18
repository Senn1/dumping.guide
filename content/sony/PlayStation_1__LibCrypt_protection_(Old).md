---
title: "PlayStation 1 LibCrypt Protection (Old)"
---


Note: This guide is outdated, please see
[here](http://wiki.redump.org/index.php?title=CD_Dumping_Guide_\(Disc_Image_Creator\)).

The **PlayStation 1: LibCrypt protection** guide is intended to allow
you to determine if a game has LibCrypt and how to properly rip it.

## Common Information

Sony first introduced LibCrypt protection in PAL version of MediEvil in
October 1998. Since then more than hundred games containing LibCrypt
have been released. What's special about this protection is that it uses
subchannels to store some non-Yellow Book data, thus breaking the
standard.

Every CD sector contains 2352 bytes of main channel data and 96 (+ 2
sync) bytes of subchannels data. While main channel stores user data,
sync and error-correction codes, subchannels data was not intended to
contain user data. 96 bytes of subchannels are divided to 8 12-byte
channels: P, Q, R, S, T, U, V, W. In case of non-protected CD channel P
contains pause info, channel Q contains current track flags and current
sector address; other subchannels are zeroed. As all this data can be
included in CUE, it's one of the reasons PSXDB images contain only main
channel data. The other reason is that it's nearly impossible to make
perfect copy of subchannels data, because they don't have
error-correction codes, not being encoded with CIRC. So, both dumping
subchannels and calculating their checksums makes no sense.

Discs with LibCrypt protection have 16 or 32 sectors with slightly
modified Q-channel, comparing to the same sectors in standard Yellow
Book disc. The first half of the sectors is located on 3rd minute, and
the second half on 9th minute. All modified sectors can be divided into
pairs, the distance between sectors in each pair is 5 sectors. At the
moment we have found 3 different protected sectors generation schemas.

## Protected sectors generation schemas

  - 2 bits from both MSFs are modified, CRC-16 is recalculated and XORed
    with 0x0080.
      - Games: [MediEvil (Europe)](http://redump.org/disc/592/).
  - 2 bits from both MSFs are modified, original CRC-16 is XORed with
    0x8001.
      - Games: [CTR: Crash Team Racing (Europe) (En,Fr,De,Es,It,Nl) (No
        EDC)](http://redump.org/disc/798/), [CTR: Crash Team Racing
        (Europe) (En,Fr,De,Es,It,Nl)
        (EDC)](http://redump.org/disc/897/), [Dino Crisis
        (Europe)](http://redump.org/disc/710/), [Eagle One: Harrier
        Attack (Europe) (En,Fr,De,Es,It)](http://redump.org/disc/880/)
        et al.
  - Either 2 bits or none from both MSFs are modified, CRC-16 is
    recalculated and XORed with 0x0080.
      - Games: [Ape Escape: La Invasión de los Monos
        (Spain)](http://redump.org/disc/1128/) et al.

## Detecting and dumping LibCrypted data

### Method one: psxt001z

For this you need [psxt001z 0.21
beta 1](http://redump.org/download/psxt001z-0.21b1.7z). Insert your
PlayStation CD in drive and type in command line:

`psxt001z --libcryptdrvfast [drive_letter]`

for example,

`psxt001z --libcryptdrvfast D:`

In case tool reports error, try method two. If eveything is OK, it will
start scanning disc for modified sectors. Please note that "modified"
doesn't mean LibCrypted, because sectors contents also depends on disc
quality and drive. When scanning finished, the number of modified
sectors will be printed. Please include "sectors.log" file (which
contains list of modified sectors along with their contents) when
posting disc info to the forum or using internal site function. If error
occured during the scanning process, try running the tool again or
method two.

### Method two: CloneCD + psxt001z

For this you need
[CloneCD](https://www.redfox.bz/download/SetupCloneCD.exe) and
[psxt001z 0.21 beta 1](http://redump.org/download/psxt001z-0.21b1.7z).
Install CloneCD, insert your PlayStation CD in drive, run CloneCD, press
first button, select drive from the list, then select "Game CD" profile
(not "Protected PC Game"), and start dumping. When image is created,
delete all files but "IMAGE.SUB". Then type in command line:

`psxt001z --libcrypt [path_to_sub]>sectors.log`

for example,

`psxt001z --libcrypt "C:\IMAGE.SUB">sectors.log`

Please include generated "sectors.log" file (which contains list of
modified sectors along with their contents) when posting disc info to
the forum or using internal site function.

## Storing LibCrypt data

To store LibCrypt data, we use SBI format, which contains modified-only
sectors with Q-channel data. SBIs for LibCrypted discs can be downloaded
from PSXDB (link "SBI subchannels" on protected disc page). SBI format
is supported by:

  - ePSXe, PlayStation emulator. To use SBI, name it after EXE name,
    leaving extension .sbi, and put in /epsxe/pathes folder. For
    example, "SLES_025.29.sbi" for PAL version of Resident Evil 3:
    Nemesis.
  - P.E.Op.S. CDR plugin, which is supported by many PlayStation
    emulators. To use SBI, open plugin settings window, select "Use
    subchannel SBI/M3S info file" option from "subchannel reading" menu,
    then choose your SBI in "File" field.

Unfortunately, no disc emulation or burning software currently supports
SBI, neither do image formats. Our new image format with SBI support is
in early development stage.

## Links

  - [PSXCPLIST](https://web.archive.org/web/20091026192418/http://geocities.com/psxcplist/)
    — PlayStation Copy Protection list — list of both LibCrypt and
    Anti-Modchip protected games.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")