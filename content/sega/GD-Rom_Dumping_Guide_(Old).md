---
title: "GD-Rom (Old)"
---

<div class="textblock" style="background: #febaba; padding: 10px;">

<span style="font-size: 18px; font-weight: bold;">Note: This dumping
guide is deprecated, please use the updated dumping guide here [GD-Rom
Dumping Guide](GD-Rom_Dumping_Guide "wikilink"). </span>

</div>

## Introduction

The GD-ROM format is actually a special and customized, multisession CD
format developed by Yamaha for Sega. The Dreamcast console contained a
modified 12x CD-ROM reader to read the format, which contained a
high-density layer. This high-density zone is very similar to normal CD
data, except that it is more squeezed (like a CD-R burned with the
GigaRec technology by certain real Plextor writers). The high-density
zone of GD-ROM contains subcodes and raw data sectors (2352 bytes per
sector), and can even can contain CDDA audio tracks.

A GD-ROM consists of two zones:

  - A low density area (the first 2 tracks)
  - A high density area (the rest of the disc).

The low denisty area can be accessed by just about any drive, while the
high density portion is only accessible by COMPATIBLE drives using a
technique called "hotswapping." Hotswapping basically involves pressing
the escape/eject button on the drive while in use to
eject-and-switch-discs ("hot swap") so that the high density portion can
be reached by the ripping software.

Since the low density area is visible by just about any drive, it can be
dumped in the normal way (without hotswapping). See the [Main CD Dumping
Guide](#Main_CD_dumping_guide "wikilink") for instructions on how to
dump the low density tracks.

Because only a handful of drives are capable of reading the high-density
area of a GD-ROM disc there is an on-going list of SUPPORTED or
UNSUPPORTED drives are provided below. The list is a work-in-progress,
so please let us know if a drive can be added to either section\! :)

Lastly, there are presently two methods used to dump redump.org GD-ROMs.
This guide will attempt to walk you through each method. You are free to
choose whichever seems the simplest\!

## Method A

