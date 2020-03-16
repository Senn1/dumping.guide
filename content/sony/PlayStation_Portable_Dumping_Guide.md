This guide is for dumping PlayStation Portable games, alternately if
your disc has a movie partition as well follow [this
guide](PlayStation_Portable_\(with_Movie_Partition\)_Dumping_Guide "wikilink")
instead (usually just for multi-demos - or Stealth movie + WipEout Pure
demo disc). Note: Some test discs need the PSP to be resigned to dump
them UMDT-99813, [see
here](PlayStation_Portable_Test_Disc_Dumping "wikilink").

## Required Hardware

  - Sony PSP with the latest [CFW
    installed](https://revive.today/psp/cfw/).
  - Memory Stick with at least 2 GB of free space.

## First Time Setup / Tools

  - [PSP Filer v6.6](https://archive.org/download/filer6.6/filer6.6.zip)
  - Start dump and upon finish move image from root folder ms0:/ISO to
    computer
  - [SFOInfo](https://archive.org/download/SFOInfo/SFOInfo.7z) to
    extract info
  - [Hashcalc](http://www.slavasoft.com/hashcalc/) (or another program
    that can calculate CRC32/MD5/SHA1 of a file)
  - [IsoBuster](https://www.isobuster.com/download.php) for PVD data
    (free version is fine)
  - **Note: Please do not use USBSSS — it makes bad dumps\!**

### Installing PSP Filer onto your PSP

1.  Extract the PSP Filer ZIP file
2.  Open the 'release\\GAME' folder, select the 'Filer' folder and
    'copy' it
3.  Connect the PSP to the computer using a USB Cable
4.  Open your memory stick, then open the 'PSP\\Game' folder and select
    paste
5.  Disconnect the PSP from the computer.

## Dumping a UMD using PSP Filer

1.  Enable your PSP to run homebrew / start your Custom Firmware.
2.  Insert the UMD you want to dump into your PSP.
3.  Select Game \> Memory Stick \> PSP Filer and start it.
4.  When PSP Filer starts, Press the Triangle button to open a menu.
5.  Press the 'Right Trigger' button to select 'UMD Ripping'.
6.  Make a note of the filename the UMD will be dumped to. (Example:
    ULES-00135.iso)
7.  Press the 'Start' button to start dumping.
8.  Wait while the UMD dumps to your Memory stick. This can take a
    while, it depends on the size of the game.
9.  When completed, Press the Cross button then exit 'PSP filer' using
    the Home button then Quit game.

## Transferring the dumped ISO file to your computer

1.  Connect the PSP to your computer using a USB Cable
2.  Open your Memory Stick then open the ISO folder.
3.  Copy/Cut the Dumped ISO from your memory stick to a folder on your
    computer.
4.  Disconnect the PSP from the computer.

## Retrieving PVD

  - Open IsoBuster app.
  - File \> Open Image File.
  - In the left hand side of the app, right click on "Session 1" \>
    Sector View.
  - In the box at the top input "16".
  - Scoll down and highlight lines 0320 - 0370 \> click on the
    notepad-looking icon (when your mouse hovers over it, it says
    "Copy").
  - Paste this info into your submission, it's the "PVD" info. Here's an
    example of how it should look:

`0320 : 20 20 20 20 20 20 20 20  20 20 20 20 20 32 30 30                200`
`0330 : 38 30 32 31 32 30 30 30  30 30 30 30 30 24 30 30   8021200000000$00`
`0340 : 30 30 30 30 30 30 30 30  30 30 30 30 30 30 00 30   00000000000000.0`
`0350 : 30 30 30 30 30 30 30 30  30 30 30 30 30 30 30 00   000000000000000.`
`0360 : 30 30 30 30 30 30 30 30  30 30 30 30 30 30 30 30   0000000000000000`
`0370 : 00 02 00 55 4C 55 53 2D  31 30 33 33 39 7C 31 39   ...ULUS-10339|19`

## Collecting the necessary info and submitting the dump

1\. Extract SFOInfo from the ZIP file and place it in the folder as your
Dumped ISO.

2\. Mount the ISO image file with Daemon Tools or whatever you use
normally to mount disc images on a virtual drive.

2\. Get the virtual drive letter and use this command "**sfoinfo s f:\\
d:\\PSP\\myinfo.txt**" where f:\\ is the virtual drive and
d:\\PSP\\myinfo.txt is the drive folder where you need to extract the
data. Change the letters according to your computer configuration, and
if you want you can prepare a small batch file so you don't need to open
the command prompt every time.

3\. Run Hashcalc, press the '...' button and browse for the ISO file
that your dumped.

4\. Tick the MD5, SHA-1 and CRC32 boxes then click 'calculate'

5\. Open the text file that got created in step 2.

6\. Copy the template data below and paste at the top of the text file.

7\. Replace the data in <Angled Brackets> with the data from your dump
and save when done.

`--- Template Start ---`
`General Info:`
`Game Name:    <Name of the Game that you dumped>`
`Dumping PSP:  <PSP Type and Firmware Version, E.g 'PSP-1000, 6.20 PRO-B7'>`
`Dumping Tool: <Program used to Dump. E.g 'PSP Filer 6.6'>`
`Filesize:     <Go to Properties of ISO and copy 'size' NOT 'size on disk' e.g '756 MB (793,280,512 bytes)'>`
`Barcode:      <The barcode on the back of box (usually in the bottom right corner)>`
`Edition:      <What Edition of the game is it? Original?, Demo?, Special Edition?>`
`Languages:    <What languages is this game in?, e.g 'English, French, German, Italian, Spanish'>`
`Ring Codes:   <Found on the data side near the center hub, some games may only have one ring code>`
`- Outer Ring Mastering Code (laser branded/etched): <code>`
`- Outer Ring Mastering SID Code: <code>`
`- Outer Ring Toolstamp (engraved/stamped): <code>`
`- Inner Ring Mastering Code (laser branded/etched): <code>`
`- Inner Ring Mastering SID Code: <code>`
`- Inner Ring Toolstamp (engraved/stamped): <code>`
`- Mould SID Code: <code> (not all the discs have it, it's really small and it can be hard to see)`
`  `
`HashCalc Info:`
`MD5:   <Paste the MD5 of your ISO from Hashcalc here>`
`SHA1:  <Paste the SHA1 of your ISO from Hashcalc here>`
`CRC32: <Paste the CRC32 of your ISO from Hashcalc here>`
` --- Template End ---`
`Note: Your SFOInfo data should be here.`

8\. Go to [Dumps](http://forum.redump.org/forum/11/dumps/) section of
the Redump forum, Click 'Post New Topic'

  - In 'Topic Subject' type in: "\[PSP\] <Name of Game> (Region)"
  - E.g "\[PSP\] Ghost in the Shell - Stand Alone Complex (Europe)"
  - In the 'Write Message' box, paste the info from the text file.

9\. Check that you have posted all the required information:

  - General Info
  - Hashcalc Info
  - SFO Info

10\. Press the 'Submit' button ONCE and wait for the information to be
submitted.

Example of a Complete Dump Info:

`General Info:`
`Game Name:    Ghost in the Shell - Stand Alone Complex`
`Dumping PSP:  PSP-1000, 6.20 PRO-B7`
`Dumping Tool: PSP Filer 6.6`
`Filesize:     756 MB (793,280,512 bytes)`
`Barcode:      3 296580 802487`
`Edition:      Original`
`Languages:    English, French, German, Italian, Spanish`
`Ring Codes:   `
`- Outer Ring Mastering Code (laser branded/etched): Sony DADC A0100633844-A511 17 `
`- Outer Ring Mastering SID Code: IFPI L557`
`- Outer Ring Toolstamp (engraved/stamped): A1`
`- Inner Ring Mastering Code (laser branded/etched): Sony DADC A0600666666-B511 96 `
`- Inner Ring Mastering SID Code: IFPI L556`
`- Inner Ring Toolstamp (engraved/stamped): C10`
`- Mould SID Code: IFPI 942X`
`  `
`HashCalc Info:`
`MD5:   e52a046153932917584007e415405dc2`
`SHA1:  7aed3fa5538c53b79a38ef21aac9d01cd506c557`
`CRC32: a7190995`
`  `
`  `
`SFO file: ULES-00135\PSP_GAME\PARAM.SFO`
`SFO Version: 1.1`
`BOOTABLE: 1`
`CATEGORY: UG `
`DISC_ID: ULES00135 `
`DISC_NUMBER: 1`
`DISC_TOTAL: 1`
`DISC_VERSION: 1.00 `
`PARENTAL_LEVEL: 5`
`PSP_SYSTEM_VER: 1.52 `
`REGION: 32768`
`TITLE: GHOST IN THE SHELL STAND ALONE COMPLEX `
`  `
`SFO file: ULES-00135\PSP_GAME\SYSDIR\UPDATE\PARAM.SFO`
`SFO Version: 1.1`
`BOOTABLE: 1`
`CATEGORY: MG `
`DISC_ID: MSTKUPDATE `
`DISC_VERSION: 1.00 `
`PARENTAL_LEVEL: 1`
`REGION: 32768`
`TITLE: PSP™ Update ver 2.00 `
`TITLE_0: PSP™ アップデート ver 2.00 `
`TITLE_2: Mise à jour PSP™ ver. 2.00 `
`TITLE_3: Actualización de PSP™ ver. 2.00 `
`TITLE_4: PSP™-Aktualisierung Ver. 2.00 `
`TITLE_5: Aggiornamento della PSP™ ver. 2.00 `
`TITLE_6: PSP™-update versie 2.00 `
`TITLE_7: Actualização PSP™ ver 2.00 `
`TITLE_8: Обновление PSP™ вер. 2.00 `
`TITLE_9: PSP™ 업데이트 버전 2.00 `
`UPDATER_VER: 2.00 `

-----

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")