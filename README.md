# Installation and Troubleshooting Guide

## Introduction
Guitar Hero II Deluxe (or GH2DX) for PS2 is playable only as an ISO running on a real PS2 or on an emulator. If you can emulate GH2, you can emulate GH2DX and even eke out extra performance from the emulator's latency controls and our own Focus Mode additions.

## Installation on Emulator
The easiest way to get GH2DX going is with an emulator, like PCSX2. They can explain how to set up their emulator best, but you'll need a PS2 BIOS, either one from your own console or one you can download online, to boot into the game. From there, boot up the ISO like any other PS2 game.

Some people find emulators to be a bit laggy and slow. You can speed the game up by using the Focus Mode modifier, which disables venue rendering. On any setlist, double-tap the Select button to access the Modifiers Menu.

To reduce audio lag, reduce the accuracy and latency of the SPU2-X plugin. These settings are found in Config > Audio (SPU2) > "Plugin Settings...". Set "Interpolation" to Nearest, "Synchronizing Mode" to None, and reduce "Latency" to about 30ms. This will reduce the lag immensely at the cost of audio quality.

PCSX2 will work with any DirectInput controller. PS2 and Wii guitars will work through adapters. We recommend Raphnet, good for Clone Hero as well as GH2DX. If your guitar doesn't work right, try another guitar, another adapter, or ask for help in our Discord (see the bottom of this readme for a link).

## Installation on Console
Running backup games (from a disc image or burned DVD-R) on a real PS2 is out of the scope of this readme, and you'll need to know a bit about your specific PS2 model anyway. A good place to start looking is the Free McBoot and FreeDVDBoot exploits, at least one of which will let you run homebrew (and thus GH2DX) on your console.

If you can already run homebrew, you have some choices as to how you want to boot GH2DX. Here's your options, in order from most to least recommended:

- **From a hard drive:** Very fast, very ideal, but takes some setup and requires one of the original "fat" PS2s with the tray loader, as opposed to the top loading "slim" models. Look into a PS2 IDE to SATA adapter and read the "WinHIIP vs. HDL DUMP" section later in this readme.
- **From your local network:** Also fast, but iffy to get working. You'll need a Network Adapter if you have a fat PS2; slim models come with ethernet built in. Windows 10 has SMBv1, which network booting solutions require, disabled by default.
- **From DVD-R:** Simple, but not ideal. Faster speedups (up to around 200%) are likely to stutter. Use good quality DVD-Rs, especially Verbatim discs. Discs have to be ESR patched before they can be booted.
- **From USB:** Stupid simple, but absurdly slow (USB 1.1 speeds), and notorious for causing FMV issues. You will almost certainly not be able to play speedups well over USB. We've had so much trouble in testing GH2DX thanks to USB **that we officially do not recommend or condone its usage**. If you have game problems and we find out you're using USB, the solution we'll give you is to boot the game using literally any other method.

## WinHIIP vs. HDL DUMP
If you've chosen to install GH2DX to your console's hard drive, you'll need to use one of two programs to get it on there, WinHIIP or HDL DUMP. We have had numerous issues getting the game to work using WinHIIP to install it, and we cannot recommend or support people using it. If you installed using WinHIIP and the game doesn't work, please try HDL DUMP or another one of the HDL-based programs.

