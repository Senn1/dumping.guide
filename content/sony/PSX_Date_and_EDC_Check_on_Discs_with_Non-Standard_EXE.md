---
title: "PSX Discs with Non-Standard EXE"
---

Some PSX discs such as LightSpan and GameShark have irregular
executables on the disc that require an alternate way to determine Exe
Date and EDC status.

## EXE Date

1.  Open Isobuster
2.  Check the time stamps settings under Options \> File System Settings
    \> Time stamps, and make sure both settings are set to local time
    stamp (recorded time stamp)
3.  Click on the ISO icon under Track 01
4.  Right click on system.cnf and click 'Sector View'
5.  Note the filename after boot=cdrom
6.  Close Sector View
7.  Find that filename in the right side window (might be inside a
    folder)
8.  Note the date of this file (note that redump requires date in
    yyyy-mm-dd format)

## EDC Yes/No

1.  Highlight Track 01 on the left side of screen
2.  Right click and select 'Sector View'
3.  In the sector box next to the blue arrows type in '12' and check the
    RAW box
4.  If the last 4 bytes are zero then no EDC. If last 4 bytes are
    0x3F13B0BE then EDC.
5.  Repeat for sectors 13,14, and 15

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")