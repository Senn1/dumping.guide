---
title: "PlayStation Network"
---


## Generate Links

This can be done with a PC in a web browser, no console required.

-   Download and install the  [PSDLE browser extension](https://repod.github.io/psdle/)
-   With PSDLE installed you'll see an Icon on the bottom left corner. Click it.
-   You will be brought to a start page. Click "Start"
-   It will list all you digital games/DLC/themes. Everything you "own" on your Playstation Account, including free content, so seek out undumped free content as well.
-   You may select platforms you dont want to be included in exported file.
-   Click on "EXPORT VIEW" on the top.
-   You can select custom formatting for the output file. One suggested type is [["platform","Platform"],["name","Name"],["pkg","PKG direct link"],["id","Content ID"],["size","File Size"],["baseGame","Alternate Name"]]
-   Press OK and then CSV button to export the file to your PC.
-   The CSV file contains links for content which can be used to download pkg files or contributed as is.

## Dump Keys (PS3 and PSP)

Activation keys are needed for many PSN titles, except for updates and some other free content. Activation information is dumped to the .RAP format for PS3 and PSP.

Creating RAP files requires a CFW PS3. See other guides online for how to achieve this on up to 4.82 FW for most models using PS3Xploit 2.0

-   Download rif2rap
-   You will need to obtain the following files from your PS3 using FTP or another file managing solution
    -   **act.dat**  located at /dev_hdd0/home/00000000X/exdata/
    -   **idps**
    -   **.rif files**  located at /dev_hdd0/home/00000000X/*.rif
-   Run RifConv and in "Rif2Rap" tab select IDPS and act.dat files you previously downloaded from your PS3. Also select the directory where RIF files are located. Press create button to create RAPs.

[to be continued, see other online guide in the mean time]