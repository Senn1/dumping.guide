This is a step-by-step guide designed to be easy to follow so that you
can make reproducible, good dumps of your GD-ROMs to the Redump
standard. We have been unsuccessful getting GD-R's to dump with the
redump method, further testing may be required.

Note: Some GD-Roms will NOT dump with this method, and require a
TOSEC-style SD Card dump for the HD area which then has to be "fixed" to
meet redump spec. If the game is a single track in the HD area, then the
TOSEC-style dump will be equal a redump dump for HD area, LD area still
needs Plextor dumping. See [GD-Rom SD Card Dumping
Guide](GD-Rom_SD_Card_Dumping_Guide "wikilink").

**NOTE: A work in progress video dumping tutorial guide is available
[here](https://www.youtube.com/playlist?list=PLQB0cW1F4d0umPPY-vU1BHhjH1iyry2Yd).**

## What are GDs?

GDs (Gigadiscs) are the type of [optical
media](wikipedia:Optical_disc "wikilink") used by the [Sega
Dreamcast](wikipedia:Dreamcast "wikilink") as well as the [Sega
NAOMI](https://segaretro.org/Sega_NAOMI), [Sega
NAOMI 2](https://segaretro.org/Sega_NAOMI_2), [Sega
Chihiro](https://segaretro.org/Sega_Chihiro) and
[Triforce](https://segaretro.org/Triforce) arcade systems. The disc
contains two distinct areas, a Low Density (LD) Area and a High Density
(HD) Area, physically separated by a ring. To get a good dump, you need
to extract both Areas from the disc.

If you have any of the officially released discs for the Dreamcast or
any of the above mentioned arcade systems, you are pretty much
guaranteed to have a GD. The Dreamcast did however support loading of
[MIL-CDs](wikipedia:MIL-CD "wikilink"), which lead to a number of
unlicensed software being pressed on regular CD-Roms. Check for the
GD-ROM logo on the disc or check the reflective side of the disc for a
visible LD/HD Area divide if you are unsure.

## Tools

First you need to make sure you have the necessary equipment. To dump a
GD you need:

  - Windows PC
  - [Compatible
    drive(s)](DiscImageCreator:_Optical_Disc_Drive_Compatibility#GD-Rom "wikilink")
  - [DICUI app](https://github.com/reignstumble/DICUI/releases/latest)
  - Download [VGPC GD-Rom Dumping
    Kit](https://archive.org/download/VGPCGDRomDumpingKit_201811/VGPC%20GD-Rom%20Dumping%20Kit.7z)
    (audio trap disc image, dcdumper, ice, startstop)
  - CD-R to create an Audio Trap Disc.

## Burning an Audio Trap Disc

You'll need an Audio Trap Disc for the HD Area dumping process as it
tricks your drive into reading into that part of the disc.

The Audio Trap Disc image is included with the VGPC GD-Rom Dumping Kit.
Because the image intentionally has errors, many programs won’t burn it
properly. We’ve found that
[CloneCD](https://www.redfox.bz/en/clonecd.html) (free trial) can
reliably burn it properly:

  - Open CloneCD and click on "Write from ImageFile".
  - Click on "Browse" and navigate to where you extracted the VGPC
    GD-Rom Dumping Kit, and select "TOC122A.CCD".
  - Then, select the drive with the blank CD-R inside. Click on the
    "Protected PC Game" profile. The write speed shouldn't matter much
    since this is such a small image, but 8x speed recommended.

## Dumping the LD Area

The LD Area should be dumped with DICUI using this guide: [Disc Dumping
Guide (DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").

The LD Area is a standard CD-Rom, so it will be the only data to appear
when mounted in a computer.

## Dumping the HD Area

To dump the HD Area of the GD-Rom, the swap disc method is used. To do
this you will have to remove the four bottom screws of your drive and
faceplate. Afterwards, set the top back onto the drive. It will be
removed after the startstop step. Note: Refer to video guide at the top
of this page if you're confused.

  - Insert the audio Trap Disc to an HD Area [compatible
    drive](DiscImageCreator:_Optical_Disc_Drive_Compatibility#GD-Rom "wikilink").
  - In command line, **cd** (change directory) to the "VGPC GD-Rom
    Dumping Kit" folder.
  - Run **startstop \[driveletter\] 1**
  - Remove the top off the drive.
  - Insert the GD-Rom and put the drive top back on.
  - Run **dcdumper \[drive letter\] -c446261 -df -ft -t0 -p20**
  - It will take several "PASS"es to get all matches, this is fine. If
    you need to stop (sometimes there is no progress for 30mins) and
    restart the dumping process, it will continue where it left off - so
    don't delete progress if you have to stop it.

If dcdumper fails to run with an error complaining about MSVCP100.DLL
being missing, install the Microsoft Visual C++ 2010 Redistributable
Package (x86) to fix this issue.

## Converting HD Area dump Sections to Tracks

When the HD Area dump completes, you'll convert it to it's final form.

Run **ice.exe dense.bin 44990 \> gamename.txt** This will produce a
bunch of files starting with "Track 03" and going as high as however
many “tracks” were on the HD section of the disc (sometimes there will
only be one, sometimes it will go up to Track 98).

## Submitting your dump info

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")