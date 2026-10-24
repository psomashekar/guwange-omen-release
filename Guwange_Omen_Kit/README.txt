GUWANGE: OMEN -- N64 / PS VITA PACKAGE MAKER
============================================                       (commit 296f591+changes, 2026-10-23)

Guwange: Omen is an arrangement of Cave's Guwange by Coin-Op Game Studio. This kit makes it for the
Nintendo 64 (guwange_omen.z64) and the PS Vita (guwange_omen.vpk) from your own copy of the arcade
ROM images. Both include all three modes: the original Guwange (1999), the Special / Blue Label
version (2000) and Omen. It also makes the arcade version (guwangeo.zip), from the IPS patches in
arcade/: for MAME, or to burn to EPROMs for a real Guwange board.

The kit contains no game data. Its files in kit/ are encrypted with a key computed from the contents
of the arcade ROM images: they open only with correct dumps, and the game's graphics, sound and
program are decoded from your files when the packages are made. Nothing is installed or downloaded.


WHAT YOU NEED
-------------
MAME's Guwange sets (MAME 0.287 names): "guwange" (the original) and "guwanges" (the Special
version). A merged guwange.zip holds both; split sets (guwange.zip + guwanges.zip) work too, and so
do loose files in a folder. File names do not matter: every file is found by its size and CRC32 and
checked against its SHA-1. The thirteen files:

  gu-u0127.bin    gu-u0129.bin              guwange  -- the original's program
  gu-u0127b.bin   gu-u0129b.bin             guwanges -- the Special version's program
  u083.bin u082.bin u086.bin u085.bin       sprites
  u101.bin u10102.bin u10103.bin            backgrounds
  u0462.bin                                 sound samples
  eeprom-guwange.bin                        default settings


MAKING THE PACKAGES
-------------------
Windows: put your ROM zips in the roms folder and double-click guwange-kit.exe -- or drop the zips
onto guwange-kit.exe.

From a command prompt or terminal in this folder (Linux: guwange-kit-linux; macOS:
guwange-kit-macos-arm64 on Apple silicon, guwange-kit-macos-intel on Intel Macs):

  guwange-kit                                     everything, ROMs from the roms folder
  guwange-kit n64                                 the N64 only
  guwange-kit arcade                              the MAME set only
  guwange-kit vita --roms D:\mame\roms            the Vita only, ROMs from another folder
  guwange-kit path\to\guwange.zip --out D:\out    ROMs named directly, another output folder
  guwange-kit --check                             only check the ROM sets

(macOS may refuse to start a program from the internet: right-click it, Open, then Open again.)

The packages go to the output folder: n64/, vita/, arcade/ and the manuals in manual/. Each package is
checked before it is written.


INSTALLING
----------
Nintendo 64: copy n64/guwange_omen.z64 to a flash cart (EverDrive 64 X7, SummerCart64, 64drive).
It needs the 8 MB Expansion Pak; saves go to the cartridge's EEPROM (16K, set by the image's header).

PS Vita: install vita/guwange_omen.vpk with VitaShell on a Vita running HENkaku / Enso.

Arcade: arcade/guwangeo.zip holds Omen's four ROM files, the Special (Blue Label) set's two program
ROMs and two sprite ROMs with the patches applied:

  gu-u0127b.bin  gu-u0129b.bin   program, 4 Mbit each (board locations U0127 and U0129)
  u085.bin       u086.bin        sprites, 32 Mbit each (U085 and U086)

  MAME -- MAME finds a set by its name, so copy guwangeo.zip as guwanges.zip into a folder of its
  own (say omen, beside MAME's roms folder, which keeps your untouched guwange.zip) and run
  "mame guwanges -rompath omen;roms". MAME warns about four wrong checksums: that is expected.

  The real board -- burn the four files to four ROM chips and replace the chips at those four
  locations on a Guwange Blue Label board with them.

arcade/ in the kit holds the four IPS patches, their notes (README.txt) and a preview, for patching the
Blue Label files by hand instead.

The instruction booklets for each system (English and Japanese) are in manual/.


IF SOMETHING GOES WRONG
-----------------------
MISSING -- that file was not in what you gave the kit. The list shows each file's size, CRC32 and
           set; most often it is the guwanges (Special) set's two program files.
BAD     -- a file of that name is not the right dump (an old MAME set's, a patched or damaged file).
           Get a good dump of it.


The packages you make hold data from your ROM images: they are for your own use, not for
distribution. Guwange is (c) 1999 Cave / Atlus. Guwange: Omen is a fan arrangement and is not
affiliated with them.
