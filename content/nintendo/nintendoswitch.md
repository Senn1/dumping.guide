---
title: "Nintendo Switch"
---

# Table of Contents
- [NXDumpTool](#nxdumptool)
  * [Requirements](#requirements)
  * [Dumping steps](#dumping-steps)
  * [Merge part files (FAT32 only)](#merge-part-files--fat32-only-)
- [Gathering Dump Info](#gathering-dump-info)

## NXDumpTool

It's an open-source homebrew application capable of generating NX Card Image (XCI) dumps from *Nintendo Switch* gamecards.

### Requirements

-   A *Nintendo Switch* console with a firmware version greater than or equal to 3.0.0. Must either be vulnerable to  [*Fusée Gelée*](https://github.com/Qyriad/fusee-launcher/blob/master/report/fusee_gelee.md)  or have a firmware version compatible with  [*Caffeine*](https://github.com/liuervehc/caffeine). The exact details on how to use these exploits to launch homebrew applications aren't covered in this guide.
-   The latest  [*NXDumpTool*](https://github.com/DarkMatterCore/nxdumptool/releases/latest)  release saved to  `sdmc:/switch/nxdumptool/nxdumptool.nro`.
-   Optional: the latest  [NSWDB.COM XML database](http://nswdb.com/xml.php)  saved to  `sdmc:/switch/nxdumptool/NSWreleases.xml`. This is used by NXDumpTool to verify gamecard dumps against scene releases at runtime. You can also get it straight from the application by going into  `Update options`  ->  `Update NSWDB.COM XML database`  from the main menu.

  
**Note #1:**  if you use a SD card with a FAT32 partition and the game you wish to dump is bigger than 4 GiB, you can dump it in smaller parts, but you must reassemble them afterwards.

  
**Note #2:**  you don't need to have enough free space in your SD card for a whole dump. Sequential (multi-session) dumping is available in NXDumpTool, and it's automatically triggered if there's not enough space for a whole dump - but there must be at least 1 GiB of free space. After each session, you'll have to transfer the generated part files to your PC before continuing the dump process in the next session.

  
**Note #3:**  dump verification against No-Intro database is also available in the application, but it requires a working Internet connection at runtime.

### Dumping steps

1.  Using either *Fusée Gelée* or *Caffeine*, boot into the CFW of your preference and load the *Homebrew Launcher* using title override (hold R while launching a game).
2.  Load *NXDumpTool*.
3.  Select  `Dump gamecard content`.
4.  Select  `NX Card Image (XCI) dump`.
5.  Set the available options to the following values:
    -   `Split output dump (FAT32 support)`: set it to  **Yes**  if you're using a FAT32 partition in your SD card. Otherwise, set it to  **No**.
    -   `Create directory with archive bit set`:  **No**.
    -   `Keep certificate`:  **No**. This will wipe the gamecard-unique certificate from the output XCI dump.
    -   `Trim output dump`:  **No**.
    -   `CRC32 checksum calculation + dump verification`:  **Yes**.
    -   `Dump verification method`:
        -   Set it to  `NSWDB.COM XML database (offline)`  if you wish to verify your dump using the NSWDB.COM XML database. Bear in mind that this will only work if you downloaded the NSWDB.COM XML database to its corresponding location in the SD card.
        -   Otherwise, set it to  `No-Intro database lookup (online)`  if you wish to verify your dump with No-Intro. This requires a working Internet connection.
6.  Select  `Start XCI dump process`, press A and wait for the process to finish. You'll be able to find the output file(s) in  `sdmc:/switch/nxdumptool/XCI`.
7.  After dumping, you should see the CRC32 checksum for your dump. If the application says that it found a matching database entry, then this is likely a good redump. However, we do need a little more information (see  [Gathering Dump Info](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Dumping_Guide#Gathering_Dump_Info "Nintendo Switch Dumping Guide")).
8.  Copy the output dump to your PC. If you used the split method for FAT32, or if you used sequential (multi-session) dumping, you'll need to reassemble the part files into a single XCI dump.

### Merge part files (FAT32 only)

1.  Copy all parts of your XCI dump to your PC.
2.  Merge your part files into a complete dump:
    1.  **On Windows**:
        1.  Open the command prompt and use  `cd`  to change the current working directory to the one that holds your split files (e.g.  `cd C:\switch_dumps`).
        2.  Type  `copy /b *.xc* game.xci`  and then press Enter.
    2.  **On Linux/Mac**:
        1.  Open your terminal emulator and use  `cd`  to change the current working directory to the one that holds your split files (e.g.  `cd /dev/sdb/switch_dumps`).
        2.  Type  `cat *.xc* > game.xci`  and then press Enter.
3.  Your part files should be reassembled into a full  `game.xci`  file. You can safely delete your part files afterwards.

## Gathering Dump Info

-   **CRC32**: Generated from the ROM file using  [HxD](https://mh-nexus.de/en/hxd/)  or  [HashTab](http://implbits.com/products/hashtab/)  on windows, or by using crc32 in a terminal emulator for linux/mac.
-   **MD5**: As above, or by using md5 in a terminal emulator for linux/mac.
-   **SHA-1**: As above, or by using shasum -a 1 in a terminal emulator for linux/mac.
-   **SHA-256**: As above, or by using shasum -a 256 in a terminal emulator for linux/mac.
-   **Game title**: If it differs between different places (e.g. title screen, console menu banner, box, cart) then go with the one on the front of the box.
-   **Region**: The region the cart originated from such as USA, Japan, Europe, Korea, China or "World" if it is being sold in three or more regions If you're unsure, consult the  [DAT-o-MATIC](http://datomatic.no-intro.org/)  or simply use the region from the label of your cart.
-   **Cart Serial**: It is located on the label on the front of the cart the form of "**LA-H-XXXXX-XXX**" (where X is a letter). The last three letters are the cartridge's region, not necessarily the region of the game itself. For additional information on cartridge serials, see  [Understanding Serials](https://wiki.no-intro.org/index.php?title=Understanding_Serials#Nintendo_-_Nintendo_Switch "Understanding Serials").
-   **Cart Reverse Serial**: It is located on the back of the cartridge printed on the plastic in the form "**AAAAABBBCCC**" where A is Cart Serial, B is unknown, and C is cartridge revision.
-   **Cart Revision (If applicable)**: last 3 digits on the reverse cartridge serial.
-   **Box Barcode**: The number on the case displayed beneath the vertical lines, see  [Barcode](http://en.wikipedia.org/wiki/Barcode).
-   **Box Serial**: The serial on the case. Example: HAC P AAAAA USA
-   **Size**: The size of the ROM in bytes.
-   **Scans**: The following scans (or photos) would be good to have: Front and back of the following items - box, cart and PCB.