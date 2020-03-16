This guide will help you understand, identify and properly dump
**SafeDisc** and **SmartE** protected discs.

## Information & Features

**SafeDisc** is a protection format that places "corrupt" sectors near
the beginning of a disc (usually in the 807 - 11920 sector range),
although these sectors can be found just about anywhere. The key to
dumping SafeDisc images correctly is to make sure that the corrupted
sectors are dumped properly. It is also critical to dump the disc at
least two times using at least two different drives (the more, the
better). If everything goes well, all of your checksums will match.

**SmartE** is Microsoft's cheaper version of SafeDisc. It functions very
much the same was as SafeDisc, and can be dumped the same way. The key
difference is that you should always get a total of 10 errors in your
SmartE image. If you get a different value than this, consult with one
of the dumping experts on the redump forums. (NOTE: Plextor drives have
been found to handle SmartE protection the best. Other drives can
produce unreliable results.)

## Detection

For this you need [ProtectionID
download](https://web.archive.org/web/20180101183850/https://pid.gamecopyworld.com/dl.php?f=ProtectionId.690.December.2017.rar)
or [BurnOut](http://sourceforge.net/projects/burnout/).

If you've installed the game, you can use [SafeDisc
Analyser](http://www.generalfiles.biz/download/gs4e5062a4h32i0/SafediscAnalyser.zip.html)
to find out the exact SafeDisc version being used.

## Dumping

### Methods

There are two solutions (at present) for dumping SafeDisc games: (1)
CloneCD, and (2) CD Manipulator. Both tools have been tested
extensively, and have proven to be highly dependable in most cases (when
properly configured). It's generally advisable to dump protected discs
using different software AND different drives whenever possible in order
to ensure that a thorough dump has been performed. That said, feel free
to use whichever tool suits you best\! Use the following to guide to
setup your software:

1.  [CloneCD](http://www.slysoft.com/en/clonecd.html)
      - Create a custom profile (see
        [link](http://wiki.redump.org/index.php?title=Setting_Up#CloneCD)),
        and use it for all SafeDisc dumps.
      - You're all set\! The software will handle the rest.
2.  [CD Manipulator](http://img94.imageshack.us/img94/8494/atr0.png)
      - Select "Read from CD to Image File"
      - Select the applicable drive from the drop-down list
      - Select "Single-Session mode (high compatibility)" in the
        drop-down menu
      - Specify where the image (.CUE/.CDM) will be saved
      - Check "Extended Settings" and then check "Ignore Read Errors"
        and "Auto Detect Read Channel". Uncheck everything else.
      - Set your "Data" and "Audio" speeds to 4x-8x, depending on your
        drive's compatibility.
      - You're all set\! The software will handle the rest.

### Data-Only

1.  Use BurnOut or ProtectionID to determine the SafeDisc version
2.  Use either CloneCD or CD Manipulator to dump the disc.
      - Always dump the disc twice, using different drives.
3.  Compare the checksums.
      - If they match...great\!
      - If they don't match...check your settings; try different drives;
        try different tools; ask the community.
4.  Open the image in CDMage to get the SafeDisc error count (it's
    usually helpful to save the error log).
5.  You're now ready to submit your dump\!

### Mixed-Mode

Most SafeDisc titles are data-only. However, a few mixed-mode discs
(data+audio) have been spotted in the wild. If your SafeDisc protected
disc happens to contain audio tracks...it is CRITICAL that you dump the
data portion of the image separately from the AUDIO tracks and then dump
the AUDIO tracks in the normal way. This is because the suggested
dumping software translates SafeDisc errors in a special way, and if any
SafeDisc errors are present in the audio tracks they will need to be
read "normally."

## Subs & CCDs (Optional)

Sub-headers and CCD data can be extremely useful in disc replication and
emulation. While redump does not presently archive this information, it
is generally a good idea to capture this data for personal preservation
purposes. Additional steps may be required for mixed-mode discs (i.e.
discs containing CDDA). Search the forums or ask one of the MODs for
help if you get stuck.

  - Use [CloneCD](http://www.slysoft.com/en/clonecd.html) to generate a
    valid CCD file. Be sure to use this [custom
    profile](http://wiki.redump.org/index.php?title=Setting_Up#CloneCD).
  - Use Subdump to capture highly accurate sub-header data from the
    disc. Subdump is an internal development tool, and is presently only
    available upon request. Ask a Moderator if you have interest in
    using it.

## Submission Data

Please include the following additional information with your SafeDisc
submissions in addition to the regular [Submission
Information](#Submission_Information "wikilink"):

1.  SafeDisc version
2.  SafeDisc sector count (total errors)

## Examples

  - [Sid Meier's Civilization III (USA,
    Europe)](http://redump.org/disc/20371/) (SafeDisc)
  - [Zoo Tycoon 2 (USA)](http://redump.org/disc/43148/) (SmartE)

[Category:Dumping Guides](Category:Dumping_Guides "wikilink")