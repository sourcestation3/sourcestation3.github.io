---
layout: post
title:  "To Mod Portal 2"
---

Fair warning: This article will be a bit rough around the edges. Portal 2 has incredible modding potential, but takes a fair bit more effort. Regardless, we do have the technology and tools to make something beautiful out of this game yet.

Portal 2 uses a special kind of zip file to store information. Some files (videos, maps, binaries) aren't shipped using these zips, and those filetypes must always exist outside the ZIP format. Others MUST exist in zip format for them to be mounted. So, how do we modify these zips?

On our tools page, you can find a tool called vXZip which can extract AND create these zip files. Also note, they are loaded in order, and you can have up to 100 (`zip0.ps3.zip` up to `zip99.ps3.zip`). Anything you add into a later zip number (like zip1) will override the same file in a lower zip (like zip0). This is useful because it means you do not have to edit the large, stock zips, which can take a while to transfer over to PS3. Using this trick, you can edit many files, such as the control configs. Some files are PS3 specific and will be tricky with vXZip alone, however.

This is what MakeGameData is for. MakeGameData is an official tool used by Valve when creating this port that directly converts PC models to 360/PS3 models. There is a game on Steam called Dino D-Day which has this tool included in its SDK. It is a bit cumbersome to set up, however.

To set up MakeGameData, you must first create a folder on your PC called "game". Inside this folder, make another folder called "bin", and copy all the files from Dino D-Day's bin folder into there. Then, from the "game" folder, you make another folder, call it whatever you want, but make sure that there is a valid gameinfo.txt file in there (just steal from Portal 2 PC), otherwise MakeGameData won't work. All your game assets go in this folder. VPKs are **not** processed by MakeGameData, so you will need to extract all the files from the VPKs using a tool such as [GCFscape](https://developer.valvesoftware.com/wiki/GCFScape) or [Crowbar](https://developer.valvesoftware.com/wiki/Crowbar). After this, in the folder you extracted the game assets to, open a command prompt. I recommend using this trick, but type "cmd" rather than "wt":

![](../postassets/old/cmd.gif)

Inside this command prompt, run the following command:

`..\bin\makegamedata.exe *.* -ps3 -r -z zip0.ps3.zip`

**Note:** You can adjust these switches to taste if needed. `*.*` grabs all files that can be converted, `-ps3` sets the target machine to PS3 (otherwise it builds for Xbox 360), `-r` scans folders within the folder (so, you can just copy the entire game directory and it will convert everything). `-z zip0.ps3.zip` creates a zip named `zip0.ps3.zip` containing all files that need to be in a zip file to work.

Also, the zip will only generate correctly if you grab the game files from the correct directory. For Half Life 2, this is `hl2`, for Portal 2, this is `portal2`. You can also grab the DLC and localization folders if you so desire, but they may need to be processed separately.

Please note, all these tools can be finicky. But they're what we have, they're capable, and [Relt got the mod Portal Reloaded to PS3 using the Dino D-Day MakeGameData tool](https://www.youtube.com/watch?v=xN82N-7FiGU). With enough trial and error, you can likely achieve something wonderful too.