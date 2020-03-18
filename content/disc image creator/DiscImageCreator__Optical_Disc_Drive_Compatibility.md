---
title: "DiscImageCreator Disc Drive Compatibility"
---

DiscImageCreator (DIC) is an a disc dumping app focusing on perfect disc
dumping only. Some formats require certain drive models to dump
perfectly.

## DVD

DVD-Video and DVD-Rom dumping is supported with ANY drive that supports
the DVD format. For your first dump/submission, please dump twice to
verify matching hashes for any potentially misbehaving DVD-Rom drives.

For Xbox OG and 360 see [this drive
list](DiscImageCreator:_Optical_Disc_Drive_Compatibility#Xbox_original_.26_Xbox_360 "wikilink").

## CD-Rom / CD-Audio

CD format is particularly a pain in the ass, hardware support wise.
**Certain models of Plextor brand drives can dump with DIC** flawlessly.
Your drive should have the [final
firmware](http://www.skcj.co.jp/discon/download/index.html) installed.
**The final firmware is also linked below on archive.org for most
models.**

  - USB Models:
      - [PX-755UF](https://archive.org/download/PlextorFirmware/px755A%20&%20px755SA_108.zip)
      - [PX-716UF](https://archive.org/download/PlextorFirmware/px716A%20&%20px716SA%20&%20px716UF_111.zip)
      - [PX-712UF](https://archive.org/download/PlextorFirmware/px712A%20&%20px712SA%20&%20px712U_109.zip)
      - [PX-708UF](https://archive.org/download/PlextorFirmware/px708A%20&%20px708UF_112.zip)
  - SATA Models. Note: These can be very hard to find or expensive, it's
    often easier to just buy an IDE model + IDE \> USB adapter.
      - [PX-760SA](https://archive.org/download/PlextorFirmware/px760A%20&%20px760SA_107.zip)
      - [PX-755SA](https://archive.org/download/PlextorFirmware/px755A%20&%20px755SA_108.zip)
      - [PX-716SA](https://archive.org/download/PlextorFirmware/px716A%20&%20px716SA%20&%20px716UF_111.zip)
      - [PX-712SA](https://archive.org/download/PlextorFirmware/px712A%20&%20px712SA%20&%20px712U_109.zip)
  - IDE Models. Note: IDE models can be used on a Laptop with a USB
    Adapter (search "UGREEN USB to IDE Converter, USB 3.0 to IDE" on
    Amazon - do NOT buy a cheap crappy Chinese adapter) or a Desktop
    tower with a cheap card.
      - PX-760 series:
        [PX-760A](https://archive.org/download/PlextorFirmware/px760A%20&%20px760SA_107.zip)
      - PX-755 series:
        [PX-755A](https://archive.org/download/PlextorFirmware/px755A%20&%20px755SA_108.zip)
      - PX-716 series:
        [PX-716A](https://archive.org/download/PlextorFirmware/px716A%20&%20px716SA%20&%20px716UF_111.zip),
        [PX-716AL](https://archive.org/download/PlextorFirmware/px716l%20aka%20px716AL%20&%20px716UFL_102.zip),
        PX-716UFL
      - PX-714 series:
      - PX-712 series:
        [PX-712A](https://archive.org/download/PlextorFirmware/px712A%20&%20px712SA%20&%20px712U_109.zip)
      - PX-708 series:
        [PX-708A](https://archive.org/download/PlextorFirmware/px708A%20&%20px708UF_112.zip)
      - PX-704 series:
      - [Premium2
        series](https://archive.org/download/PlextorFirmware/Premium2_103.zip):
      - Premium series: Premium, PremiumU (good drives to dump with, but
        expensive)
      - PX-W5224 series: [PX-W5224A, PX-W5224TA,
        PX-W5224TU](https://archive.org/download/PlextorFirmware/pxw5224_104.zip)
        (Second best drive to dump with, doesn't have problems with
        SecuROM/SafeDisc)
      - PX-4824 series: [PX-W4824A, PX-W4824TA, PX-W4824U,
        PX-W4824TU](https://archive.org/download/PlextorFirmware/pxw4824_107.zip)
        (Can't dump SecuROM nor illegal ToC)
      - PX-4012 series: [PX-W4012A, PX-W4012TA, PX-W4012S, PX-W4012TS,
        PX-W4012U,
        PX-W4012TU](https://archive.org/download/PlextorFirmware/pxw4012_107.zip)
        (Best drive to dump with, reads errors better)
  - SCSI Models: SCSI models can only be used with a Desktop tower with
    a cheap card (no laptops).
      - [PX-W4220T](https://archive.org/download/PlextorFirmware/pxw4220_104.zip),
        PX-32TS/CS, PX-83CS/85CS, PX-63CS/65CS, PX-43CS 43CE 43CH/45CS
        45CE 45CH, DM-3028/5028, DM-3024/5024, DM-3021/5021,
        DM-3020/5020

The Plextors in the 700 range that can read DVDs have firmware bugs and
the lasers can go bad easily.

Additional drive brands may work, some with limitations (such as can
only read discs with a negative write-offset). A few LG/Asus BD drives
are also compatible with DIC dumping methods, **but they do need to be
[flashed with the Asus BW-16D1HT 3.02
firmware](Flashing_with_Asus_BW-16D1HT_3.02_firmware "wikilink")**.
Note: not all listed models have been (known) tested with DIC yet,
please share your results.

  - Asus BC-12B1ST b (ASUS Label (circle) ID: 90DD0230-B38000, ASUS
    Label (rectangular) ID: MEZ65067809). (Not tested with DIC yet)
  - Asus BC-12D2HT (confirmed compatible)
  - Asus BW-16D1HT (confirmed compatible)
  - Asus BW-16D1H-U
  - LG BE16NU50
  - LG BH14NS50
  - LG BH14NS58
  - LG BH16NS40
  - LG BH16NS50
  - LG BH16NS55 (plus WH14NS40, BH16NS40 and WH16NS40 with SVC
    CODE:NS50) (confirmed compatible, but most probably negative offset
    discs only)
  - LG BH16NS58
  - LG BH16NS60
  - LG BP50NB40
  - LG BP50NB50
  - LG BP55EB40
  - LG BP55EB50
  - LG BP60NB10
  - LG BU40N
  - LG BU50N
  - LG CH12NS40
  - LG UH12NS30 (confirmed compatible, but negative offset discs only)
  - LG UH12NS40
  - LG WH14NS40
  - LG WH14NS50
  - LG WH16NS40
  - LG WH16NS50
  - LG WH16NS58
  - LG WH16NS60
  - LG WP50NB40
  - LG WP50NB50

## GD-Rom

GDs are strange in that they contain two distinctly different areas of
data. What this means to you is that you will have to dump the disc's LD
and HD area separately. Unfortunately, this also means that you **will
need special hardware**.

For dumping the **LD area**, the same rules apply as in dumping a CD, as
they use the same technology. A list of compatible drives for dumping LD
area is above
[\#CD-Rom_.2F_CD-Audio](#CD-Rom_.2F_CD-Audio "wikilink").

### HD area

But for the **HD area** the process is different, and you need one of
the following drives to dump it. In our testing, some drives worked
better than others:

**Recommended** (tested with dcdumper):

  - Samsung TSSTCorp models:
      - TS-H353A aka SH-D163A
      - TS-H352C aka SH-162C

**Not Recommended or Don't Work** (were rumored to work):

  - LG model: GCR-8522B - Works, but "slower and klunkier" than
    Recommended drive models.
  - Lite-On model: SOHD-167T - difficult to remove lid to swap discs,
    pin eject method doesn't seem to work. When dumping, lots of issues,
    I couldn't get a single section to dump properly.
  - NEC model: CDR-1901A - difficult to remove lid to swap discs, did
    not get matches in RevQuixo's test (needs more testing?)
  - Samsung TSSTCorp models: TS-H353B (isn't as fast or match-friendly
    as TS-H353A & TS-H352C)

**Untested, but should work(?)**

  - Lite-On models: LH-18A1H, LTD-165H, SOHD-16P9S (wiggy bought for
    testing)
  - Plextor models: PX-W4824TA, PX-W4824TU, PX-755SA
  - Samsung TSSTCorp models: TS-H192C, SH-D162D

## PlayStation 3 & 4

Compatible drive list sourced from [here](https://rpcs3.net/quickstart).

  - Asus models: BC-08B1LT, BC-16D1HT, BC-12B1ST, BC-12D2HT, BW-12B1ST,
    BW-16D1HT
  - BENQ BR1000
  - LG models: BH26NS40, UH12NS30, BH16NS40, BH16NS48, BH14NS40,
    WH24NS40, WH12LS30, WH24LS30, WH26NS40, WH16NS40, WH14NS40,
    WH16NS48, BP50NB40
  - LITE-ON models: DH-4O1S, IHBS112
  - Sony Optiarc 5300S
  - Sony PlayStation 3 stock
    drive[1](https://www.ebay.com/itm/252061696576) with 3k3y ripper
    adapter (**Note: can key extract PS3 games.**)
  - [Sony PlayStation 3 Console with Custom
    Firmware](PlayStation_3_Dumping_Guide#Dumping_with_a_PS3_Console_with_CFW_3.55 "wikilink")
    (**Note: for PS3 dumping only, can key extract.**)

## Xbox original & Xbox 360

Dumping Xbox original and Xbox 360 there are two options for hardware.
The Kreon is much easier and cheaper.

  - Kreon disc drives:
      - SATA models:
          - SH-D163A aka TS-H353A
          - SH-D163B aka TS-H353B
      - IDE models:
          - SH-162C aka TS-H352C aka SD-M2012C(?)
          - SH-D162D aka TS-H352D
  - [0800 drive flashed with custom firmware + Team Xecuter X360USB
    PRO](0800 "wikilink")

## Xbox One

For compatibilty discussion
see[2](http://forum.redump.org/topic/16301/done-xbox-one/)

  - BDR-208D
  - BDR-209D
  - Pioneer BD-ROM BDC-TD03VA (BDC-TD03): Only compatible with single
    layer BD-25 discs, not double layer BD-50 discs.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")
[Category:Optical Disc Drives](Category:Optical_Disc_Drives "wikilink")