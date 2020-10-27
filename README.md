# re3-vita

re3-vita is a port of [re3](https://github.com/GTAmodding/re3), a full reverse engineered reimplementation of Grand Theft Auto III using librw, a full and open source reimplementation of RenderWare graphics engine.  
re3-vita allows to play Grand Theft Auto III on PS Vita/PSTV after providing game files from your own copy of the game (if you don't have a physical copy of GTA III for PC, you can buy the game on Steam (https://store.steampowered.com/app/12100/Grand_Theft_Auto_III/).

## Downloads

Check [releases](https://github.com/TheOfficialFloW/re3/releases).

## Installation

A comprehensive tutorial, wrote by Samilop Cimmerian Iter, on how to install re3-vita can be found here:
https://samilops2.gitbook.io/vita-troubleshooting-guide/grand-theft-auto/gta-iii.

## Build instructions

1. Install [vitasdk](https://vitasdk.org/).
2. Install [vitaGL](https://github.com/Rinnegatamante/vitaGL) using `make HAVE_SBRK=1 HAVE_SHARK=1 NO_DEBUG=1 install`.
3. Install [librw-vita](https://github.com/Rinnegatamante/librw-vita) using `make install`.
4. Compile re3-vita using `make`.

## Credits

- The re3 team for the incredible work done with the reverse engineering of the game.
- aap, author of re3 that gave us a huge hand improving, fixing and optimizing this port.
- AGraber for the Switch port of re3 used as original base for the port and for his Batch script used to convert audio files into uncompressed wavs easily.
- Freakler for the awesome Livearea assets
- Samilop Cimmerian Iter for the installation tutorial and extensively testing the port.

## Original README

[![Build status](https://ci.appveyor.com/api/projects/status/hyiwgegks122h8jg/branch/master?svg=true)](https://ci.appveyor.com/project/aap/re3/branch/master)
<a href="https://discord.gg/jYpXxTm"><img src="https://img.shields.io/badge/discord-join-7289DA.svg?logo=discord&longCache=true&style=flat" /></a>
| Platform | Debug | Release |
|------------------|-------------|-------------|
| Windows Direct3D9 | [![Download](https://api.bintray.com/packages/gtamodding/re3/Debug_win-x86-librw_d3d9-mss/images/download.svg)](https://bintray.com/gtamodding/re3/Debug_win-x86-librw_d3d9-mss/_latestVersion) | [![Download](https://api.bintray.com/packages/gtamodding/re3/Release_win-x86-librw_d3d9-mss/images/download.svg)](https://bintray.com/gtamodding/re3/Release_win-x86-librw_d3d9-mss/_latestVersion) |
| Windows OpenGL3.3 | [![Download](https://api.bintray.com/packages/gtamodding/re3/Debug_win-x86-librw_gl3_glfw-mss/images/download.svg)](https://bintray.com/gtamodding/re3/Debug_win-x86-librw_gl3_glfw-mss/_latestVersion) | [![Download](https://api.bintray.com/packages/gtamodding/re3/Release_win-x86-librw_gl3_glfw-mss/images/download.svg)](https://bintray.com/gtamodding/re3/Release_win-x86-librw_gl3_glfw-mss/_latestVersion) |

## Intro

The aim of this project is to reverse GTA III for PC by replacing
parts of the game [one by one](https://en.wikipedia.org/wiki/Ship_of_Theseus)
such that we have a working game at all times.

## How can I try it?

- re3 requires game assets to work, so you **must** own [a copy of GTA III](https://store.steampowered.com/app/12100/Grand_Theft_Auto_III/).
- Build re3 or download it from one of the above links (Debug or Release).
- (Optional) If you want to use optional features like Russian language or menu map, copy the files in /gamefiles folder to your game root folder.
- Move re3.exe to GTA 3 directory and run it.

## Preparing the environment for building

- Clone the repo using the argument `--recursive`.
- Point GTA_III_RE_DIR environment variable to GTA3 root folder.
- Run premake
	- On Windows: one of the `premake-vsXXXX.cmd` variants on root folder
	- On Linux: proceed to [Building on Linux](https://github.com/GTAmodding/re3/wiki/Building-on-Linux).
- There are various settings at the very bottom of [config.h](https://github.com/GTAmodding/re3/tree/master/src/core/config.h), you may want to take a look there. i.e. FIX_BUGS define fixes the bugs we've come across.
- **If you use 64-bit D3D9**: We don't ship 64-bit Dx9 SDK. You need to download it from Microsoft if you don't have it(although it should come pre-installed after some Windows version)


> :information_source: **If you choose OpenAL on Windows** You must read [Running OpenAL build on Windows](https://github.com/GTAmodding/re3/wiki/Running-OpenAL-build-on-Windows).

> :information_source: **Did you notice librw?** re3 uses completely homebrew RenderWare-replacement rendering engine; [librw](https://github.com/aap/librw/). librw comes as submodule of re3, but you also can use LIBRW enviorenment variable to specify path to your own librw.

## Contributing
Please read the [Coding Style](https://github.com/GTAmodding/re3/blob/master/CODING_STYLE.md) Document

### Unreversed / incomplete classes (at least the ones we know)
The following classes have only unused or practically unused code left:
```
CCullZone - only mobile stuff
CCullZones - only mobile stuff
```

