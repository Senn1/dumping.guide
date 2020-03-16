Note: This guide is only for dumping Blu-Ray Video discs, NOT Blu-Ray
console discs (see [Dumping Guides](Dumping_Guides "wikilink")).

**Caveat with this guide:** The following 2 older versions of DVDFab and
Find VUK work together. The disadvantage of using this older version of
DVDFab is that it won't be able to process newer discs. For a disc from
2018, I got a message saying to upgrade to newer DVDFab. However if you
do, you'll need to figure out which version of Find VUK will work with
it. Please let us know if you do so we can update the below links with
newer versions of the below apps that are compatible with each other.

## Software

  - [Find
    VUK 1.09](https://archive.org/download/findvuk1.09/FindVUK_1.09.zip)
    (unzip FindVUK in a folder with write-access)
  - [DVDFab
    v10.0.4.8](https://archive.org/download/dvdfabv10.0.4.8/DVDFab_v10.0.4.8.exe)
    (install)

## Dumping

  - DVDFab should be closed.
  - Insert Blu-Ray disc.
  - Launch FindVUK.exe, this will automatically launch DVDFab.
  - Select "Try" to use DVDFab as a trial.
  - A progress bar window should appear as DVDFab is processing the
    disc, which takes a few seconds. FindVUK should report that it found
    the key.
  - Eject the disc, close FindVUK, close DVDFab (you may have to
    forcibly kill the process, for me it frequently hangs at that time).
  - In FindVUK's OnlineDB_Backup subfolder, an xml file is created for
    each disc. Example for [1](http://redump.org/disc/)
    48128/D6630E5AA891CE4164A44E627E5672F092D0D717-BDROM (Meta).xml:

<?xml version="1.0" encoding="UTF-8"?>

<Bluray>
` `<FileType>`BlurayMetaXML`</FileType>
` `<DiscId Date="2008-04-30">`D6630E5AA891CE4164A44E627E5672F092D0D717`</DiscId>
` `<VolumeId>`FC3AAC79EA225AE1448C983C98259319`</VolumeId>
` `<MediaKey>`D3A5957A0219001AB62D31EAC9A10E5A`</MediaKey>
` `<VolumeUniqueKey>`F283D691673583569819F114460A6BF7`</VolumeUniqueKey>
` `<VolumeLabel>`BDROM`</VolumeLabel>
` `<BDplus>`0`</BDplus>
` `<BusEncryptionEnabled>`0`</BusEncryptionEnabled>
` `<MKBrev>`7`</MKBrev>
` `<MainPlaylist/>
` `<UnitKeys>
`   `<UnitKey Nr="1">`562D5AC9EF5925866D7F07BBDC8ADFEF`</UnitKey>
` `</UnitKeys>
` `<MetaTitles>
`   `<MetaTitle Language="" Manual="1">`Metal Gear Solid 4 Bonus Disc`</MetaTitle>
` `</MetaTitles>
` `<Hashes>
`   `<Hash Type="MD5" File="MKB_RO.inf" Size="1048576">`BF8D213F679D3423526B1185B30C63D2`</Hash>
` `</Hashes>
` `<Application>`FindVUK 1.09`</Application>
` `<VolumeSize>`24395972608`</VolumeSize>
</Bluray>

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")