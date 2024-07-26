---
layout: post
title:  "[Orange Box] Initial Datamining Observations"
---

This post assumes you already know at least a little bit about the Source Engine and filesystem, if not that's ok but prepare to be a little confused.

Before 2013, Source Engine games were all packed together and used one game directory with different folders for individual games. Half-Life 2 and its episodes, together with Half-Life Source, still do this somewhat: 

![Picture of the HL2 game directory](../postassets/old/hl2.png)

The Orange Box follows this convention on Xbox 360, the port handled by Valve. The PS3 port, on the other hand, takes a different approach: 

![Screenshot of the PS3 folder showing 4 directories: BIN, CONTENT, FILEGROUPS, GAME, and one file, EBOOT.BIN](../postassets/old/ps3filestruc.png)

The entire disc is in all caps. Underneath BIN are some .SELF files, presumably executables for the PS3. The CONTENT folder contains some images for the XMB, likely the images used for save icons as the XMB loads a different file for discs.

FILEGROUPS is where things get strange. Each game in the Orange Box has its own sub-folder, and in each folder are files named after each map: 

![GRP files with names following different maps.](../postassets/old/ps3filegroups.png)

This .GRP extension is used in various different software, most certainly is NOT a "Microsoft Program Group" as Windows states, and through some cursory internet searching appears to be a file format many PS3 games use which presumably contain game assets. I was not able to find a program to open these, however. These games were always meant to have one shared asset pool; separating assets by map results in a lot of duplicate files, which results in the game taking up a whopping 17 gigabytes of disc space. Not so impressive nowadays, until you realize the Xbox 360 version, which is *the exact same collection*, takes up only 6GB. The 360 can't even have games on a single disc this big in size, as it requires Blu-ray (or second disc) to store above 8GB. Anyways, as a consequence of this arbitrary format, it is currently not possible to add new assets to the game through modding, as the tools to create this format do not exist as far as I can tell.

Moving over to the GAME folder, we have the same format of each game getting a different sub-folder, albeit with the addition of a MOVIES folder. These are presumably all the different videos that play in the game selection menu, but they are in an arbitary PS3-exclusive PAM format so can't be viewed or altered. This is compared to the 360 which stores these same clips in .wmv format.

The individual game sub-folders have this format: 

![Screenshot showing the folders CFG, MAPS, SAVECONTENTPS3, and GAMEINFO.XTX](../postassets/old/ps3gamesfolder.png)

GAMEINFO.XTX is the same format as PC, with the exception of this `type` line which is either set to `singleplayer_only` or `multiplayer_only` (TF2). Not entirely sure what that switch does yet. This flag is also present on 360.

the CFG folder contains a single file called CONFIG.PS3.CFG, which contains default controls as well as some ConVar adjustments, such as enabling autoaim or lowering the amount of damage taken (presumably to compensate for slower controller aim). All controller binds use the names for the 360 buttons, and the controller name is set to "Xbox controller". Curiously, there are also some cheat binds for buttons such as "A_BUTTON_2". Obviously 360 and PS3 controllers don't have these mysterious secondary A buttons, so I do wonder how these were ever triggered. "START_2" is bound to "debug_NewLevelDialog", which I did attempt to bind to an actual button - this menu, whatever it was, no longer works in retail copies.

SAVECONTENTPS3 are just pictures used as the icons and backgrounds for savegames on the XMB.

MAPS contains all the maps for the game, all in all caps, all ending in `.PS3.BSP`. These maps are entirely different than their 360 counterparts, and most likely do not follow the same format as later Valve PS3 games, meaning they would need a special tool to be made. This tool isn't available to the public as far as I can tell, and it is debatable whether it still exists at all. Somehow I doubt EA has kept everything PS3 related after all this time.

All in all, this port will be extremely difficult to mod beyond binds compared to its 360 counterpart. Portal 2 and CS:GO, on the other hand, are very similar across both consoles, and significant progress has been made in that direction.