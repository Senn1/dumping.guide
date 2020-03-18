---
title: "CD without Audio Tracks (old)"
---

<div class="textblock" style="background: #febaba; padding: 10px;">

<span style="font-size: 18px; font-weight: bold;">This is an OLD
deprecated guide for reference only. </span>

</div>

For the current dumping guide see: [Disc Dumping Guide
(DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").

## Introduction

This guide will explain how to preserve CD-based games in the best
possible way. It is a general purpose guide meant for all systems that
use CD media (consoles or computers) and for most CD variants WITHOUT
Redbook Audio Tracks. Also the discs must not have protection (such as
PC games using SafeDisc etc).

Software needed:

  - [IsoBuster](https://www.isobuster.com/): Click "Download", it will
    download the free version.
  - psxt001z (PSX only) - skip for now

## Determining Disc Type

Before we dump the disc, we need to know if it contains any audio
tracks. Insert the disc into the drive and launch IsoBuster. A disc with
just a data track will only say "Track 1" on the left pane, but a disc
with audio tracks will have multiple tracks ("Track 2" and maybe more).

If your disc has audio tracks, please see [CD Dumping Guide with Audio
Tracks (Old)](CD_Dumping_Guide_with_Audio_Tracks_\(Old\) "wikilink").

## Ripping the Data Track

  - Insert the CD you want to rip (make sure the disc has a clean
    surface).

### Ripping the data track using IsoBuster

  - Start IsoBuster
  - Insert the disc (If you have multiple drives with cd's inserted,
    make sure you select the right one)
  - Right mouse button on Track 01 → Extract Track 01 → Extract RAW Data
    (2352 bytes/block) (\*.bin, \*.iso)
  - Choose a destination folder.

The data will now be extracted. If you get “Unreadable sector” errors at
the end of the track (this is common for discs with audio tracks), pick
the option “Replace with User Data All zeroes” for all unreadable
sectors.

Errors should only occur at the very end of the track (99%-100%
extraction). If the error occurs earlier, make sure that the disc is
free of scratches. After extraction, if it asks if you want to delete
the file, choose "No".

When the extraction is complete, you will have a perfect disc image
(.bin file).

## Mandatory Information

Submit the following info here
[1](http://forum.redump.org/forum/11/dumps/).

  - Game title (Including subtitle)
  - Please post this in your submission post: "The disc is a single data
    track, I don't have a Plextor, I used this dumping guide
    <http://wiki.redump.org/index.php?title=CD_Dumping_Guide_without_Audio_Tracks_(Old)>"
  - Disc ID / Serial: For example, with PlayStation 1 discs:
    "SLUS-12345"
  - EXE date in YY-MM-DD format (not for IBM discs) (Date of EXE file,
    e.g. “SLUS_123.45” (or any other file which's name is located in
    SYSTEM.CNF file). Date should be looked in IsoBuster, but be sure to
    turn on option "Options → File System Setting → General → Time
    Stamps → Display time stamp → Local time stamp").
  - Game languages.
  - LibCrypt output (PSX only) - ignore for JAPAN and USA
  - Size, CRC-32, MD5 and SHA-1 checksums of all tracks (All track
    should be dumped twice to make sure they were dumped correctly\!
    Checksums you can get using
    [HashCalc](http://www.slavasoft.com/zip/hashcalc.zip) or CLR Mame
    Pro.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")