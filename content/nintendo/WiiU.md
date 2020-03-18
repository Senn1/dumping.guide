---
title: "Nintendo WiiU"
---

This guide is an early work in progress.

## Tools

  - A Wii U console with an Internet Connection - 5.5.1 or later is
    recommended, but anything that can run the homebrew channel for Wii
    U is fine
  - A 32GB (or higher) SD Card formatted to FAT32, or an SD card of any
    size and a 32GB (or higher) USB flash drive formatted to FAT32 or
    NTFS. Higher sizes are recommended due to every Wii U Dump being
    25GB, however Wii U cannot power some external HDDs without a
    Y-Cable.
  - [WUDump](https://github.com/FIX94/wudump/releases/latest), to dump
    the actual game.
  - (Optional) [WUDCompress](https://archive.org/download/WudCompress)
    to later compress the WUD into a WUX, which is a lot more space
    saving.

## First Time Setup

If you are planning on using homebrew a lot, consider setting up Haxchi
- this allows you to run homebrew from a title on your Wii U Menu
instead of trying from the browser multiple times. If you already have
Haxchi, simply put the WUDump ELF into sd:/wiiu/apps/wudump/ and then
run it in HBL.

  - Download [The Homebrew
    Channel](https://github.com/dimok789/homebrew_launcher/releases/tag/v1.3)
    and place the wiiu folder on your SD Root.
  - Download WUDump from above, and place it in SD:/wiiu/apps/wudump/
    (you will need to make the folder 'wudump')

## Dumping

  - If you use Haxchi, open Haxchi and run the Homebrew Launcher.
  - If you don't use Haxchi, go to <http://usploit.hacks.guide> on your
    Wii U (bookmark the page as the exploit isnt the most stable) - make
    sure the curtains are open on the TV and run the launcher. If your
    Wii U freezes, reboot and try again.

<!-- end list -->

  - Once in the Homebrew launcher, select wudump, then hit Load.
  - Press the appropiate button for what device you are dumping to
    (FAT32 USB, NTFS USB, or FAT32 SD)
  - Once ready, the program will inform you to insert the disc; if you
    already have the disc inserted, simply eject and re-insert.

This process takes a long time (1-2 hours\!), so go get lunch and wait.

## Submitting Info to Redump

Submit your dumps on the "Dumps" forum
[here](http://forum.redump.org/forum/11/dumps/). If you have dumper
rights you can submit the dumpinfo using the [New Disc
form](http://redump.org/newdisc/).

**Notes using the New Disc form**:

  - In the New Disc form, put all ring information in the 'Ring' field
    like you would using the template below (a moderator will format
    them properly).
  - Language Select and Case Serial information can go into the
    'Comments' field.
  - Make sure you submit the game.key\!

`[quote]`
`Note: paste the contents of the WUDump `<GAMEID>`-dumpinfo.txt here.`
`[/quote]`

`[b]Game Information:[/b]`

`[b]Game Title:[/b]`
`[b]Region:[/b] Europe / USA / Japan / UK / Scandinavia / Australia`
`[b]Languages:[/b] English, German, French, Spanish, Italian, Dutch, Swedish, Norwegian, Danish, etc...`
`[b]Language Select:[/b] Language select via BIOS system settings / Language select screen at startup`
`[b]Disc Serial:[/b]`
`[b]Edition:[/b] Original / Demo / Starter Pack / Nintendo Selects`
`[b]Case Barcode:[/b] `
`[b]Case Serial:[/b]`
`[b]Size:[/b] 25.025.314.816`

`[b]Ring Information:[/b]`

`[b]Mastering Code (back):[/b]`
`[b]Mastering SID Code (back):[/b] `
`[b]Mould SID Code (back):[/b] IFPI XXXX `
`[b]Additional Mould Text (back):[/b]`
`[b]Toolstamp (back):[/b]`
`[b]Mould SID Code (front):[/b] IFPI XXXX`
`[b]Additional Mould Text (front):[/b]`

`[b]Game Key:[/b] Attached`

**Note:** Don't forget to attach the game.key file to the post\!

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")