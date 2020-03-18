---
title: "Nintendo Switch Digital"
---

# Table of Contents
- [From installed title (NXDumpTool)](#from-installed-title--nxdumptool-)
  * [Requirements](#requirements)
  * [Dumping steps](#dumping-steps)
  * [Dumping steps (orphan content)](#dumping-steps--orphan-content-)
  * [Merge part files (FAT32 / multi-session dump only)](#merge-part-files--fat32---multi-session-dump-only-)
  * [Extracting data from NSP](#extracting-data-from-nsp)
    + [Unpacking NSP dump](#unpacking-nsp-dump)
    + [Collect ticket information](#collect-ticket-information)
    + [Collect NCA information](#collect-nca-information)
- [Gathering Dump Info](#gathering-dump-info)

[todo: you can possibly get dec+enc title key in one go by using hactool "-i" on the main nca]

## From installed title (NXDumpTool)

It's an open-source homebrew application capable of generating installable Nintendo Submission Package (NSP) dumps from installed digital titles.

### Requirements

-   A Nintendo Switch console with a firmware version greater than or equal to 3.0.0. Must either be vulnerable to  [Fusée Gelée](https://github.com/Qyriad/fusee-launcher/blob/master/report/fusee_gelee.md)  or have a firmware version compatible with  [Caffeine](https://github.com/liuervehc/caffeine). The exact details on how to use these exploits to launch homebrew applications aren't covered in this guide.
-   The latest  [NXDumpTool](https://github.com/DarkMatterCore/nxdumptool/releases/latest)  release saved to  `sdmc:/switch/nxdumptool/nxdumptool.nro`.
-   Keys file generated using  [Lockpick_RCM](https://github.com/shchmue/Lockpick_RCM), located at  `sdmc:/switch/prod.keys`. Run the payload on your console in order to dump the keys. They're needed by NXDumpTool to decrypt contents while generating NSP dumps.

  
**Note #1:**  if you use a SD card with a FAT32 partition and the game you wish to dump is bigger than 4 GiB, you can dump it in smaller parts, but you must reassemble them afterwards.

  
**Note #2:**  you don't need to have enough free space in your SD card for a whole dump. Sequential (multi-session) dumping is available in NXDumpTool, and it's automatically triggered if there's not enough space for a whole dump - but there must be at least 1 GiB of free space. After each session, you'll have to transfer the generated part files to your PC before continuing the dump process in the next session.

  
**Note #3:**  dump verification against No-Intro database is also available in the application, but it requires a working Internet connection at runtime.

### Dumping steps

1.  Using either Fusée Gelée or Caffeine, boot into the CFW of your preference and load the Homebrew Launcher using title override (hold R while launching a game).
2.  Load NXDumpTool.
3.  Select  `Dump SD card / eMMC (NANDUSER) content`, then select the game you wish to dump from the displayed list.
    -   **If you can't find your game on the list, or if the list is empty**, it most likely means you're using a gamecard with updates/DLCs installed to the SD card and/or eMMC. These titles are internally referred to as "orphan content" in NXDumpTool. You can access the orphan content list by pressing the Y button in the SD/eMMC menu. For more information, see  [Dumping steps (orphan content)](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Digital_Software_Dumping_Guide#Dumping_steps_.28orphan_content.29 "Nintendo Switch Digital Software Dumping Guide").
4.  Select  `Nintendo Submission Package (NSP) dump`.
    1.  **If you have installed updates / DLCs for the selected title**:
        -   If you want to dump the base game / application, select  `Dump base application NSP`.
        -   If you want to dump an installed update, select  `Dump installed update NSP`.
        -   If you want to dump an installed DLC, select  `Dump installed DLC NSP`.
    2.  **Otherwise, if you have no installed updates / DLCs for the selected title**, go to the next step.
5.  Set the available options to the following values:
    -   `Split output dump (FAT32 support)`: set it to  **Yes**  if you're using a FAT32 partition in your SD card. Otherwise, set it to  **No**.
    -   `Verify dump using No-Intro database`: set it to  **Yes**  if you wish to verify your dump using the No-Intro database. This requires a working Internet connection.
    -   `Remove console specific data`:  **Yes**. This will remove console/account data from a personalized ticket and convert it to a common ticket if the title you wish to dump uses titlekey crypto. If the ticket is already a common one, it is left untouched.
    -   `Generate ticket-less dump`:  **No**.
    -   `Change NPDM RSA key/sig in Program NCA`:  **No**. This option only appears with base applications and updates.
    -   **If you chose to dump an installed update**:
        -   `Dump delta fragments`:  **Yes**. This will dump the delta fragments from the update (if available).
        -   `Update to dump`: use the left/right buttons to cycle between the available updates and select the one you want to dump.
    -   **If you chose to dump an installed DLC**:
        -   `DLC to dump`: use the left/right buttons to cycle between the available DLCs and select the one you want to dump.
    -   `Output naming scheme`: optional. Just choose the naming scheme you'd like to use.
6.  Select  `Start NSP dump process`, press A and wait for the process to finish. You'll be able to find the output file(s) in  `sdmc:/switch/nxdumptool/NSP`.
7.  **If dump verification is enabled**, after dumping, you should see the CRC32 checksum for the encrypted CNMT NCA in your NSP dump. If the application says that it found a matching database entry, then this is likely a good redump. However, we do need a little more information (see  [Extracting data from NSP](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Digital_Software_Dumping_Guide#Extracting_data_from_NSP "Nintendo Switch Digital Software Dumping Guide")).
8.  Copy the output dump to your PC. If you used the split method for FAT32, or if you used sequential (multi-session) dumping, you'll need to reassemble the part files into a single NSP dump. For more information, see  [Merge part files (FAT32 / multi-session dump only)](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Digital_Software_Dumping_Guide#Merge_part_files_.28FAT32_.2F_multi-session_dump_only.29 "Nintendo Switch Digital Software Dumping Guide").

### Dumping steps (orphan content)

1.  Using either Fusée Gelée or Caffeine, boot into the CFW of your preference and load the Homebrew Launcher using title override (hold R while launching a game).
2.  Load NXDumpTool.
3.  Select  `Dump SD card / eMMC (NANDUSER) content`, then press the Y button.
4.  Look for the orphan update / DLC you wish to dump, then press A on it.
5.  Select  `Nintendo Submission Package (NSP) dump`.
6.  Set the available options to the following values:
    -   `Split output dump (FAT32 support)`: set it to  **Yes**  if you're using a FAT32 partition in your SD card. Otherwise, set it to  **No**.
    -   `Verify dump using No-Intro database`: set it to  **Yes**  if you wish to verify your dump using the No-Intro database. This requires a working Internet connection.
    -   `Remove console specific data`:  **Yes**. This will remove console/account data from a personalized ticket and convert it to a common ticket if the title you wish to dump uses titlekey crypto. If the ticket is already a common one, it is left untouched.
    -   `Generate ticket-less dump`:  **No**.
    -   **If you chose to dump an orphan update**:
        -   `Change NPDM RSA key/sig in Program NCA`:  **No**.
        -   `Dump delta fragments`:  **Yes**. This will dump the delta fragments from the orphan update (if available).
    -   `Output naming scheme`: optional. Just choose the naming scheme you'd like to use.
7.  Select  `Start NSP dump process`, press A and wait for the process to finish. You'll be able to find the output file(s) in  `sdmc:/switch/nxdumptool/NSP`.
8.  **If dump verification is enabled**, after dumping, you should see the CRC32 checksum for the encrypted CNMT NCA in your NSP dump. If the application says that it found a matching database entry, then this is likely a good redump. However, we do need a little more information (see  [Extracting data from NSP](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Digital_Software_Dumping_Guide#Extracting_data_from_NSP "Nintendo Switch Digital Software Dumping Guide")).
9.  Copy the output dump to your PC. If you used the split method for FAT32, or if you used sequential (multi-session) dumping, you'll need to reassemble the part files into a single NSP dump. For more information, see  [Merge part files (FAT32 / multi-session dump only)](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Digital_Software_Dumping_Guide#Merge_part_files_.28FAT32_.2F_multi-session_dump_only.29 "Nintendo Switch Digital Software Dumping Guide").

### Merge part files (FAT32 / multi-session dump only)

1.  Copy all parts of your NSP dump to your PC.
2.  Merge your part files into a complete dump:
    1.  **On Windows**:
        1.  Open the command prompt and use  `cd`  to change the current working directory to the one that holds your split files (e.g.  `cd C:\switch_dumps`).
        2.  Type the following command according to your specific case, then press Enter:
            -   **If you're dealing with a split NSP dump (non-sequential)**:  `copy /b * game.nsp`.
            -   **If you're dealing with a split NSP dump (sequential)**:  `copy /b *.nsp.hdr+*.nsp.0* game.nsp`.
    2.  **On Linux/Mac**:
        1.  Open your terminal emulator and use  `cd`  to change the current working directory to the one that holds your split files (e.g.  `cd /dev/sdb/switch_dumps`).
        2.  Type the following command according to your specific case, then press Enter:
            -   **If you're dealing with a split NSP dump (non-sequential)**:  `cat * > game.nsp`.
            -   **If you're dealing with a split NSP dump (sequential)**:  `cat *.nsp.hdr *.nsp.0* > game.nsp`.
3.  Your part files should be reassembled into a full  `game.nsp`  file. You can safely delete your part files afterwards.

### Extracting data from NSP

[To do: some sort of batch script would be desirable for this section]

In order to gather relevant data from digital title dumps (like NCA information, ticket, titlekey, etc.), you'll need to use  [hactool](https://github.com/SciresM/hactool)  and  [nstool](https://github.com/jakcron/nstool). The following sections will assume:

1.  You have already downloaded both programs to a specific location in your PC.
2.  Moved the full NSP dump and copied the keys file generated by Lockpick_RCM (located at  `sdmc:/switch/prod.keys`) to the same location.
3.  Opened a command prompt / terminal emulator window.
4.  Used  `cd`  to change the current working directory accordingly.

#### Unpacking NSP dump

1.  Type  `hactool -r -t pfs0 --outdir=unpacked_nsp [game.nsp]`  and press Enter. You'll end up with a  `unpacked_nsp`  directory, which holds the unpacked NSP data.
    -   **Note:**  replace  `[game.nsp]`  with the actual NSP filename. If it has any whitespaces, enclose it using double quotes (e.g.  `hactool -r -t pfs0 --outdir=unpacked_nsp "VA-11 HALL-A v65536 (0100A6700D66E800) (UPD).nsp"`).

#### Collect ticket information

1.  Look for a  `.tik`  file inside the  `unpacked_nsp`  directory and copy its full filename (e.g.  `0100a6700d66e8000000000000000008.tik`).
    -   **Note:**  if there's no  `.tik`  file available, it means the digital title you dumped uses standard crypto. Skip to  [Collect NCA information](https://wiki.no-intro.org/index.php?title=Nintendo_Switch_Digital_Software_Dumping_Guide#Collect_NCA_information "Nintendo Switch Digital Software Dumping Guide").
2.  To collect data from the ticket:
    -   **On Windows**:
        -   Type  `nstool -t tik unpacked_nsp\[file.tik] > tik_info.txt`  and press Enter.
    -   **On Linux/Mac**:
        -   Type  `nstool -t tik unpacked_nsp/[file.tik] > tik_info.txt`  and press Enter.
    -   **Note:**  replace  `[file.tik]`  with the actual ticket filename (e.g.  `nstool -t tik unpacked_nsp\0100a6700d66e8000000000000000008.tik > tik_info.txt`).
3.  You'll end up with a  `tik_info.txt`  file, which contains info from the ticket file. Open it, copy the  `Data`  element and strip the colons from it (e.g.  `00:01:02:03:04:05:06:07:08:09:0A:0B:0C:0D:0E:0F`  ->  `000102030405060708090A0B0C0D0E0F`). This is the encrypted titlekey for your dumped title - keep it in your clipboard or save it somewhere else.

#### Collect NCA information

You'll have to repeat the following steps for every  `.nca`  file inside the  `unpacked_nsp`  directory.

1.  To collect data from a NCA:
    -   **On Windows**:
        -   **If your dumped title uses titlekey crypto**, type  `hactool -r -y -k prod.keys -t nca --titlekey=[stripped_titlekey] --disablekeywarns unpacked_nsp\[file.nca] > [nca_info.txt]`  and press Enter.
        -   **Otherwise, if your dumped title uses standard crypto**, type  `hactool -r -y -k prod.keys -t nca --disablekeywarns unpacked_nsp\[file.nca] > [nca_info.txt]`  and press Enter.
    -   **On Linux/Mac**:
        -   **If your dumped title uses titlekey crypto**, type  `hactool -r -y -k prod.keys -t nca --titlekey=[stripped_titlekey] --disablekeywarns unpacked_nsp/[file.nca] > [nca_info.txt]`  and press Enter.
        -   **Otherwise, if your dumped title uses standard crypto**, type  `hactool -r -y -k prod.keys -t nca --disablekeywarns unpacked_nsp/[file.nca] > [nca_info.txt]`  and press Enter.
    -   **Note:**  replace the following sections in the provided command(s):
        -   `[stripped_titlekey]`  with the encrypted titlekey from the previous section, if applicable (e.g.  `000102030405060708090A0B0C0D0E0F`).
        -   `[file.nca]`  with the current NCA filename (e.g.  `e4239b7e79cc5a4b307413e5f34ea325.nca`).
        -   `[nca_info.txt]`  with a TXT filename that resembles the current NCA file (e.g.  `e4239b7e79cc5a4b307413e5f34ea325_info.txt`).
    -   Example command line:  `hactool -r -y -k prod.keys -t nca --titlekey=000102030405060708090A0B0C0D0E0F --disablekeywarns unpacked_nsp\e4239b7e79cc5a4b307413e5f34ea325.nca > e4239b7e79cc5a4b307413e5f34ea325_info.txt`.
2.  You'll end up with a TXT for each NCA file available in the  `unpacked_nsp`  directory, each one containing in-depth details about their corresponding NCA file.

## Gathering Dump Info

-   **Digital serial**:
    -   **For CDN dumps**, put the title ID that was requested from the CDN  `atum`  server, in lowercase.
    -   **For installed title dumps made with NXDumpTool**  (and dumps of unknown origin), put the title ID from the  `Id`  children element in  `ContentMeta`, located in the  `.cnmt.xml`  file inside the  `unpacked_nsp`  directory. Remove the  `0x`  prefix (e.g.  `<Id>0x0100a6700d66e800</Id>`  ->  `0100A6700D66E800`). This is the same as the title ID at 0x0 in the original .cnmt.
-   **Dump tool**: e.g. "NXDumpTool vX.Y.Z".
-   **Files**:
    -   Set  **Format**  to  **CDN**.
    -   For filenames, use only the  **Native filename**  field.
    -   **For CDN dumps**, a  `.txt`  file containing the HTTP response headers should  _optionally_  be attached to each NCA. Each  `.txt`  should only contain the response headers for that exact NCA download request (e.g. not one from downloading it again / getting a HEAD request afterwards, etc.).
    -   Dat following files:
        1.  The NCAs, using the  `[lowercase_nca_id].nca`  /  `[lowercase_nca_id].cnmt.nca`  naming scheme (add the  `.nca`  /  `.cnmt.nca`  if it isn't present - e.g. if dumped straight from CDN).
        2.  Optional,  **if dealing with a title that uses titlekey crypto (ticket file)**:
            1.  First, dat the ticket file according to the dump method you used:
                -   **For CDN dumps**: check the value for the titlekey type field (1 byte @ 0x281) in the ticket file:
                    -   If it's set to  `0x01`, you're dealing with a personalized ticket that should be stripped like  [this](http://forum.no-intro.org/viewtopic.php?p=22683#p22683)  (the way NXDumpTool does, as of 2019-11-25). Afterwards, use  `[lowercase_rights_id]-stripped.tik`  as the ticket filename (e.g.  `0100a6700d66e8000000000000000008-stripped.tik`).
                    -   Otherwise, if it's set to  `0x00`, it's a common ticket that doesn't need to be modified. Use  `[lowercase_rights_id]-cetk.tik`  as the ticket filename (e.g.  `0100a6700d66e8000000000000000008-cetk.tik`).
                -   **For installed title dumps made with NXDumpTool**: check if the ticket file has already been stripped by looking at the 0x100 bytes area @ 0x004:
                    -   If it's filled with  `0xFF`, you're dealing with a stripped personalized ticket.
                    -   Otherwise, it's an untouched common ticket.
            2.  Grab the 16 bytes @ 0x180 in the stripped/common ticket and save them to a  `[lowercase_rights_id].enctitlekey.bin`  file (e.g.  `0100a6700d66e8000000000000000008.enctitlekey.bin`). This is the encrypted titlekey - dat this new file.
            3.  Now you'll need to decrypt the titlekey. Run  [hactool](https://github.com/SciresM/hactool)  on the  `Program`  type NCA from your dump using this command:  `hactool -r -y -k [keys_file] -t nca --titlekey=[encrypted_titlekey] --disablekeywarns [file.nca]`.
                -   **Note:**  replace the following sections in the provided command:
                    -   `[keys_file]`  with the filename from a keys file that contains previously dumped keys from a Switch console.
                    -   `[encrypted_titlekey]`  with the encrypted titlekey from the previous step (e.g.  `000102030405060708090A0B0C0D0E0F`).
                    -   `[file.nca]`  with the filename from the biggest NCA from your dump (e.g.  `e4239b7e79cc5a4b307413e5f34ea325.nca`).
                -   Example command line:  `hactool -r -y -k prod.keys -t nca --titlekey=000102030405060708090A0B0C0D0E0F --disablekeywarns e4239b7e79cc5a4b307413e5f34ea325.nca`.
            4.  Look for the  `Titlekey (Decrypted) (From CLI)`  element in the console output from hactool and copy its value - this is the decrypted titlekey. Save these 16 bytes to a  `[lowercase_rights_id].dectitlekey.bin`  file (e.g.  `0100a6700d66e8000000000000000008.dectitlekey.bin`) and dat it.
-   **Dump origin**:
    -   **Console SD card**: dumped from installed title data on console SD card.
    -   **Dev console**: dumped from installed title data on console.
    -   **CDN**: title data retrieved straight from CDN to PC, via PC downloading tool (that emulates the Switch download process) or network sniffer.