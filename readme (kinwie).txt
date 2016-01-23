Salamander Drumkit SFZ
reconstructed for Plogue sforzando sample player
-----------------------------------------------------

Thanks to the author, Alexander Holm for making this great sounding drumkit available free!
But there are some player-issue when using the original included sfz file with sforzando.

So I make a reconstruction version closely follows the original version with several changes/adjustments :
- Fixed the kick's clicking noise non-destuctively witihin this sfz file, so please use the original kick samples.
- Changed snare stick and toms to random-robin (lo/hirand) instead of round-robin (seq_length/position).
- Adjusted some lorand/hirand values.
- The semi-open hihat use CC4 instead of original's cc64 and adjusted CC value : 0-open to 127-closed.
- The foot/stomp hihat also use CC4 rather than using velocity : 0-95 foot stomp (release trigger) and 96-127 foot closed.
- Added available samples : snare_OH_FF_9, hihatOpen_OH_FF_6 and cowbell_P_11. Used samples count : 535.
- Added ampeg_release to the ride2/bell for the 'off_mode=normal' use.
- Adjusted and sorted group/off_by.
- Labeling and added vol/pan control per kitpiece.

Author website :
http://rytmenpinne.wordpress.com/salamander-drumkit/

To find the samples, here :
https://archive.org/details/SalamanderDrumkit

---------------------
Enjoy!
kinwie@yahoo.com