### Software needed

  - CDRWin (v4.0a - v4.0h)
  - [dctools](http://www.mediafire.com/?2qk7vtnjt9w6p7c)
  - [Audio trap disc](http://www.mediafire.com/?2nygv2oyzzz)

### Instructions

The high density area (sector 45000-549150) can be dumped as follows:

1.  Insert the audio trap disc (a disc with a hacked TOC of 99 mins
    audio, burn it with CloneCD or Alcohol).
2.  Use 'startstop.exe \[driveletter\] 1' to stop the drive motor.
3.  Use a pin to press the escape eject button, so the tray will eject
    (or remove the drive cover).
4.  Insert the GD-ROM into the tray and gently push the tray back into
    the drive (or replace the drive cover if you removed it). NOTE: If
    you don't hear the magnet lock into place, there's a 90% chance the
    next step will \*NOT\* work.
5.  Use 'startstop.exe \[driveletter\] 2' to restart the drive motor.
    This will help lock the disc in place\!\!\!
6.  Now extract sectors 44990 - 549150 using CDRWin's 'Select Sectors'
    feature. Make sure you use the following settings:
      - CD Audio (2352)
      - File Format = INTEL
      - Error Recovery = Abort
      - Audio Speed = 1x (if unregistered); 4x (if registered)
      - Read Retry Count = 1
7.  Once the software is finished extracting, use 'ICE.exe dumpfile.bin
    45000' to descramble and split the dump data.
8.  If everything went well, the dump should be ready for submission\!

## Method B

### Software needed

  - \[<http://www.mediafire.com/download/3aaeh22wa7addng/DCdumper_(0.42a>).7z
    DCdumper (v0.42a)\]
  - CDRWin (v4.0a - v4.0h)
  - [dctools](http://www.mediafire.com/?2qk7vtnjt9w6p7c)
  - [Audio trap disc](http://www.mediafire.com/?2nygv2oyzzz)

### Instructions

The downside to Method A is that CDRWin (by itself) can have problems
dumping certain sectors of the GD-ROM. Therefore, JamJam created a tool
called
[DCdumper](http://forum.redump.org/topic/9436/new-dreamcast-dumping-program-test-please/)
to provide more secure sector verification during dumping that generally
results in far less errors and more accurate dumps. CDRWin is still
needed to align the laser, but DCdumper performs the actual dumping.

1.  Insert the audio trap disc into the drive.
2.  Open CDRWin and set it up like you would if you were using it to do
    the dump:
      - CD Audio (2352)
      - File Format = INTEL
      - Error Recovery = Abort
      - Audio Speed = 1x (if unregistered); 4x (if registered)
      - Read Retry Count = 1
3.  Change the 'Start-End' sector to 44990 - \[xxxxxx\] (i.e. the end of
    the first sector range you're scanning); leave everything else the
    same.
4.  Next, use 'startstop.exe \[driveletter\] 1' to stop the drive motor.
5.  Once the drive has stopped, carefully remove the trap disc using the
    hotswap technique (see above), and replace it with the GD-ROM.
      - IMPORTANT: To prevent damage to the edging of your disc, push
        the tray carefully and gently until it's 99.9% of the way in and
        won't seem to go any further. Then, give the WHOLE tray surface
        an EXTRA-HARD push. If you're lucky, you'll hear the magnet
        picking up the disc...but don't worry if you don't. As long as
        you pressed in really hard, nothing should happen to the
        GD-ROM...hopefully\! :)
6.  With the GD-ROM now successfully swapped, use CDRWin to pre-align
    the laser by entering the sector ranges you wish to dump and press
    'Start'. Let it reach 1%, wait a few seconds longer, and then
    'Cancel' the reading. This effectively "aligns" the laser for the
    next step.
7.  Once the laser has been aligned you can run DCdumper to dump the
    same sector range: 'DCdumper.exe \[driveletter\] -df -dt'
8.  Once you finish dumping all sections (1-49), a file called
    "dense.bin" will be created containing the scrambled dump data.
9.  Extract the data using 'ICE.exe' from the dctools collection.
10. If everything went well, the dump is now ready for submission\!

For more information on dumping GD-ROMs using METHOD B, see the
[DCdumper
Tutorial](http://forum.redump.org/topic/12014/dreamcast-dumping-my-best-way/).

## Method C

### Software needed

  - [CD Tool
    (v1.21b)](http://www.cdtool.pwp.blueyonder.co.uk/downloads.htm)
  - [dctools](http://www.mediafire.com/?2qk7vtnjt9w6p7c)
  - [Audio trap disc](http://www.mediafire.com/?2nygv2oyzzz)

### Instructions

METHOD C uses CD Tool to align the laser and perform the dump.

1.  Open CD Tool
2.  Use dctools and the audio trap disc to hotswap the GD-ROM.
3.  Switch back to CD Tool and select the 'CD to image' option.
4.  Set the first sector to '44990' and press 'From TOC'.
5.  Then, assuming you have a decent drive that reports C2 errors,
    choose the following:
      - Subchannel: (001b)
      - Check 'Deinterleave subs'
      - C2 error reporting: 01b
      - C2 error reporting read order:
          - If using a Mediatek based Lite-On drive, set the order to
            "Main+Sub+C2". Otherwise, CDTool will wrongly arrange the C2
            and sub files.
          - For all other drives, use the default order (Main+C2+Sub).
6.  Try several read speeds in order to determine the optimal (4x speed
    is what some users have found luck with).
7.  When dumping is finished, the .C2 file created must \*NOT\* have any
    non-null bytes. If so, then there are errors in the dump.
8.  Use ICE.exe to extract the data, and the dump should be ready for
    submission\!

## Best Practices / Tips

  - Burn the Audio Trap Disc image to a CD-RW vs. a regular CD-R. CD-RWs
    are more durable, and are less prone to damage than a CD-R.
  - Hotswapping (the eject-pin-hole method) works very well, and is
    generally favored over the lid-removal method. However, extra care
    is necessary during the transition in order to avoid scratching the
    GD-ROM and/or audio trap disc.
  - To prevent damage to the edging of your disc, push the GD-ROM in the
    tray carefully and gently until it's 99.9% of the way in and won't
    seem to go any further. Then, give ALL parts of the tray an
    EXTRA-HARD push. If you're lucky, you'll hear the magnet picing up
    the disc...but don't worry if you don't. As long as you pressed in
    really hard, nothing should happen to the GD-ROM...hopefully\! :)
  - If you own a Plextor drive, you can quickly determine the factory
    write offset value by using px_d8 (v1.01A) tool (usage: 'px_d8
    \[driveletter\] 45000'). Take note that the write offset of the low
    density zone can differ from the write offset of the high density
    zone. (Refer to the [Main CD Dumping
    Guide](#Main_CD_dumping_guide "wikilink") for details on how to
    determine the write offset value with non-Plextor drives.)
  - A best-practice for dumping with DCdumper is to dump-then-match the
    GD-ROM in three separate section ranges. This technique allows you
    to quickly re-align the laser (using CDRWin), reset the trap disc,
    and resume dumping if/when DCdumper encounters an unreadable sector
    (which happens occasionally). The following is a recommended (though
    optional) range split to use for dumping: (1) 044990-240480
    \[sections 1-19\], (2) 240481-435971 \[sections 20-38\], (3)
    435972-549150 \[sections 39-49\]. DCdumper won't create a dense.bin
    until it has successfully matched all section dumps, so you can
    stop/restart the program at any point in time to pause dumping,
    realign the laser, or reset the audio trap disc.

## Troubleshooting

  - If you have a drive on the SUPPORTED list, and it doesn't work after
    some retries: (1) read ahead a bit (sector 60,000-x), (2) try/retry
    the normal range again, and (3) try removing the cover.
  - If DCdumper is working fine and then begins to fail reading sector
    ranges, STOP the program, DELETE the failed partial .bin file(s)
    (since DCdumper does \*NOT\* do this for you), re-scan the opening
    1-2% of the sector range using CDRWin, and then try re-running
    DCdumper to see if it fixes itself. If it still fails, you may need
    to re-insert the audio trap disc and realign the laser using CDRWin
    (i.e. start over). If it STILL fails, then you may have a bad disc
    or a drive-related problem. Check and/or clean your disc's data
    surface, and verify that your drive's firmware version is
    up-to-date.
  - If you keep getting errors during the extraction OR if your drive
    fails to read the GD-ROM disc after swapping, then this most likely
    means that your drive isn't suitable for dumping GD-ROM discs. See
    the SUPPORTED and UNSUPPORTED lists for more information.
  - If some of the required software tools aren't working properly, try
    updating your drive's firmware to the latest version. Out-of-date
    firmware has been known to cause problems with some of the homebrew
    tools used in dumping discs.
  - If you're having problems descrambling the 'dense.bin' file with
    ICE.exe, refer to this [forum
    discussion](http://forum.redump.org/topic/12597/having-a-problem-with-a-dreamcast-disc/)
    and download Sarami's DiscImageCreator tool.
  - If you're using CD Tool (METHOD C) to dump GD-ROMs and are using a
    Mediatek Lite-On drive, then you will need to remove the cover to
    hotswap the disc and you will have to select Main+Sub+C2 instead of
    Main+C2+Sub (default value). Otherwise, CDTool will wrongly
    interchange the C2 and sub files.
  - If you're having problems with STARTSTOP.exe or the Audio Trap Disc,
    see this [forum
    discussion](http://forum.redump.org/topic/9872/starstopexe-problems/).

## Supported Drives

Drives that have been reported as COMPATIBLE (tested and verified).

  - **Lite-On LH-18A1H** (themabus)
  - **Lite-On SOHD-167T** (iR0b0t, Jackal, olofolleola4)
  - **Plextor PX-W4824TA** (pablogm123)
  - **Plextor PX-W4824TU** (pablogm123)
  - **Samsung TSSTCorp SH-D162C** (tossEAC)
  - **Samsung TSSTCorp SH-D162D** (iR0b0t, Jackal, tossEAC, r09,
    Rocknroms, nrl_quaker)

## Reported Drives

Drives that have been reported as COMPATIBLE (unverified):

  - LG GCR-8522B
  - Lite-On LTD-165H
  - Lite-On SOHD-16P9S
  - NEC CDR-1901A
  - Plextor PX-708A (iR0b0t)
  - Plextor PX-755SA
  - Samsung TSSTCorp TS-H192C
  - Samsung TSSTCorp TS-H352C
  - Samsung TSSTCorp TS-H353A
  - Samsung TSSTCorp TS-H353B

## Unsupported Drives

Drives that have been verified as being INCOMPATIBLE:

  - ASUS CRW-5224A (axisleon)
  - ASUS DRW-24B1ST a (Enker)
  - LG BD-RE GGW-H20L (Teancum)
  - LG CED-8120B (iR0b0t)
  - LG GCC4482B (Enker)
  - LG GDR-8164B (iR0b0t, Rocknroms)
  - LG GSA-H10N (Enker)
  - LG GSA-H42L (iR0b0t)
  - Lite-On iHAS324-32 B (axisleon)
  - Lite-On iHBS112 2 (Enker)
  - Lite-On iHBS212 2 (MrTikki)
  - Lite-On iHDP118 4 (Enker)
  - Pioneer DVR-103 (iR0b0t)
  - Pioneer DVD-129P (axisleon)
  - Pioneer DVR-111 (axisleon)
  - Pioneer DVR-216 (axisleon)
  - Plextor PX-116A (axisleon)
  - Plextor PX-760A (iR0b0t, Rocknroms, Jackal)
  - Toshiba SD-M1502 (iR0b0t)
  - SONY CRX140S (axisleon)
  - SONY CRX230E (nrl_quaker)
  - NEC ND-4550A (nrl_quaker)
  - TEAC CD-532S (axisleon)
  - Toshiba SD-M1502 (iR0b0t)
  - TSSTcorp SH-S202J (nrl_quaker)
  - HL-DT-ST BD-RE GGW-H20L (Teancum)

## Forum

For any questions, suggestions or problems please visit the [Dreamcast
GD-ROM
dumping](http://forum.redump.org/topic/2620/dreamcast-gdrom-dumping-instructions/)
topic in the forum. If you have anything to add to the dumping method or
supported drives please share with us your findings.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")