
# Table of Contents
- [Tools](#tools)
- [Looking up depot info](#looking-up-depot-info)
- [Obtaining depot manifests](#obtaining-depot-manifests)
- [Downloading the depot data](#downloading-the-depot-data)
- [Validating and cleaning depot data](#validating-and-cleaning-depot-data)
- [Finishing up](#finishing-up)
- [Some remarks](#some-remarks)


## Tools

-   [Steam](https://store.steampowered.com/about/)
-   [sisInstall](https://www.mediafire.com/file/gyyolxgylprcozr/sisInstall.2019-10-27.7z/file)
-   [TINcft command line](https://www.mediafire.com/file/zbl1eu1x3nknhcn/TINcft_command.zip/file)
-   [PICSDownloader](https://www.mediafire.com/file/6vuzvw507vx45bn/PICSdownloader.2019-01-11.7z/file)
-   [TrrntZipUI V2.5.2](http://www.romvault.com/trrntzip/)

## Looking up depot info

To find info about a particular game and its (historical) depots, visit  [SteamDB](https://steamdb.info/).  
Use the Search... box to find a particular game, click on its APPID. Then click on 'Depots'. Then you can select the 'public' branch and it will show the most recent Depot ID's and GID's (GID = Manifest ID).  
If you are looking for historical Depot ID's, click on one of the Depot ID's and then on the 'Manifests' tab. This will show a list of the 'Previous manifests' and their ID's.  
  
Alternatively, here's an Excel spreadsheet that shows all the up to date Apps and Manifests as of 16-8-2019:  [[1]](http://www.mediafire.com/file/qvjvhy8912am7wp/190816_Steam_Manifests.xlsx/file). Instructions will be added later for generating a fresh .csv file using your Steam account, PICSdownloader and some tools.

## Obtaining depot manifests

After determining the App ID, Depot ID and Manifest ID's that are needed, it's time to download the actual .manifest files.  
Manifest files contain all the information (filenames, filesizes, SHA1 hashes) that is needed to verify the game contents.  
The easiest way of downloading the most recent manifest version of a depot is to install the game with Steam, and grab the needed .manifest files from the 'depotcache' folder in the main Steam folder.  
For downloading any new or old depot manifest, it's also possible to use  [sisInstall](http://www.mediafire.com/file/c2zaokhois4xv4g/sisInstall.2019-05-19.7z/file)  
Download and extract it somewhere, open Command Prompt, and use the following command:  
getManifest <appID> <cfID> <cfVersion> <username> <password> [steamGuardKeyOrMobileCode]  
where cfID is the Depot ID, cfVersion is the Manifest ID.  
It's recommended that you completely disable Steam Guard for your account, and also exit Steam, before using sisInstall.

## Downloading the depot data

[Here](https://steamcommunity.com/sharedfiles/filedetails/?id=889624474)  you can find a guide that explains how to download a particular depot (version) using the "download_depot" Steam console command.

## Validating and cleaning depot data

Download and extract  [TINcft command line](https://www.mediafire.com/file/zbl1eu1x3nknhcn/TINcft_command.zip/file). Put any .manifest files in the same folder.  
Copy the game files that you downloaded to a folder.  
The following commands can be used for validating/cleaning the files in a folder:  

    TINcft_command validate -c <manifest>@<folder> (check for missing or bad files)  
    TINcft_command correct -c <manifest>@<folder> (fix filenames and remove files with bad filesizes/checksums)  
    TINcft_command junk -c <manifest>@<folder> (list any unreferenced files)  
    TINcft_command clean -c <manifest>@<folder> (remove any unreferenced files)  

Be careful about using the 'correct' and 'clean' commands, as they will remove any files that aren't referenced in the depot manifest. If somehow your game folder contains mixed together files from multiple depots then it's probably best to determine (using the 'junk' command) which files are unneeded and move them to a separate (parent) folder for later use.

## Finishing up

After you validated/cleaned the files inside a folder with TINcft_command and it is a complete match to the .manifest (no bad/missing/unneeded files/folders), it's time to compress them. I have been storing my games as torrentzipped .zip archives with the filename matching to the .manifest filename. These files are stored in a folder with the format "AppID - Game name" (this info can be found on SteamDB or in the Steam store). Here's an example .sfv for some games:

    228980 - Steamworks Common Redistributables\228982_6413394087650432851.manifest 27715B07  
    228980 - Steamworks Common Redistributables\228982_6413394087650432851.zip 68FF9CA2  
    228980 - Steamworks Common Redistributables\228990_1829726630299308803.manifest CE4FED72  
    228980 - Steamworks Common Redistributables\228990_1829726630299308803.zip 17340C94  
    220 - Half-Life 2\221_6852525334866196612.manifest D2962409  
    220 - Half-Life 2\221_6852525334866196612.zip F10ED3FE  
    220 - Half-Life 2\222_7778301893023663250.manifest 99B7C537  
    220 - Half-Life 2\222_7778301893023663250.zip 210E8557  
    380 - Half-Life 2 Episode One\380_557309076835369147.manifest 9018AEEE  
    380 - Half-Life 2 Episode One\380_557309076835369147.zip 44041C9F  
    380 - Half-Life 2 Episode One\389_7610921509433355487.manifest FB72C27B  
    380 - Half-Life 2 Episode One\389_7610921509433355487.zip 222DC97A  
    420 - Half-Life 2 Episode Two\420_7240365789913596100.manifest 7BC60D6B  
    420 - Half-Life 2 Episode Two\420_7240365789913596100.zip 498C7E6D  

If you end up with the same files, then you're doing it correctly.

## Some remarks

- This method is only for preserving content that is currently hosted on Steam. The current Steam3 network was introduced in late 2011, so the network is missing historical game data from before this time.  
- SteamDB only started logging historical manifest ID's in 2014, so info from before this time may be missing/unknown, unless an old .manifest is available somewhere.  
- Only the pure game data is preserved, so any DRM is kept intact. To play games that only have Steam stub protection, you could use an emulator like "Smart Steam Emu". For games with other DRM (incomplete list:  [[2]](https://pcgamingwiki.com/wiki/The_Big_List_of_3rd_Party_DRM_on_Steam)), you may have to resort to cracks/fixed files.  
- Even though the tools/methods in this guide were tested thoroughly, they are offered at your own risk. The author of the tools (steamCooker) and we will not accept responsibility for any damages!
