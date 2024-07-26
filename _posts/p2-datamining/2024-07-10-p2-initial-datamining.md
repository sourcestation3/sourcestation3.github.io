---
layout: post
title:  "[Portal 2] Initial Datamining Observations"
---

Compared to the bizzare file layouts seen in The Orange Box, the Portal 2 port is very conventional:

![layout of the PS3 disc](../postassets/old/filestruc.png)

`EBOOT.BIN` is presumably a required file to launch the game, while `bin` contains some PS3 executables in the `.sprx` format. 

This port also makes use of some `.zip` files, which presumably take the place of VPK files as the pakfiles of choice. Pakfiles are used because it is faster to load one big file than a bunch of small files. These `.zip` files are a little strange; they cannot be opened by Windows file explorer, but can be opened (and have files extracted) by 7-zip. However, 7-zip CANNOT create a zip file that is accepted by the game. The format was customized slightly, and you will need [vXZip](https://github.com/CRACKbomber/vxzip) to be able to modify these zips.

The `platform` folder is relatively uninteresting, with a zip holding engine placeholders (for example, the "Oh, fiddlesticks" sound that plays when a sound is missing), but does have fonts used by the game menus outside of the zip under `platform/vgui/fonts`. Presumably, this means the game CAN see all files outside of ZIPs, but chooses not to use them.

Inside the main `portal2` folder, we have the following arrangement:

![has folders BIN, MAPS, and MEDIA, a single gameinfo.xtx file, and 3 ZIP files.](../postassets/old/portal2folder.png)

As usual, most of the game is contained inside ZIP folders, with the exception of maps and videos, which presumably are large enough on their own not to benefit from filepacking. Videos are in .BIK format, which was added to Source in 2011 specifically for the monitors in Portal 2. It is also used for several cutscenes and the intro Valve logo, and can be viewed in VLC. Maps are still `.ps3.bsp` files and need a special tool called MakeGameData to convert to PS3. This was an internal Valve tool, and a PS3-compatible version of it is currently available in the SDK for the game Dino D-Day.

The folders for French, German, Russian, and Spanish all contain subtitles and dubs for those versions, including a few cutscene videos. Overall, not very interesting. 

However, can the game run without zip files?

After extracting each zip file to its rightful place, I ran the game, and after playing through the intro Valve logo, the game freezes. When the game freezes, it also makes the XMB inaccessible. You have to restart the entire console by pressing the power button, which for some reason causes the PS3 to beep 3 times. I assume this means when the game freezes, the OS also freezes? I'm not really sure what's going on here.

Anyways, this game is significantly more moddable than the Orange Box, but it is simultaneously a lot more difficult to properly crack open. The tools luckily do exist, but they can be cumbersome. Still, the tools here at least exist, which is more than I can say for Orange Box.