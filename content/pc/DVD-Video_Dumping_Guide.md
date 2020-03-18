---
title: "DVD Video"
---

<div class="textblock" style="background: #febaba; padding: 10px;">

<span style="font-size: 18px; font-weight: bold;">This is an OLD
deprecated guide for reference only. </span>

</div>

For the current dumping guide see: [Disc Dumping Guide
(DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").

How to dump a DVD-Video disc using standard DVD copy protection.

## Dumping

### DVD Decryptor

[Download DVD
Decrypter](https://archive.org/download/SetupDVDDecrypter3.5.4.0/SetupDVDDecrypter_3.5.4.0.exe)

  - Start DVD Decryptor
  - Check the log window for the RCE protection type and make note of it
    for submission info, or take a screenshot and include it in the
    submission info.
  - Close DVD Decryptor

### ISO Buster

Download the free version of [ISO
Buster](https://www.isobuster.com/download.php).

  - Open up IsoBuster \> Track 01 \> Extract User Data. This will create
    a dump of your DVD-Video.
  - Right click on Track 1 \> Sector View \> type "16" in at the top,
    then copy + paste all text into a .txt document to submit with your
    logs. The PVD data from 0320 - 0370 (full six rows) are the
    pertinent info.

## Retrieving Decryption Keys

[Download QPxTool](https://archive.org/download/QPxTool/QPxTool.7z) and
unzip.

  - Open your Command Prompt and cd to the location of your unzipped
    folder, for example: "C:\\Users\\\[YOUR COMPUTER USER NAME
    HERE\]\\Downloads\\QPxTool"
  - Run **readdvd.exe -d D: -o NUL** (note "D:" is the drive letter with
    the DVD, change accordingly).
  - Press Q to stop reading and then copy the three keys from the
    command window (decrypting disc key, trying player key, decrypted
    disc key).

## Submitting your Dumps

Time to have your disc added to redump's database\! If it is your first
submission, do so via the forum. [Forum sign-up
here](http://forum.redump.org/topic/12228/want-to-register-please-read-first/).
Forum disc info submission
[here](http://forum.redump.org/forum/11/dumps/).

### Info from DVD Decrypter's log window

  - **Region**: \#,\#,etc.
  - **RCE Protection**: No or Yes
  - **Copyright Protection System Type**: CSS/CPPM

### Info from QPxTool

  - **Encrypted Disc Key**:
  - **Player Key**:
  - **Decrypted Disc Key**:

### General Info

  - **Movie title**: Most obvious, is located everywhere. Please include
    subtitle.
  - **Languages**:
  - **Bundled?**: Is this a bonus disc bundled with a game? If so which
    one?
  - **Barcode**: Submit the numbers from the barcode:
    [EAN](http://en.wikipedia.org/wiki/European_Article_Number) /
    [UPC](http://en.wikipedia.org/wiki/Universal_Product_Code) code,
    usually printed on the back cover of the packaging or disc case.
  - **Serial number**: If one exists.
  - **Media**: If the DVD is greater than 4.7 GB and up to 8.5 GB, the
    DVD is DVD-9. Otherwise most of the time, it is DVD-5.
  - **Ring code info**: stamped on the inner ring. Check both sides for
    any ringcodes (small stamps may require magnifying glass to see).
    Report whatever ring codes are readable.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")