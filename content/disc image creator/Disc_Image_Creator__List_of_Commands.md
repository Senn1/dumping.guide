## Usage

`       cd `<DriveLetter>` `<Filename>` <DriveSpeed(0-72)> [/q] [/a (val)]`
`          [/be (str) or /d8] [/c2 (val1) (val2) (val3)] [/f] [/m] [/p]`
`          [/raw] [/sf (val)] [/ss] [/np] [/nq] [/nr] [/ns] [/s (val)]`
`               Ripping a CD from A to Z`
`               For PLEXTOR or drive that can scramble ripping`
`       data `<DriveLetter>` `<Filename>` <DriveSpeed(0-72)> `<StartLBA>` <EndLBA+1>`
`            [/q] [/be (str) or /d8] [/c2 (val1) (val2) (val3)] [/sf (val)]`
`            [/ss] [/r] [/np] [/nq] [/nr] [/ns] [/s (val)]`
`               Ripping a CD from start to end (using 'all' flag)`
`               For no PLEXTOR or drive that can't scramble ripping`
`       audio `<DriveLetter>` `<Filename>` <DriveSpeed(0-72)> `<StartLBA>` <EndLBA+1>`
`             [/q] [/a (val)] [/be (str) or /d8] [/c2 (val1) (val2) (val3)]`
`             [/sf (val)] [/np] [/nq] [/nr] [/ns] [/s (val)]`
`               Ripping a CD from start to end (using 'cdda' flag)`
`               For dumping a lead-in, lead-out mainly`
`       gd `<DriveLetter>` `<Filename>` <DriveSpeed(0-72)> [/q] [/be (str) or /d8]`
`          [/c2 (val1) (val2) (val3)] [/np] [/nq] [/nr] [/ns] [/s (val)]`
`               Ripping a HD area of GD from A to Z`
`       dvd `<DriveLetter>` `<Filename>` <DriveSpeed(0-16)> [/c] [/f] [/q]`
`               Ripping a DVD from A to Z`
`       fd `<DriveLetter>` `<Filename>
`               Ripping a floppy disk`
`       stop `<DriveLetter>
`               Spin off the disc`
`       start `<DriveLetter>
`               Spin up the disc`
`       eject `<DriveLetter>
`               Eject the tray`
`       close `<DriveLetter>
`               Close the tray`
`       reset `<DriveLetter>
`               Reset the drive (Only PLEXTOR)`
`       sub `<Subfile>
`               Parse CloneCD sub file and output to readable format`

## Option (generic)

`       /f      Use 'Force Unit Access' flag to defeat the cache (very slow)`
`       /q      Disable beep`

## Option (for CD read mode)

`       /a      Add CD offset manually (Only Audio CD)`
`                       val     samples value`
`       /be     Use 0xbe as the opcode for Reading CD forcibly`
`                       str      raw: sub channel mode is raw (default)`
`                               pack: sub channel mode is pack`
`       /d8     Use 0xd8 as the opcode for Reading CD forcibly`
`       /c2     Continue reading CD to recover C2 error existing sector`
`                       val1    value to reread (default: 1024)`
`                       val2    value to fix a C2 error (default: 4096)`
`                       val3    value to reread speed (default: 4)`
`       /m      Use if MCN exists in the first pregap sector of the track`
`                       For some PC-Engine`
`       /p      Ripping AMSF from 00:00:00 to 00:01:74`
`                       For SagaFrontier Original Sound Track (Disc 3) etc.`
`                       Support drive: PLEXTOR PX-W5224, PREMIUM, PREMIUM2`
`                                      PX-704, 708, 712, 714, 716, 755, 760`
`       /r      Read CD from the reverse`
`                       For Alpha-Disc, Tages (very slow)`
`       /raw    Read the lead-out of 1st session and the lead-in of 2nd session`
`                       For Multi-session`
`       /sf     Scan file to detect protect. If reading error exists,`
`               continue reading and ignore c2 error on specific sector`
`                       For CodeLock, LaserLock, RingProtect, RingPROTECH`
`                            SafeDisc, SmartE, CD.IDX, ProtectCD-VOB, CDS300`
`                       val     timeout value (default: 60)`
`       /ss     Scan sector to detect protect. If reading error exists,`
`               continue reading and ignore c2 error on specific sector`
`                       For ProtectCD-VOB`

## Option (for CD SubChannel)

`       /np     Not fix SubP`
`       /nq     Not fix SubQ`
`       /nr     Not fix SubRtoW`
`       /nl     Not fix SubQ (RMSF, AMSF, CRC) (LBA 14100 - 16199)`
`                                              (LBA 42000 - 44399)`
`                       For PlayStation LibCrypt`
`       /ns     Not fix SubQ (RMSF, AMSF, CRC) (LBA 0 - 7, 5000 - 18799)`
`                                           or (LBA 30800 - 34799)`
`                                           or (LBA 40000 - 45799)`
`                       For SecuROM`
`       /s      Use if it reads subchannel precisely`
`                       val     0: no read next sub (fast, but lack precision)`
`                               1: read next sub (normal, this val is default)`
`                               2: read next & next next sub (slow, precision)`

## Option (for DVD)

`       /c      Log Copyright Management Information`

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")