## Debugging the Game
GH2DX 2.0 features a loader at startup with several versions of the game, two of which are marked as "debug". (Previously, you'd have to rebuild the entire disc to use these executables.) These include warnings on benign errors, a full stack trace for most crashes, and controller and keyboard "cheat" functionality.

Please note that the debug executables use different saves from the normal game executables to prevent save corruption and cheating.

Here's a not-so-exhaustive cheat sheet of some of the debug binds on controller or through a USB keyboard, if one's plugged in (on hardware) or if using a USB plugin like PCSX2 now offers out of the box:

| DualShock | Function |
| ------------- | ------------- |
| L1+L2+Left | Cycle free camera modes during songs |
| L1+L2+Up | Lighting call information print during songs |
| L1+L2+Right | Camera angle information print during songs |
| L1+L2+Down | Timers (how long the game spends during certain tasks, in ms) |
| L1+L2+Square | Tempomap debug (audible beep/fretboard bounce on downbeats) |
| L1+L2+Triangle | Progressive scan toggle |
| L1+L2+Triangle | Graphical stats (tris, meshes, mats, etc) print |
| L1+L2+Start | World rendering toggle (in essence, quick Focus Mode) |
| R1+R2+Left | Crowd likes you slightly less |
| R1+R2+Up | Fills Star Power meter |
| R1+R2+Right | Crowd likes you slightly more |
| R1+R2+Down | Empty Star Power meter |
| R1+R2+Square | Cycle autoplay modes (P1, P2, both, none) |
| R1+R2+Triangle | Win current song with five stars |
| R1+R2+Circle | Disable crowd meter altogether |

| Keyboard | Function |
| -------- | -------- |
| F4 | Lighting call information print during songs |
| F5 | Empty Star Power Meter |
| F6 | Hide gems from rendering during songs |
| F7 | Hide fretboard surface from rendering (transparent fretboard) |
| Shift-3 | Win current song with three stars |
| Shift-4 | Win current song with four stars or add $200 if in Career store |
| Shift-5 | Win current song with five stars |
| A | World rendering toggle (in essence, quick Focus Mode) |
| Shift-A | If not on a setlist, toggle access to all songs |
| B | Audible beep on downbeats |
| Shift-B | Fretboard bounce on downbeats |
| C | Cycle camera angle during songs |
| Shift-C | Camera angle information print during songs |
| E | Crowd likes you slightly less |
| Shift-E | Crowd likes you slightly more |
| F | Hide fretboard |
| Shift-F | Cycle free camera modes during songs |
| G | Toggle waypoint (guitarist walk points) visibility during songs |
| H | Hide entire HUD |
| Shift-H | Hide only HUD, but not fretboard |
| I | Enable/disable all world lighting calls |
| Shift-I | Lighting call information print during songs |
| K | Guitarist teleports randomly to another waypoint |
| L | Lose current song immediately |
| M | Disable crowd meter altogether |
| Shift-M | Toggle all game audio |
| P | Cycle autoplay modes (P1, P2, both, none) |
| Shift-P | Cycle song speeds (100%, 50%, 25%, 10%) during songs |
| Shift-R | Quickly restart current song |
| S | Scoring debug (point value, timing, accuracy of hit notes) print |
| Shift-S | Fills Star Power meter |
| Shift-T | Timers (how long the game spends during certain tasks, in ms) |
| V | Toggle static camera |
| Esc | Toggle console for running Data Array expressions interactively |

## Frequently Asked Questions
**Q: What's the long and short of what GH2DX changes?**

For completeness, see the changelog.txt included in this archive. In short, 1.0 fixes the strum limit, adds speedups, note streak popups, more songs, new art, and bass/rhythm in quickplay.

2.0 adds GH80's and GH1 in as separate campaigns, adds drums as a playable instrument, adds a streak meter and FC indicator, and overhauls the UI for that real slick shine.

**Q: What's a "strum limit"?**

In short, the game has a cooldown timer every time the player strums. Effectively, this means that you simply can't hit notes over 15nps on NTSC and 16.6nps on PAL. (This differs based on framerate, so PAL and NTSC have two different strum limits.)
   
Infamously, this affects "Trogdor", where only PAL players have ever been able to legitimately FC the song. Other songs, like "Ballroom Blitz" in 80s, require HOPOs to not top the strum limit. "Six" and "Misirlou" require much more precise timing to keep a multiplier thanks to the strum limit.
   
In March 2021, GenericMadScientist isolated and patched out the timer, killing the strum limit. The game will now accept strums once a frame, so 60nps on NTSC and 50nps on PAL. One of the initial reasons for GH2DX coming into existence was to provide a disc to the community with this fix applied.

**Q: I've found a bug or crash in GH2DX! What do I do and how can I tell you?**

Tell us in MiloHax (https://discord.gg/WWmsQvHSC6)! We distribute GH2DX through GitHub now, which means we're not bound to specific discs with specific release dates, so we can keep providing fixes should we see a need. Ideally, bring us a screenshot or photo of a stack trace if you can. You can get one of these by redoing what you did to cause the crash using the debug version of the game instead. (Check the startup loader for the debug versions.)

**Q: Why didn't you guys add the ability for me to use my Wiitar/set audio delay/[other code-only fixes]?**

There's only so much we can do here. Many of these fixes require us to be able to play with the game's executable code, which we can't do. Other systems' guitars can be used on an emulator or if pademu ever gets updated to support them. We don't write pademu. For lower latency, play on a CRT or a monitor with a 1ms response time.

**Q: I saw boxed copies of GH2DX somewhere! How can I buy one?**

Well, if you saw it from Acai's tweet or Moose's tweet, those are a few samples jnack had pressed up that he sent to people who claimed them. (Yours truly also got one :marfpeek:) GH2DX **is not** and **never will be** for sale; if you bought this disc, you got scammed. We provide the box art and disc label for you to print for yourself, so if you want copies for you and for a few friends, use a disc manufacturing service and shell out the $75 for a couple of your own. We're not selling this because it'd be morally dubious at best and blatantly illegal at worst.

### Contact
Guitar Hero II Deluxe was brought to you by some of the folks at MiloHax, dedicated to cracking open Harmonix games and stirring up what's inside. If you'd like to get in touch with us, ask for help, tell us how fantastic the results of our way too many months of hard work are, or get to work modding this game yourself, you can join the Discord at:

https://discord.gg/WWmsQvHSC6

Enjoy the disc!

- The GH2 Deluxe Team
