---
layout: post
title:  "[Portal 2] Video Guide to porting to PS3"
---

I've created a video guide to porting content to the PS3. You can watch it here through YouTube:

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/XO9JHZrGh3o?si=-8QX0pEK3uNzm9mQ" title="YouTube video player" frameborder="0" allow="clipboard-write; encrypted-media; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[<kbd> <br> Alternatively, click here to view the video on YouTube directly. <br> </kbd>][https://www.youtube.com/watch?v=XO9JHZrGh3o]

[https://www.youtube.com/watch?v=XO9JHZrGh3o]: # 'Link with example title.'

Here's the video description as of publishing this post (July 26 2024):

> Here's the command for command prompt:
>
> `..\bin\makegamedata.exe *.* -ps3 -r -z zip3.ps3.zip`
>
>If you want to adjust this, \*.\* is a wildcard meaning "all file names of all extensions", so file.* would search for files named "file", and *.bsp would only convert BSP files
>
>-ps3 compiles for PS3 (otherwise it compiles for 360)
>
>-r (Recursive) scans folders inside the current directory (otherwise it won't scan maps folder etc)
>
>For scenes, run the following before running the above command:
>
>`..\bin\makegamedata.exe -scenes -ps3`
>
>I don't know if it does anything useful, though. I have a feeling it might help with some of the cutscenes?? maybe?


And here is how the MakeGameData tool describes its options: 
```
[-v]                    Version
[-q]                    Quiet (critical spew only)
[-h] [-help] [-?]       Help
[-t targetPath]         Alternate output path, will generate output at target
[-r] [-recurse]         Recurse into source directory
[-f] [-force]           Force update, otherwise checks timestamps
[-test]                 Skip writing to disk
[-z <zipname>]          Generate zip file AND create or update stale conversions
[-preloadinfo]          Spew contents of preload section in zip
[-kvinfo]               Spew contents of kvpool in zip
[-xmaquality <quality>] XMA Encoding quality override, [0-100]
[-scenes]               Make Xbox 360 scene image cache.
[-pcscenes]             Make PC scene image cache.
[-usemaplist]           For BSP related conversions, restricts to maplist.txt.
[-files <script>]       Restricts processing to files specified in script.
[-zipformat]            Compatible zip format (Allows WinZip viewing)
[-audiocache]           Make PC audio _master.cache file.
[-updateaudiocache]     Update PC audio _master.cache file w/ new or changed .wav files.
[-language <name>]      Build _master_name.cache language specific cache file.
[-ps3]                  Build for Sony PS3
[-sonyps3]              Build for Sony PS3
[-cert]                 CERT build, uses environment VPC_AUTO_ARGS or VPC_CONSOLE_ARGS
```