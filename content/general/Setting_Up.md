---
title: "Setting Up"
---

Before we start dumping we must first setup our tools properly.

## IsoBuster

  - Open *Options → File system settings*.
  - In *Display Time Stamp* options group select *Local time stamp*
    option.

## CloneCD

Create a new .TXT file and copy/paste the following information into the
file (remove the preceding tabs). Rename the file as "redump.cpp" and
move it into CloneCD's profile folder (e.g. C:\\Program Files
(x86)\\SlySoft\\CloneCD\\Profiles):

  - \[CloneCD ReadPrefs\]
  - ReadSubData=1
  - RegenerateData=0
  - ReadSubAudio=1
  - AbortOnReadError=0
  - FastErrorSkip=0
  - ReadSpeedData=8
  - ReadSpeedAudio=8
  - IntelligentBadSectorScan=1
  - SectorSkip=1
  - NoErrorReport=0
  - FirstSessionOnly=0
  - AudioQuality=3

**NOTE 1:** Plextor drives can set "FastErrorSkip=1" or if you know your
drive supports it.

**NOTE 2:** Setting the Data/Audio ReadSpeeds at speeds lower than 8x
can cause permanent damage to modern drives. Do so at your own risk\!

**NOTE 3:** Only enable “overread into lead-in and lead-out” if your
drive actually supports that. EAC itself has a function to test that in
the same tab.

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")