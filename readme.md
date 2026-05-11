# The Salamander Drumkit #

Original files (including samples) from [linuxaudio.org](http://download.linuxaudio.org/musical-instrument-libraries/sfz/salamander_drumkit_v1.tar.7z) or [the Internet Archive](https://archive.org/details/SalamanderDrumkit)  (Both contain identical files except the first has a slightly expanded license description.)

(I was going to fix up the errors and make it work in sforzando, but then discovered kinwie's version which already has these things fixed and seems to work fine, so I lost motivation.)  :D

## Original README ##

> As with the salamander grand piano, this has only been properly tested on linuxsampler but it should work with other sample
> players that can load .sfz, it probably works better as it's not even half the size of the salamander piano
> It doesn't have many velocity layers, but instead many samples per velocity, in an attempt to get a more authentic sound when programming.
> The closed-hat has no less than 20 samples per velocity... only two velocity layers tho, so that makes 40 in total..
> I've actually built the drumkit myself (in 2009) It's built out of birch staves and
> has _very_ thick shells (couldn't lathe the insides) It also features an unusual one of a kind ropetuning system,
> the 12" tomtom is a prototype of another kind tho tuning system..
>
> - 12x7" racktom, Aquarian modern vintage (not the one in the picture...)
> - 14x14" floortom, Remo emperor or evans g2 can't remember for shure.
> - 18x18" kick, Remo pinstripe, Coated Ambassador on the resonant side.
> - 14x5" snare birchstaves with thin mahogany stripes, Evans power center reverse dot, Coated
> - 14x6" snare2 birch and mahogany staves, Evans genera dry Coated, with most of the muffling ring ripped off..
>
> Cymbals
>
> - Paiste 18" Innovations china (china2)
> - Paiste 18" Innovations medium crash (crash1)
> - Paiste 20" Rude thin crash (crash2)
> - Paiste 20" pst5 medium ride (ride1)
> - Paiste 8"  pst5 splash
> - Paiste 6"  accent
> - Stagg 20" SH medium ride (ride 1)
> - Stagg 14" SH hihat
> - Stagg 16" SH crash (crash3)
> - Masterworks 20" Custom china (china1)
>
>
> Licence: [CC BY-SA](http://creativecommons.org/licenses/by-sa/3.0/)
>
> The "share-alike" condition in the license only applies if you modify
> the samples themselves or create new sample libraries with them.
> Produced Music and other non-sample-library works can be licensed at will
>
> Author: Alexander Holm  
> Feel free to mail me with any questions, if you're lucky, I might just answer them ;)  
> axeldenstore (at) gmail (dot) com


# sforzando version #

`Salamander Drumkit.sfz` is a modified version for Sforzando by kinwie ([KVR Audio Forum post](http://www.kvraudio.com/forum/viewtopic.php?p=6189825#p6189825), original on [Dropbox](https://www.dropbox.com/s/i24fgjryj05w5gp/Salamander_Drumkit_sforzando.rar?dl=0)) 


## Original README ##

> Salamander Drumkit SFZ
>
> reconstructed for Plogue sforzando sample player
>
> Thanks to the author, Alexander Holm for making this great sounding drumkit available free!
> But there are some player-issue when using the original included sfz file with sforzando.
>
> So I make a reconstruction version closely follows the original version with several changes/adjustments :
>
> - Fixed the kick's clicking noise non-destuctively witihin this sfz file, so please use the original kick samples.
> - Changed snare stick and toms to random-robin (`lorand`/`hirand`) instead of round-robin (`seq_length`/`seq_position`).
> - Adjusted some `lorand`/`hirand` values.
> - The semi-open hihat use CC4 instead of original's cc64 and adjusted CC value : 0-open to 127-closed.
> - The foot/stomp hihat also use CC4 rather than using velocity : 0-95 foot stomp (release trigger) and 96-127 foot closed.
> - Added available samples : `snare_OH_FF_9`, `hihatOpen_OH_FF_6` and `cowbell_P_11`. Used samples count : 535.
> - Added `ampeg_release` to the ride2/bell for the `off_mode=normal` use.
> - Adjusted and sorted group/off_by.
> - Labeling and added vol/pan control per kitpiece.
>
> Author website :
> http://rytmenpinne.wordpress.com/salamander-drumkit/
>
> To find the samples, here :
> https://archive.org/details/SalamanderDrumkit
>
> ---------------------
> Enjoy!
> kinwie@yahoo.com

## Salamander Drumkit Trim.sfz by Jesse Chappell

The original audio files in the above archives included some silent audio before the drum hits in almost all samples, causing unnecessary latency. Here is a ZIP with an edited set of the audio files from essej with the extra silence trimmed from them. They also correct some end of sample issues. So use the `Salamander Drumkit Trim.sfz` file instead when using the modified samples, which removes the unnecessary fixes made previously for the kick end offset. - [Trimmed Files](https://drive.google.com/file/d/1K1gbuUhSqlMem2sZI48NHSrqdJ6Uheh8/view?usp=sharing).  [`salamanderDrumkitSamplesFixedOnsets.zip` 385M MD5: 8080018e91ad940efd884dde65bad207]

## StudioRack (Open Audio Stack) discovery

[StudioRack](https://github.com/studiorack/studiorack) indexes GitHub repositories that are tagged with the [`studiorack-plugin`](https://github.com/topics/studiorack-plugin) topic and that publish a GitHub **Release** whose assets include a file named exactly **`plugins.json`** (alongside the downloadable package). The crawler loads metadata from:

`https://github.com/<owner>/<repo>/releases/download/<tag>/plugins.json`

This repository includes a root-level [`plugins.json`](plugins.json) you can upload unchanged **after** editing the `version`, `date`, and each `files.*.size` field to match the byte sizes GitHub shows for your release assets.

For each release, attach at minimum:

1. **`plugins.json`** — same shape as in this repo; `files.linux`, `files.mac`, and `files.win` must reference a **`.zip`** asset on that same release (the same archive for all three is fine for SFZ + WAV data).
2. **`SalamanderDrumkit.zip`** — zip containing the SFZ files from this repository plus the `.wav` sample tree from the [Internet Archive](https://archive.org/details/SalamanderDrumkit) (or another licensed copy of the kit). SFZ paths must match the layout inside the zip.
3. **`SalamanderDrumkit.jpg`** — small cover or kit photo (StudioRack’s validator prefers JPEG previews).
4. **`SalamanderDrumkit.flac`** — a short audio preview (FLAC is the format their tooling recommends).

Then add the **`studiorack-plugin`** topic to the repository on GitHub (About → Topics). The [studiorack-registry](https://github.com/studiorack/studiorack-registry) job merges `plugins.json` with release assets; indexing runs on a daily schedule.

**License on GitHub:** the registry rejects `license: other`. Set a repository license in GitHub that maps to a SPDX id StudioRack knows (for example **CC BY-SA 4.0** for this repo’s combined metadata and SFZ text, while keeping the original sample licensing described in the Original README above), so the API does not report a null license.

YAML is used by the separate [Open Audio Stack registry](https://github.com/open-audio-stack/open-audio-stack-registry) for packages they host directly; for StudioRack’s GitHub-based flow, **`plugins.json` on the release** is the file their indexer expects.
