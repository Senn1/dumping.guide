<div class="textblock" style="background: #febaba; padding: 10px;">

<span style="font-size: 18px; font-weight: bold;">This is an OLD
deprecated guide for reference only. </span>

</div>

For the current dumping guide see: [Disc Dumping Guide
(DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").

## Introduction

This guide will explain how to preserve CD-based games in the best
possible way. It is a general purpose guide meant for all systems that
use CD media (consoles or computers) and for most CD variants (data cds,
audio cds, mixed cds). Also the discs must be unprotected and must not
have any kind of abnormalities (eg audio pregaps marked as data). Please
refer to more specific guides on how to dump protected and non-standard
cds.

Software needed:

  - IsoBuster
  - ExactAudioCopy V0.99 Prebeta 5
  - Resize
  - psxt001z (PSX only)

## Determining Disc Type

### Mixed-Mode CDs

Before we dump the disc, we need to know if it contains any audio
tracks. Insert the disc into the drive and launch IsoBuster. A disc with
audio tracks will look as follows (notice how the audio track icon
differs from the data track one): \[dead image\]

A disc with audio tracks will unfortunately take a bit longer to dump,
because audio tracks require a different treatment than data tracks.

### Copy Protected CDs

If you are dumping a PC game you will need to scan executables and DLLs
for protection. Use the following tools: BurnOut or ProtectionID. If a
protection is detected, refer to the protection specific Dumping Guides.

## Ripping the Data Track

### Ripping the data track using IsoBuster

  - Start IsoBuster;
  - Insert the disc (If you have multiple drives with cd's inserted,
    make sure you select the right one);
  - Right mouse button on Track 01 → Extract Track 01 → Extract RAW Data
    (2352 bytes/block) (\*.bin, \*.iso);
  - Choose a destination folder.

The data will now be extracted. If you get “Unreadable sector” errors at
the end of the track (this is common for discs with audio tracks), pick
the option “Replace with User Data All zeroes” for all unreadable
sectors. \[dead image\]

Errors should only occur at the very end of the track (99%-100%
extraction). If the error occurs earlier, make sure that the disc is
free of scratches. After extraction, if it asks if you want to delete
the file, choose “No”. \[dead image\]

When the extraction is complete, you will have an image file of the data
track. If the disc contains audio tracks, go to the next part. If the
disc only contains a data track, head on to the Final steps part.

### Fixing the Pregap

If the disc has audio tracks, we will have to do some more steps to get
the data track down to the right size. Because IsoBuster is unable to
detect where the audio track starts, it will add a part from the first
audio track to the end of the data track.

In order to remove the required amount of bytes from the end of the
track, it is necessary to determine the length of the Track02 pregap.
This can be done using Exact Audio Copy (this is also the tool that's we
will use to extract the audio tracks).

### Determining Pregap Length

  - Insert the CD you want to rip (make sure the disc has a clean
    surface);
  - Press F4 (or select Action → Detect Gaps);
  - EAC will now detect gaps between the tracks.

\[dead image\]

You can see that in this picture, EAC detected a Track02 pregap of 4
seconds. In most cases the pregap will be 2 seconds. Each second of
audio data equals 176400 bytes, so a pregap of 2 seconds is 2\*176400 =
352800 bytes. Each second also equals 75 sectors, so a pregap of 2
seconds is 150 sectors. A pregap of 1.74 seconds 149 sectors. Now that
you know the Track02 pregap length, go to the next step.

### Removing the pregap using Resize

To remove the Track02 pregap from Track 01, we will use a tool called
'Resize'. To use this tool, download it and extract it in the same
folder as the 'Track 01.bin' file. Resize.com requires you to work in
Command Prompt. If EAC reported a pregap of 2 seconds = 352800 bytes and
the filename of the image is 'Track 01.bin', the command would be as
follows:

RESIZE -r -352800 "Track 01.bin"

\[dead image\]\]

When the correct amount of bytes is removed from the end of the image,
you can go to the next step. For PSX discs, this is 'Checking and
repairing the postgap'. For other discs, it's 'Ripping the audio
tracks'.

## Ripping Audio Tracks

### Determining the (factory) write offset

**Note**: Plextor users can skip this section and use a different
(faster, easier and more flexible) method instead. To determine the
factory write offset value we will use IsoBuster to browse to the
relevant cd sector:

  - Insert the CD you want to rip (make sure the disc is clean);
  - Start IsoBuster;
  - Make sure that the correct CD Reader is selected;
  - In the track list in the left column, click on Track 02 with right
    mouse button and select 'Sector View';
  - Make sure that the 'RAW' checkbox is enabled;
  - If the Track02 pregap was 2 seconds, or 150 sectors, first go back
    (pregap -1) sectors = 149 sectors (substract 149 from from the
    number in the white box);
  - Now use the arrow to go back one more sector (if you go back 150
    right away there's a chance the data won't show). If everything is
    alright, your screen will look similar to this:

\[dead image\]

Now you should get a number of rows that show (scrambled) binary data,
followed by rows of zeroes. It is also possible that the last row of
data is not filled completely, but is partly zeroed. Each row is 16
bytes, so if we have 8 full rows (like in the screenshot above) that are
filled with data (and not just zeroes) this means we have 8\*16 = 128
bytes. The amount of data in bytes has to be divided by 4 to get the
amount of samples, so in our screenshot it's 128 bytes of data /4 = 32
samples. This is the offset value that we will use in EAC for ripping
the audio tracks.

Note 1: It can happen that the sector shows no data at all, but only
zeroes. If you are 100% sure that you are reading the correct sector and
it shows no scrambled data (and going forth and back one sector also
doesn't help), it's best to retry the audio ripping part using a
different drive, but this time try using a drive with a bigger read
offset (see list of read offsets for each drive). To be able to detect
all offsets, most dumpers in our project bought a cheap CDRW drive with
a large read offset, such as the Sony CRX-100E or 120E.

Note 2: It is also possible that the sector is full of data. A full
sector contains 2352 bytes of data. If the first sector is full of data,
browse on to the next sector(s) and make sure all data is counted until
you reach the end of the data (start of zeroes).

Now we will change the offset value in EAC to the one that we just
determined. Before we do that, we will first calculate the factory write
offset. The offset value that we just retreived from the sector and that
is used in EAC to dump the audio tracks is the combined read+write
offset. However, for documenting purposes we need you to supply us the
write offset value alone, so the read offset value needs to be
substracted from the combined offset value.

In order to do this we will need the Read offset value of your drive
(detected in EAC or taken from the accuraterip drive list). Once you
know this value, it's possible to calculate the factory write offset
value. For example, if reading the sector gives you +32 samples (or 128
bytes (=8 rows) of data) and the read from the Accuraterip database is
+30, then the factory write offset is: +32 = (?? + 30) \> ?? = +2.

Now we are finally ready to change the offset value in EAC and start
dumping the audio tracks. Please make sure that you use the offset value
that was calculated using the amount of data in the sector for EAC and
not the factory write offset value\!

### Changing the offset in EAC

Start EAC and change the offset to the proper value:

  - Open the drive options (EAC → Drive Options or press F10);
  - Change to the “Offset / Speed” tab and change the value in the 'Read
    sample offset correction value' to the new value. A value of 32
    samples (amount of data in the sector) earlier means entering '+32'
    in EAC;
  - The value should always be positive or EAC may cut off data\!
    Therefore tracks should always be dumped on the drives that show
    data in the previous step\!

\[dead image\]

### Checking overreading data (Audio CDs)

Because it is not possible to determine write offset in redbook audio
cds, they are usually dumped by using the drive offset alone. However it
they might still contain data that could be skipped.

In Isobuster right click in the last audio track and select "sector
view". Now in the sector adress type the last sector of the cd. You can
find it by hovering your mouse over the last track. Click the arrow and
go +1 sector and check if there is data or all 00s. Try to go further
sectors to be sure. Note that your drive must be able to overread or it
must have a large possitive offset.

If there is data you must correctly calculate the (assumed write) offset
that will be used to dump the tracks and do not use the drive's read
offset in this case. See the above guide on how to do this Determining
the (factory) write offset.

Now we're finally ready to start ripping the audio tracks.

### Ripping audio tracks with EAC

  - Insert the CD you want to rip (make sure the disc has a clean
    surface);
  - Press F4 (or select Action → Detect Gaps);
  - EAC will now detect gaps between the tracks;
  - If you think the gaps that you're getting are strange, clean the
    disc and try again;
  - Select Action → Append gaps to next track;
  - Select the tracks you want to rip;
  - Press Shift + F6 (or select Action → Test & Copy selected tracks →
    compressed from the menu);
  - Select a directory to rip the files to and press ok;
  - EAC will now start ripping the selected tracks. When the extraction
    is complete, a 'Status and Error Messages' window will appear;
  - Be sure to click the 'Create Log', as this .log file is mandatory
    information\!;
  - When ripping is done, the Read and Write CRC columns should contain
    equal CRC numbers\!;
  - After extracting, create a cuesheet. Do this by selecting Action →
    Create CUESheet → Current Gap Settings.

Now we are almost ready. Head on to the Final steps.

### Final Steps

After dumping, you will end up with the following files:

  - Data track and audio track binaries, properly dumped using the
    guide;
  - Cuesheets and .log file(s) created by EAC (only for games with audio
    tracks).

You can now help our project by supplying us with the information about
the dump. The information that we need is specified in the next
paragraph. If you need any additional help, contact details can be found
on this site in the 'Site' menu. Feel free to idle or ask for any help
in our IRC channel: ForeverChat \#redump.

## Mandatory Information

  - Game title (Including subtitle);
  - Disc titles (Only if the game consists of multiple discs and if the
    titles on the discs are different, or if it's a compilation and
    every disc is a seperate game);
  - Disc ID / Serial (not for IBM discs) (E.g. “SLUS-12345”);
  - EXE date in YY-MM-DD format (not for IBM discs) (Date of EXE file,
    e.g. “SLUS_123.45” (or any other file which's name is located in
    SYSTEM.CNF file). Date should be looked in IsoBuster, but be sure to
    turn on option “Options → File System Setting → General → Time
    Stamps → Display time stamp → Local time stamp”);
  - Game languages;
  - LibCrypt output (PSX only) (use this guide for LibCrypt protection
    checking);
  - Size, CRC-32, MD5 and SHA-1 checksums of all tracks (All track
    should be dumped twice to make sure they were dumped correctly\!
    Checksums you can get using HashCalc, DAMN Hash Calculator or
    ClrMamePro, and size using Windows Explorer/Total Commander/FAR, but
    not IsoBuster\!);
  - Factory write offset value.
  - EAC cue sheet for multi-track discs. Some cue sheets might also
    contain flags.
  - EAC Log file.
  - For PC protected discs scan for errors with cdmage and report the
    error number. If the erroneous sectors go beyond 10500 sector or so,
    please submit either a clonecd log or cdmage log.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")