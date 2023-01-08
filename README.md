# Guitar Hero II Deluxe

           ____       _ _               _   _                  ___ ___
          / ___|_   _(_) |_ __ _ _ __  | | | | ___ _ __ ___   |_ _|_ _|
         | |  _| | | | | __/ _` | '__| | |_| |/ _ \ '__/ _ \   | | | |
         | |_| | |_| | | || (_| | |    |  _  |  __/ | | (_) |  | | | |
          \____|\__,_|_|\__\__,_|_|    |_| |_|\___|_|  \___/  |___|___|
                        ____  _____ _    _   ___  _______
                       |  _ \| ____| |  | | | \ \/ / ____|
                       | | | |  _| | |  | | | |\  /|  _|
                       | |_| | |___| |__| |_| |/  \| |___
                       |____/|_____|_____\___//_/\_\_____|

                     Installation and Troubleshooting Guide
===============================================================================

INTRODUCTION
============
This document contains important information for playing, enjoying, and
troubleshooting Guitar Hero II Deluxe. Please read this document carefully
and keep handy for future reference.

Guitar Hero II Deluxe (or "GH2:DX") is distributed as a disc image in the ISO
format. An emulator or a PlayStation®2 console capable of running homebrew is
required to play. System requirements for GH2:DX are identical to that of the
vanilla game; if you can emulate Guitar Hero II, you can emulate GH2:DX.
GH2:DX features lag mitigation options to dramatically increase emulator
performance, and this document explains how to reduce the audio lag as well.

INSTALLATION ON EMULATOR
========================
The simplest method for playing GH2:DX is with an emulator, like PCSX2.
Emulator setup is best explained by their official documentation, though
you'll need a PlayStation®2 BIOS file, either extracted from your own
console or found online, to boot into a game.

Some people find playing on emulator to be a fairly laggy (and in some cases
slow) experience, not ideal for a rhythm game. GH2:DX features a "focus mode"
from the Modifiers Menu that disables world rendering, thus speeding up
performance. Double-tap the Select button from any setlist to access it.

For audio lag (which PCSX2 is infamous for), you can reduce the accuracy and
latency of SPU2-X to make the game feel much more responsive. Setting
"Interpolation" to Nearest, "Synchronizing Mode" to None, and "Latency"
to ~30ms will reduce the lag immensely at the cost of audio quality. These
settings are found in Config > Audio (SPU2) > "Plugin Settings...".

PCSX2 will work with any DirectInput controller. Guitars for PlayStation®2
or Wii consoles will work through adapters. We recommend Raphnet adapters,
good for both PCSX2 and Clone Hero. If your guitar doesn't work completely
with it, try another guitar, adapter, or ask for help in our Discord.

INSTALLATION ON CONSOLE
=======================
Running backup games (from a disc image or DVD-R) on a PlayStation®2 is out
of the scope of this document, and nevertheless requires knowledge of your
specific model of console. We direct you to look up information about the
FreeMcBoot and FreeDVDBoot exploits, at least one of which will let you run
homebrew on your specific console--and thus, run GH2:DX.

If your console IS homebrew-capable, you can run GH2:DX in one of a few ways.
These all apply to different models, have different means of setup, and load
at drastically different speeds.

- From the PlayStation®2 HDD: This is the most ideal way to run the game,
  with one major caveat: it's only available to the original "fat" consoles
  with the tray loader. If you have a "slimline" model that loads discs from
  the top of the console, you can't make use of the HDD without physically
  modifying your console, and that's assuming you have the first slim model.

  That said, if you have a "fat" PlayStation®2, the HDD will give you the
  fastest speeds and the most ideal experience, especially when playing
  speedups. Look into a PlayStation®2 SATA adapter (and a matching hard
  drive--250GB should be plenty) and Open PS2 Loader, and see the section
  "WinHIIP vs. HDL Dump" later in this document.

- From your local network: All PlayStation®2 consoles feature an ethernet
  port on the back of the unit. Aside from the HDD, this is the fastest way
  to load backup games. The caveat is that it requires your console be
  connected to the router in your house, naturally, and that your computer
  can communicate over SMBv1, which Windows 10 has since disabled. Network
  loading is finicky for even our modders, so be warned.

- From DVD-R: Decent, if not ideal, with two major caveats. For one, the game
  doesn't run quite as fast as over HDD, fast enough for regular speed play,
  though not quite for full-throttle (200% and higher) speedups. DVD-Rs also
  run the risk of wearing out your console's laser faster, as bad quality
  burns require more focusing power. Look into ESR if you plan on using
  DVD-Rs, as discs require patching before use.

- From USB: The simplest option, but unfortunately the worst. Open PS2 Loader
  CAN load loose ISOs from a USB drive--at USB 1.1 speeds. This is about half
  the data transfer rate of the disc drive, and is notorious for causing
  skips in audio and FMVs and especially slow load times in nearly every
  game. We DO NOT recommend using USB to play GH2:DX, at ANY speed.

WinHIIP VS. HDL DUMP
====================
If you've chosen to install GH2:DX to your console's HDD, you'll likely use
some kind of program on your computer to more quickly install disc images to
it. Often, this is a program called WinHIIP. Unfortunately, we've had many
issues relating to the way WinHIIP recognizes games on install during our
testing, and while we work around it, we don't recommend it.

GH2:DX includes an ELF (the PS2's executable format) named "SLES_666.66"
in the files alongside the other executables, which works around WinHIIP
detecting GH2:DX as the wrong game and leading many of our testers to
experience blank screens on bootup. If you have any further issues, we
can't overstate it enough: use HDL DUMP to load images on your HDD instead.

DEBUGGING THE GAME
==================
GH2:DX 2.0 features a loader with several versions of the game, two of which
are marked as "debug". (Previously, you'd have to rebuild the entire disc to
use these executables.) These include warnings on benign errors, a full stack
trace for most crashes, and controller and keyboard "cheat" functionality.

Please note that the debug executables use different saves from the normal
game executables to prevent save corruption and cheating.

Here's a not-so-exhaustive cheat sheet of some of the debug binds on
controller or through a USB keyboard, if one's plugged in (on hardware) or
if using a USB plugin like PCSX2 now offers out of the box:

DualShock       Function
---------       --------
L1+L2+Left      Cycle free camera modes during songs
L1+L2+Up        Lighting call information print during songs
L1+L2+Right     Camera angle information print during songs
L1+L2+Down      Timers (how long the game spends during certain tasks, in ms)
L1+L2+Square    Tempomap debug (audible beep/fretboard bounce on downbeats)
L1+L2+Triangle  Progressive scan toggle
L1+L2+Triangle  Graphical stats (tris, meshes, mats, etc) print
L1+L2+Start     World rendering toggle (in essence, quick Focus Mode)
R1+R2+Left      Crowd likes you slightly less
R1+R2+Up        Fills Star Power meter
R1+R2+Right     Crowd likes you slightly more
R1+R2+Down      Empty Star Power meter
R1+R2+Square    Cycle autoplay modes (P1, P2, both, none)
R1+R2+Triangle  Win current song with five stars
R1+R2+Circle    Disable crowd meter altogether

Keyboard   Function
--------   --------
F4         Lighting call information print during songs
F5         Empty Star Power Meter
F6         Hide gems from rendering during songs
F7         Hide fretboard surface from rendering (transparent fretboard)
Shift-3    Win current song with three stars
Shift-4    Win current song with four stars or add $200 if in Career store
Shift-5    Win current song with five stars
A          World rendering toggle (in essence, quick Focus Mode)
Shift-A    If not on a setlist, toggle access to all songs
B          Audible beep on downbeats
Shift-B    Fretboard bounce on downbeats
C          Cycle camera angle during songs
Shift-C    Camera angle information print during songs
E          Crowd likes you slightly less
Shift-E    Crowd likes you slightly more
F          Hide fretboard
Shift-F    Cycle free camera modes during songs
G          Toggle waypoint (guitarist walk points) visibility during songs
H          Hide entire HUD
Shift-H    Hide only HUD, but not fretboard
I          Enable/disable all world lighting calls
Shift-I    Lighting call information print during songs
K          Guitarist teleports randomly to another waypoint
L          Lose current song immediately
M          Disable crowd meter altogether
Shift-M    Toggle all game audio
P          Cycle autoplay modes (P1, P2, both, none)
Shift-P    Cycle song speeds (100%, 50%, 25%, 10%) during songs
Shift-R    Quickly restart current song
S          Scoring debug (point value, timing, accuracy of hit notes) print
Shift-S    Fills Star Power meter
Shift-T    Timers (how long the game spends during certain tasks, in ms)
V          Toggle static camera
Esc        Toggle console for running Data Array expressions interactively

FREQUENTLY ASKED QUESTIONS
==========================
Q: What's the long and short of what GH2:DX changes?
   For completeness, see the changelog.txt included in this archive. In
   short, 1.0 fixes the strum limit, adds speedups, note streak popups, more
   songs, new art, and bass/rhythm in quickplay.

   2.0 adds GH80's and GH1 in as separate campaigns, adds drums as a
   playable instrument, adds a streak meter and FC indicator, and overhauls
   the UI for that real slick shine. Go play 3.0 on Xbox 360.

Q: What's a "strum limit"?
A: In short, the game has a cooldown timer every time the player strums.
   (52ms, if you're curious.) Effectively, this means that you simply can't
   hit notes over 15nps on NTSC and 16.6nps on PAL.
   
   Infamously, this affects "Trogdor", where only PAL players have ever been
   able to legitimately FC the song. Other songs, like "Ballroom Blitz" in
   80s, require HOPOs to not top the strum limit. "Six" and "Misirlou"
   require much more precise timing to keep a multiplier thanks to the strum
   limit.
   
   In March 2021, GenericMadScientist in our Discord isolated and patched out
   the timer, killing the strum limit. The game will now accept strums once a
   frame, so 60nps on NTSC and 50nps on PAL. One of the initial reasons for
   GH2:DX coming into existence was to provide a disc to the community with
   this fix applied.

Q: I've found a bug or crash in GH2:DX! What do I do and how can I tell you?
A: Well, you can tell us in the MiloHax Discord if you really want to. We
   won't be fixing it, seeing as 2.0 is basically final. Show us a photo or a
   screenshot of a stack trace if you do, please. You can get one of these
   by redoing what you did to cause the crash using the debug version of the
   game instead. (Check the startup loader for the debug versions.)

Q: Why didn't you guys add the ability for me to use my Wiitar/set audio
   delay?
A: There's only so much we can do here, and only so much we WANT to do here.
   Other systems' guitars can be used on an emulator or if pademu ever gets
   updated to support them. We don't write pademu. Go bother the people who
   do. Audio delay, same deal. Play on a CRT or a 1ms monitor.

Q: I saw boxed copies of GH2:DX somewhere! How can I buy one?
A: Well, if you saw it from Acai's tweet or Moose's tweet, those are a few
   samples jnack had pressed up that he sent to people who claimed them.
   (Yours truly also got one :marfpeek:) GH2:DX IS NOT and NEVER WILL BE for
   sale; if you bought this disc, you got scammed. We provide the box art
   and disc label for you to print for yourself, so if you want copies for
   you and for a few friends, use a disc manufacturing service and shell out
   the $75 for a couple of your own. We're not selling this because it'd be
   morally dubious at best and blatantly illegal at worst.

Q: I don't like the note colors, change them back because I said so!
A: Free Play > Extras > GRYBO Gems. You're welcome.

CONTACT
=======
Guitar Hero II Deluxe was brought to you by some of the folks at MiloHax,
dedicated to cracking open Harmonix games and stirring up what's inside. If
you'd like to get in touch with us, ask for help, tell us how fantastic the
results of our way too many months of hard work are, or get to work modding
this game yourself, you can join the Discord at:

https://discord.gg/TPycZbVeqY

Enjoy the disc!

- The GH2 Deluxe Team
