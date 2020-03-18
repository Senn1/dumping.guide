---
title: "Playstation 3"
---

Dumping guide for PS3 discs. For the forum discussion topic on PS3
dumping please
see[1](http://forum.redump.org/topic/12699/ps3-dumping-instructions/)[2](http://forum.redump.org/topic/7656/ps3-dumping/).
3K3Y setup video here[3](https://www.youtube.com/watch?v=DTi73XAfbkY)

Dumping on PS3 console or PC work equally well, but the 3k3y can be hard
to find for sale, so using a console may be necessary. The final method,
PC + Non-PS3/OEM drive cannot dump keys, but this information can
sometimes be tracked down later, so these dumps are accepted.

Note about dumping PS3 betas: PS3 beta (BD-R / DVD-R) should be dumpable
via standard DVD-Rom or BD-Rom drives via DICUI with the IBM-PC DVD-Rom
settings (for DVD-R betas), or PS4 settings (for BD-R betas). More
testing required to confirm.

Note about dumping PS3 kiosk discs: Kiosk discs can be CD-Rom, DVD-Rom,
or BD-Rom. For CD-Rom and DVD-Rom you should dump with [Disc Dumping
Guide (DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink"). For BD-Rom, you
can dump either with DICUI or dvdtoimg (same results). Kiosk discs have
no keys to extract.

## Dumping with a PS3 Console

### Tools

  - [Compatible](https://www.psxhax.com/threads/downgradable-ps3-models-base-firmware-with-minverchk.388/)
    PS3 console running a current CFW (can be installed over the latest
    PS3 official firmware, [instructions
    here](https://www.youtube.com/watch?v=VBlYPmnJPLs)) with 3.56 CFW or
    higher.
  - MultiMAN 04.20.00 or higher
  - [GetKey
    r2](https://archive.org/download/GetKeyR2GameOS.7z/GetKey-r2-GameOS.7z)

### Dumping ISO using MultiMAN

  - In XMMB display mode, go to multiMAN \> File Manager / mmOS.
  - In the Start Menu icon (look at the MultiMAN icon in the left botton
    of the screen and click it), select 'Enable Direct Disc Access'
    (with the game disc inserted).
  - Double-click the Games icon to switch back to XMMB display mode. In
    the multiMAN column, select 'Refresh'.
  - Now go to the Video column. It should now show a BD/DVD entry. Go to
    it, and select the 'Create ISO' option.
  - You can now copy the ISO to your preferred destination. For the best
    speeds, select the internal HDD.
  - Once it is dumped, you can use File Manager to copy/paste the ISO
    from the PS3ISO folder to your USB drive.
  - If your destination is FAT, \>4GB ISO's that are split into segments
    have to be combined again (using e.g. copy /b).

### Dumping metadata using Getkey

  - Download latest version of Rebug Toolbox from
    [4](https://rebug.me/downloads/) (reinstall if necessary).
  - Once you install the Toolbox PKG, you should be able to see the app
    installed on the XMB. Launch it. Once you are inside, move to the
    right over the options till the "Utilities" icon options displays.
    Then go down till you spot the following options:

1\. "**Dump eid root key** (dump eid root key at
dev_hdd0/game/RBGTLBOX2/USRDIR/eid_root_key)". Once you push it, the
console will create a file called "eid_root_key" on the mentioned
route. NOTE: the eid_root_key is console specific so can be reused.

Next, get a copy of the eid_root_key file:

  -   - Transfer to your computer via FTP: You can FTP into your console
        to copy the eid_root_key to your computer.
      - Transfer to your thumb drive via Console: Use MultiMAN File
        Manager or any tool to move inside the PS3 file system to get
        inside the RBGTLBOX2 folder. Make sure you have a USB drive
        connected to the PS3. Copy the Eid Root Key and paste it to the
        USB drive route (should be something like /dev_usb000).

2\. "**Export Flash to File** (Backup your current NOR/NAND flash to
/dev_usb000)". As soon as you enter the option, the system will ask you
to "Please insert a USB drive (/dev_usb000) with at least 256mb free
and try again\!". Make sure you have a USB drive (if posible, on Fat32
format) connected to the correct usb port (the right-most usb port). Try
till you hit the correct port and the dumping process will start.

  - If everything was done correctly, once you pop the USB into a
    computer you should have two files: "*eid_root_key*" and something
    like this "*20181219-130200-FLASH-NOR-FW.81*" (The FW numbers
    depends on your firmware, in my case, i did it with FW 4.81).
  - Fire up an Hex Editor app. We will use "HxD" for example
    [5](https://mh-nexus.de/en/hxd/).
  - Once HxD is launched, go to "Open" and search for your NOR/NAND dump
    file. Open it.
  - Once is loaded, hit CTRL+G and type in "303A0" if you're on NOR or
    "81BA0" if on NAND. (Note: If you didnt understand this, just write
    and search "303A0", when you start hex-editing the file, you are on
    NOR)
  - At the left column, you should see the Offsets are displayed and the
    one we were looking, 0x00303A0 (for NOR in this case), will be
    there. Copy the 0x30 bytes from that offset and paste them into a
    new file AKA mark the 0x00303A0, 0x00303B0 and 0x00303C0 lines from
    "00" to "0F" values and copy them (CTRL+C). Go to File \> New and a
    clean sheet will open. Paste (CTRL+V) the content and keep it
    opened.

*' This would be a visual example of what are you looking for. Mind you
only need to search and copy the NOR bytes or the NAND bytes, not both*'
(taken from:
<http://www.psdevwiki.com/ps3/Flash:Encrypted_Individual_Data_-_eEID>):

<table>
<thead>
<tr class="header">
<th><p>NOR: 0x00303A0 - 0x00303CF</p></th>
<th><p>NAND: 0x0081BA0 - 0x0081BCF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>Offset(h) 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

000303A0  8B D7 1B A0 C3 DA 4B BE B3 72 AE 61 78 90 31 1F  ‹×. ÃÚK¾³r®ax.1.
000303B0  2E CD F1 92 28 8E 17 AD 6A 9C D5 8A 8E 17 86 39  .Íñ’(Ž.­jœÕŠŽ.†9
000303C0  C8 0A F7 9B 92 D8 3A A8 92 60 73 6A 5E 12 2A 94  È.÷›’Ø:¨’`sj^.*”</code></pre></td>
<td><pre><code>Offset(h) 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00081BA0  40 9F 75 39 22 96 C2 12 A2 9C BC CF 53 99 73 40  @Ÿu9&quot;–Â.¢œ¼ÏS™s@
00081BB0  5D AD A7 F6 26 6E 50 35 55 A8 8A B9 24 A1 F5 35  ]­§ö&amp;nP5U¨Š¹$¡õ5
00081BC0  BC 3B 7A 88 17 75 9C 44 A9 2D 4B E0 8B 80 92 E7  ¼;zˆ.uœD©-Kà‹€’ç</code></pre></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>

  - Now, go to "File" \> "Open" and search the EID root key file. Once
    is opened, do CTRL+A to select all the content and copy it (CTRL+C).
    Go to the previous sheet we created (the one where we pasted
    NOR/NAND bytes) and just paste (CTRL+V), making the bytes from the
    eid root key appear under the NOR/NAND ones. Go to "File" \> "Save"
    and rename this file as "3Dump.bin"
  - Take your "3Dump.bin" file and place it the USB drive.
  - Plug your USB drive into the right-most USB port (/dev_usb000/).
  - Launch GetKey from XMB (with the game disc inserted): it'll run and
    exit back to XMB.
  - It creates two files on the root of the USB drive: disc.pic &
    getkey.log
  - The getkey.log file will contain the disc_key, disc_id and PIC. If
    anything went wrong creating the 3Dump.bin or extracting the data,
    the "getkey.log" will contain a WARNING message saying the process
    failed.
  - Make sure that you provide the complete and correct metadata for
    each dump.

## Dumping with a PC and an external PS3/OEM Blu-Ray drive

Dumping with a Windows PC and specific, compatible Blu-Ray drive is the
cheapest way to get dumping (unless you already own a PS3).

### Tools

**Hardware**

  - 3k3y Ripper
    Device[6](https://www.modchipcentral.com/store/product.php?productid=17905):
    v2 is preferred for a wider range of compatibility, but v1 will work
    fine with the drive linked below.
  - Sony PS3 Blu-Ray drive with sector 2
    zeroing[7](https://www.ebay.com/itm/252061696576)
  - Power adapter. Search "UGREEN USB to IDE Converter, USB 3.0 to IDE"
    on Amazon - even though you don't need to convert IDE to anything,
    it's still a great power adapter for feeding power to your Blu-Ray
    drive.

**Software**

  - [IsoTools](https://archive.org/download/IsoToolsV1.34.9.7z/IsoTools-v1.34.9.7z)
  - [GetKeyFrom3k3y](https://archive.org/download/GetkeyFrom3k3yR1.7z/GetkeyFrom3k3y-r1.7z)
  - [DVDToImg](https://archive.org/download/dvdtoimg_v1_01.7z/dvdtoimg_v1_01.7z)

### First Time Setup

  - Hardware: Your Blu-Ray drive should come with a ribbon, attach this
    to the 3k3y Ripper. The 3k3y Ripper should come with a USB cable,
    plug this in to the 3k3y Ripper and the other end into your
    computer. Feed your Blu-Ray drive power with the UGREEN power
    adapter AND plug the adapter's USB cable to the computer for
    additional power. Your computer should detect the drive.
  - Software: Install IsoTools app linked above. Unzip GetKeyFrom3k3y
    and DVDToImg, these two are command line apps.
  - Power on your drive and hook up the USB to your computer.
  - Make sure your Blu-Ray drive is empty, you can eject any discs with
    the tiny black button on top of the 3k3y Ripper.
  - Open IsoTools. You should get a warning telling you that if you
    press "Yes" you will no longer be able to use the drive with a PS3
    console ("You've enabled the use of default keys..."). Chose "Yes".
    \[NOTE: if you don't get this pop-up, go to Tools \> Settings and
    uncheck and recheck "Use Default Keys", at this point you should get
    the pop-up.\]

### Dumping

  - Open IsoTools app.
  - Put your PS3 disc into the drive. IsoTools should recognize the disc
    and say something like "PS3 Game Disc: BLUS-12345, Ready". (Note 1:
    When you insert your PS3 disc, don't be surprised if Windows doesn't
    recognize it under "My Computer". Note 2: You might have to eject
    and reinsert the disc before IsoTools will recognize it.)
  - Close IsoTools app.
  - Now open up the command line and cd (change directory) to the
    location of the dvdtoimg.exe that you downloaded earlier, and run a
    command: **dvdtoimg f gamename.iso** (where "f" is the drive
    letter). Eventually, percentage will reach "100%" and then "Process
    finished".
  - Eject the disc.
  - Reopen IsoTools app, insert the disc again, and choose "Rip". Now
    IsoTools will ask you where you want to save the files (an .ird and
    a .dec.iso). Once you click Save, IsoTools will start dumping. You
    can immediately "Cancel" the dump and close IsoTools.
  - Move the gamename.dec.iso file to the location of GetKeyFrom3k3y.exe
  - Now in the command line, cd (change directory) to the location of
    GetKeyFrom3k3y.exe, and run a comand: **GetKeyFrom3k3y
    "gamename.dec.iso" \>info.txt**
  - Now you can delete the .ird and gamename.dec.iso files.

## Dumping with a PC and a Non-PS3/OEM Blu-Ray Drive

PS3 discs via this method cannot have their IRD/Keys extracted, but are
still datted in redump, sometimes this information can be tracked down
on the internet so isn't pertinent to datting.

If you choose to dump with this method, use this dumping guide: [Disc
Dumping Guide (DICUI)](Disc_Dumping_Guide_\(DICUI\) "wikilink").

## Submit your Dump

The required information for a submission is:

  - Title of the game
  - Category; usually Games.
  - Media type: either BD-25 or BD-50
  - Serial on the disc and, if it's different, serial on the cover
    (spine)
  - Version of the game. This can be found by mounting the iso file and
    opening the PARAM.SFO file in the PS3_Game folder in a hex editor
    (for example <http://www.hexed.it>). Look for the VERSION and
    **not** the APP_VER.
  - Ringcode information (see below for more information)
  - Checksums for gamename.iso
  - Contents of info.txt if dumped with PC method or getkey.log if
    dumped on console
  - Barcode(s)

Furthermore, it's optional (but highly appreciated) to check which
languages the game has.

### Ring Information

The ring information can be found on the 'bottom' of the disc at
printed/moulded on or near the inner plastic part of the disc.

**Mastering code**

For European discs, this is usually in the following format:

`A0101XXXXXX-A511   X000`

American discs have a code in the format:

`BPSS-XXXXXXXX  XX`

Asian discs have a code in the format:

`[Serial]   X`

*Don't forget the tab\!*

**Mastering SID**

Mastering SID is printed on the disc (don't confuse it with the Mould
SID which is pressed/moulded into the plastic). It is always in the
format:

`IFPI LXXX`

**Toolstamp**

The toolstamp is a very small piece of text usually at the end of the
Mastering Code. It's a few characters long. Note that the text is often
mirrored, so make sure you don't copy the code backwards.

**Mould SID**

The Mould SID not printed on the back of the disc, but moulded/pressed
in the plastic at the absolute center of the disc. The Mould SID is
really small and can be read from the front/labelside (instead of the
back) of the disc. It's always in the format:

`IFPI XXXX`

### Template

You can copy/paste the below template to submit a dump on the forum:

`[b]Media:[/b]`
`[b]Category:[/b] Games`
`[b]Title[/b]: `
`[b]Region:[/b] `
`[b]Languages:[/b] `

`[b]Serial:[/b] `

`Ring:`
`[b]Mastering Code:[/b] `
`[b]Mastering SID Code:[/b] `
`[b]Toolstamp:[/b] `
`[b]Mould SID Code:[/b] `

`[b]Barcode:[/b]  `

`[b]Comments:[/b] `


`[b]Version:[/b] `
`[b]Edition:[/b] `

`[b]Disc Key:[/b] `
`[b]Disc ID:[/b] `
`[b]PIC:[/b] `


`[b]Size:[/b] `
`[b]CRC-32:[/b] `
`[b]MD5:[/b] `
`[b]SHA1:[/b] `

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")