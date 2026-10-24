GUWANGE: OMEN  (an arrangement of Guwange Blue Label)  v2.8
======================================================
Arranged by Coin-Op Game Studio.

Target: Guwange (Japan, 2000 7/ 7 Special Ver 13:22), MAME set "guwanges".
Four files change: the two Blue Label program ROMs and two sprite ROMs.

  file            original CRC32   patched CRC32
  gu-u0127b.bin   64667d2e         d45a2c5d
  gu-u0129b.bin   a99c6b6c         628799fd
  u086.bin        188e4f81         e9f1203b
  u085.bin        a7d5659e         977d10ea

Sound, layer graphics and the original-version ROMs are untouched.


WHAT IT CHANGES
---------------
New in v2.8

- The COIN-OP GAME STUDIO logo screen after the WARNING screen, ported
  from the N64 version (same art, same timing): on black, the logo fades
  in over 40 frames, PRESENTS is typed under it a letter every 6 frames, it
  holds for 150 frames and fades out over 40 (3.8 seconds). Pressing any
  button skips straight to the fade-out. Then the attract continues as
  before (ranking, ATLUS, CAVE, title).
- Ending credits: the last card (PRESENTED BY CAVE 1999 THE END) now also
  reads ARRANGED BY / COIN-OP / GAME STUDIO under THE END, lettered with
  the credits' own font and colours, so it fades in and out with the card.

New in v2.7

- A designed red palette instead of a tint. Each character's clothing
  colours are swapped for a hand-built crimson ramp (dark maroon shadows
  leaning slightly purple, crimson mid-tones, warm scarlet highlights);
  each original shade takes the place on the ramp that matches its
  brightness, so the shading carries over. Skin, hair, metal, gold, the
  shikigami and the font keep their original colours.
  - In play: one 16-colour ramp per character is swapped (character 1's
    blue garments, character 2's lavender skirt, character 3's orange
    outfit), in all three time-of-day palettes. Nothing else changes.
  - Player select (highlighted character): the garment colours fade into
    the same ramp by hue (blue gi, blue hakama, yellow robe).
  - Ranking screen: saturated colours move onto a darker version of the
    ramp; greys and the heading keep their colours.
- Fixed: the copyright/warning screen text was tinted red in v2.6 (it uses
  the same palette as character 2). It's back to its original colours.

New in v2.6

- The red is now a real tint. v2.1-v2.5 replaced each colour's hue with a
  set of rules (keep skin, keep gold, special case for pale colours, a
  minimum saturation), and neighbouring shades could fall under different
  rules, which broke smooth gradients into bands and speckle. Now every
  colour goes through one continuous formula: its brightness is coloured
  crimson and blended 80/20 with the original. Shading stays smooth and in
  the same order as the original art.
  Applies to: the characters, shikigami and HUD portraits in play, the
  highlighted character on the player select, and the ranking screen's
  banners and strips (darker blend there, 90%).

New in v2.5

- Player select: the characters you aren't highlighting are back to their
  normal colours, and the highlighted character (and their shikigami) is
  shown in Omen red. The unpicked characters are painted into the
  backdrop and share its palette, so the backdrop is Blue Label's original
  again (it's already a dark red temple).

New in v2.4

- Fixed: the high-score screen ran at about half speed while it faded in
  and out (v2.3 recoloured every colour as it was written). The maroon is
  now built into the ROM: the screen's own fade script points at maroon
  copies of its banner and strip colours, so the game fades straight into
  them. It runs exactly as fast as the original.

New in v2.3

- Hitbox marker priority: the marker is now drawn as part of the player,
  with the player's own sprite priority, right after the player's body. It
  sits on the player but goes under anything that covers the player
  (explosions, effects), instead of over everything.
- Player select: the highlighted character and the shikigami floating
  behind them are red too (they used to show their normal colours).
- High-score (ranking) screen: the coloured banners and checkered strips
  are deep maroon, matching the title. The text keeps its gold and white,
  and the screen's fades still work.

New in v2.2

- OMEN X2 is easier to hold in dense sections: each graze now adds 10
  frames (was 6) and each slowed-bullet graze 20 frames (was 12).

New in v2.1

- Red uniforms: all three characters, their shikigami and their HUD
  portraits use the Omen crimson in every stage's palette. Skin, hair, gold
  trim, greys and whites are kept so the characters still read clearly.
- Hitbox marker: a white dot with a red ring is drawn on each player
  during play. The white core is the size of the real 6x6 px hitbox.
- Easier skull meter:
  - Grazing holds the meter: after any graze the meter can't drain for
    30 frames (half a second), so dense bullet sections keep it up.
  - The meter drains at half speed the rest of the time.
  - Shot kills give half a skull (8 units) instead of a quarter.
  - Grazes give 3 units (was 2); slowed-bullet grazes give 6 (was 4).
  In the same scripted test run, the meter spent 37% of play at 6+ skulls
  (graze range) versus 2% in v2.0.
- Kyocho tint: while OMEN X2 is active the background darkens to a deep
  red-brown (sprites, bullets and the HUD sprites keep their colours). It
  fades in over half a second and the normal colours come back when it ends.

Gameplay: the v2.0 rules

A. Shot kills fill the meter slowly
   In Blue Label every enemy your regular shot kills adds a whole skull, so
   the meter is nearly free. In Omen a shot kill adds half a skull (a quarter
   for the enemy types that used to give half; v2.0 used a quarter/eighth). Grazing and
   cancelling are now the main ways to fill it.

B. Local cancels and chains
   A shikigami kill no longer wipes every slowed bullet on screen. It only
   cancels slowed bullets within 56 px of the enemy that died (a 112 px
   square around it). Tag separate clusters, graze them, then pop each one
   by killing an enemy near it.
   Pops chain: if you pop another cluster within 1.5 seconds (90 frames),
   it's chain 2, then chain 3, and so on. Each chained pop spawns bonus
   coins equal to (bullets cancelled) x (chain - 1), up to 20 per pop.
   A pop that cancels nothing doesn't break or extend the chain.

C. Kyocho (ill omen) at a full meter
   With the shikigami out and the meter at 10 full skulls, your next graze
   starts Kyocho. "OMEN X2" appears above your life bar.
   - Every graze pays double coins (ordinary 2, slowed 6).
   - It lasts 2.5 seconds (150 frames). Each graze adds 10 frames, each
     slowed-bullet graze 20 frames, up to 5 seconds. To break even you need
     about 6 ordinary or 3 slowed-bullet grazes a second (v2.1: 6/12).
   - The indicator blinks in the last second.
   - If the timer runs out you lose 2 skulls.
   - Releasing the button ends Kyocho straight away, with no penalty.
   You keep it going only by grazing faster than it runs down.

Gameplay: the v1 rules (still in v2.0)

How Blue Label already works (for reference): while the shikigami is out,
the skull meter fills. Once it reaches 6 skulls you can graze, and the graze
box grows with each extra skull. Every graze spawns a coin that adds to your
gold chain. Ordinary bullets can be grazed up to 3 times each; a bullet the
shikigami has slowed can be grazed only once. Killing something with the
shikigami turns every slowed bullet into a coin (in Omen v2.0, only the
nearby ones; see B).

1. Tagged bullets pay more
   Grazing a bullet your shikigami has slowed spawns 3 coins instead of 1,
   and refills more skull meter (6 units instead of 3). It's still one
   graze per tagged bullet, so it can't be farmed.

2. Cancel bursts refill the skull meter
   When a shikigami kill cancels slowed bullets, each cancelled bullet adds
   2 units to the meter. Bursts of 10 or more get +8 units, and bursts of 25
   or more get another +16. One burst is capped at 48 units (3 skulls). The
   bullets still turn into coins exactly as before.

3. Grazing slows the skull drain
   Every graze adds 3 units back to your meter (and, from v2.1, stops the
   drain for half a second). This only works while the
   meter is running and never pushes it past 10 skulls. It gives you a
   reason to keep dodging close.

(16 units = 1 skull. In Blue Label the meter drains about 1 unit every
1-2 frames; v2.1 halves that.)

Everything else, including Blue Label's existing rules, is unchanged.

Graze distance (Blue Label's own table, unchanged by Omen). Your hitbox is
a 6x6 px square; grazing counts any bullet whose centre is inside a larger
square around it:

  shikigami OUT (button held)        shikigami IN (button released)
  skulls  graze square               skulls  graze square
  0-5     no graze                   0-9     no graze
  6       42 x 42 px                 10      46 x 46 px
  7       48 x 48 px
  8       54 x 54 px                 With the shikigami in, slowed bullets
  9       60 x 60 px                 can't be grazed at all; only ordinary
  10      66 x 66 px                 bullets count.

So the slowed-bullet bonus only pays while you keep holding the button.

Presentation

- Title screen: the forest is deep maroon instead of Blue Label's blue.
  (Blue Label makes its title blue by swapping the red and blue channels of
  the original sunset palette as it fades in; Omen replaces that step with a
  maroon version. Nothing outside the title screen is recoloured.)
- An "OMEN" logo sits at the top left of the title, next to the GUWANGE
  calligraphy, on both the attract title and the PRESS START screen.
- "ARRANGED BY COIN-OP GAME STUDIO" runs along the bottom of the title.
- Boot warning screen: the copyright line now reads
  ARRANGED BY COIN-OP GAME STUDIO, the version line reads 2026 10/16 OMEN,
  and the original (C)ATLUS/CAVE 1999 credit moves to the bottom.
- Player select: the highlighted character and their shikigami are shown
  with red clothing; the backdrop and the other two characters keep their
  normal colours (v2.5). (v2.0-v2.4 tinted the backdrop maroon.)
- High-score screen: maroon banners (v2.3).


HOW TO USE
----------
Option A (recommended): drop in the ready-made clone zip.
  Put guwanges.zip from this folder in the same ROM folder as your
  guwange.zip. Don't change guwange.zip. MAME looks in guwanges.zip first
  for the Blue Label set, so it picks up the Omen files, and your original
  Guwange set stays clean (it still verifies as good).
  - MAME: run "guwanges". It will warn about wrong checksums for the four
    files above; that's expected. Press a key to continue.
  - FBNeo: you may need to turn off ROM CRC checking in its settings.

  Note: putting the patched u086/u085 inside guwange.zip's "guwanges"
  subfolder does NOT work. MAME matches the sprite ROMs by checksum and loads
  the parent's originals, so the logo won't appear. Use the separate zip.

Option B: patch your own files.
  Apply each .ips to the file with the same name (Lunar IPS, Floating IPS,
  etc.). The loose patched .bin files are also included.


TUNING
------
The gameplay balance numbers are 16-bit words at program address $1974.
All values are under 256, so to change one you only need to edit a single
byte in gu-u0129b.bin (the odd/low-byte ROM), at these file offsets:

  offset  default  meaning
  0xCBA   3        skull units per normal graze
  0xCBB   6        skull units per graze of a slowed bullet
  0xCBC   2        extra coins per graze of a slowed bullet
  0xCBD   2        skull units per cancelled slowed bullet
  0xCBE   10       cancel tier 1 threshold (bullets)
  0xCBF   8        tier 1 bonus units
  0xCC0   25       cancel tier 2 threshold (bullets)
  0xCC1   16       tier 2 bonus units
  0xCC2   48       cap on units from one cancel burst

Set any "units" value to 0 to switch that part off.

The v2.0 numbers are words at program address $0B8B00. Edit them at these
file offsets; most fit in one byte in gu-u0129b.bin:

  offset   file        default  meaning
  0x5C580  gu-u0129b   8        skull units per shot kill (16 = old rule)
  0x5C581  gu-u0127b   14       cancel radius, in steps of 4 px (14 = 56 px)
  0x5C582  gu-u0129b   90       chain window (frames)
  0x5C583  gu-u0129b   20       max bonus coins per chained pop
  0x5C584  gu-u0129b   150      Kyocho length on entry (frames)
  0x5C585  gu-u0129b   10       frames added per graze in Kyocho
  0x5C586  gu-u0129b   20       frames added per slowed-bullet graze
  0x5C587  both        300      Kyocho cap (high byte 1 in gu-u0127b,
                                low byte 44 in gu-u0129b)
  0x5C588  gu-u0129b   2        skulls lost when Kyocho runs out
  0x5C589  gu-u0129b   30       frames of no drain after a graze (0 = off)
  0x5C58A  gu-u0129b   1        1 = half-speed drain, 0 = Blue Label speed
  0x5C58B  gu-u0129b   1        1 = hitbox marker on, 0 = off
  0x5C58C  gu-u0129b   1        1 = Kyocho background tint on, 0 = off

To go back to Blue Label's screen-wide cancels, set the radius to 80
(0x50 = 320 px). The title colour, logo artwork and text are set in src/
and need a rebuild to change.


TECHNICAL NOTES
---------------
- v2.1 uniforms: sprite palette banks 0, 1 and 2 (one per character) are
  recoloured in all three per-stage palette images at $0D0000, $0E0000 and
  $0F0000 (the game picks one per stage from the table at $065344).
- Hitbox marker: 16x16 sprite at code $15F90 (empty sprite ROM next to
  the logo), palette 16, centred on the player's position ($2(obj),
  $4(obj)), game modes 7-8 only. From v2.3 it's emitted by a hook on the
  generic object sprite emitter at $072872, straight after the player's
  body sprite and with the body's priority bits (within a priority level,
  later sprites draw on top on this hardware).
- v2.3 player select highlight: sprite banks 23-25 (characters) and 26
  (shikigami, which the game pulses from the base at $0D3400) are
  recoloured in the $0D0000 palette image.
- v2.8 splash: hooked at $007A24 (the WARNING screen's hand-over to the
  attract: "moveq #2,d0 / jsr $6EC12" -> jsr splash). It runs its own frame
  loop on the game's end-of-frame routine ($06EC26), draws the logo as one
  160x160 sprite (codes $10D00-$10D63) and PRESENTS as eight 16x16 sprites
  ($10D64-$10D6B) in palette 63, and fades by writing the scaled palette
  into the game's own vblank palette queue ($20EF4A / $2018A4), so the
  hardware sees the same kind of palette writes as the game's fades. When it
  ends, bank 63 is restored from the stage palette image. Code at
  $0CE100-$0CE2CC and its palette at $0CE800 (0xFF padding before the
  $0CF000 table; only the disabled boot checksum reads it). The sprite codes
  were empty in u086/u085 and the game never draws them (checked: 1,292
  screenshots of attract and play identical with those tiles filled).
  The art and its 240-colour palette come from the N64 port's
  port/n64/splash_logo.inc; the hold frame matches the N64 picture pixel
  for pixel. Its state (frame, last input, cut) is in RAM at $201690.
- v2.8 credits: the ending's last card is drawn at $0596C4 (five 16x80
  sprites, codes $1F2B-$1F43, palette 63, then the calligraphy at
  $05972E). The hook at $05972E draws three 16x96 sprites (codes
  $10D70-$10D81) under THE END at portrait rows 224-271, centred on the
  card, then runs the replaced instructions. Their letters are cut from
  the credits' own role titles (CHARACTER, PROGRAM, DESIGN, SOUND, BY;
  the font is on a 7.5-pixel pitch) with their original pens, so they use
  the card's palette and fade with it (src/mk_credits.py, cred_lines.npy).
- v2.4 ranking screen: its palette fade script at $00711A (used only by
  the ranking screen) lists a source pointer per palette segment. The three
  pointers for sprite bank 22 ($0D2C02, $0D2D00) and layer bank 66
  ($0F8402) now point at maroon copies (title maroon: hue 0.985,
  saturation x1.2, value x0.58) at $0B90C0-$0B91FD, in verified-unread
  padding. The palette images themselves are untouched, so stage 1 (which
  shares bank 66) is unaffected. No runtime code.
- v2.1 meter: the per-frame hook snapshots both meters, runs the game's
  meter routines, and undoes any drain step that's blocked (grace timer or
  every other step).
- v2.1 Kyocho tint: each frame rewrites 512 background colours (palette
  $C08000-$C0FFFF) from the current stage's ROM palette image, scaled to
  R*5/8, G*3/8, B*3/8. When Kyocho ends it sets the game's own palette
  upload request ($201899/$2018A2) to restore the background.
- v2 code (1150 bytes in v2.1) lives at $0B8B00, in 0xFF padding that only the
  boot checksum reads (watchpoints over full play sessions confirmed it).
  Its state is 48 bytes of RAM at $201660 that the game never touches; it
  resets itself on the first frame if it finds garbage there.
- v2.0 hooks: $000A9E per-frame (jsr frame_hook, wrapping both meter
  routines), $0569E2/$0569F0 cancel entries (jmp lc_p2/lc_p1), and the 12
  skull grants in the kill-scoring code at $56028-$56470.
- The kill-scoring code tags every kill: shikigami kills cancel slowed
  bullets, shot kills grant skulls. The dying enemy is in a6, which the
  local cancel uses for its position.
- Player select backdrop: palette bank $61 (ROM image $0DC200), used only
  in game mode 11. v2.0-v2.4 recoloured it; v2.5 leaves it original,
  because the unpicked characters share its entries with the temple (an
  index map showed no clean split).
- New code lives at $1974-$1C0B, inside a block at $1974-$1D5B that the
  game never runs. It's an old copy of the graze loop that the code always
  jumps over at $1970; breakpoints confirmed it never executes.
- The maroon palette table (1 KB) is at $0B7B00, inside 0xFF padding that
  only the boot ROM checksum reads. Blue Label already disables that check
  (it stores 8080/8080 placeholder sums).
- Hooks:
    $06E7C2  graze coin spawn            jmp -> graze_hook
    $056AA6  slowed-bullet cancel        jmp -> cancel_hook
    $05D5AE  title palette R/B swap      jsr -> pal_xform
    $007A4C  boot copyright line         jsr -> boot_credit
    $005BC8  title loop                  jsr -> title_hook
    $072872  object sprite emitter       jmp -> hb_hook       (v2.3)
    $005D6A  PRESS START loop            jmp -> press_hook
- The title swap fade is used only in game mode 4 (the title) and only for
  palette banks $01, $2F and $5E. Omen recolours $2F (foreground trees) and
  $5E (background); everything else keeps Blue Label's swap.
- OMEN logo: a 112x64 sprite (stored rotated, 64x112 in hardware order) at
  sprite code $15FA0, in an empty stretch at the end of u086/u085. It uses
  sprite palette 16, which is loaded for the whole game.
- Skull meter RAM: P1 skulls $2028A8 / fraction $2028AC,
                   P2 skulls $2028AA / fraction $2028AE.
- The game's RNG is bumped by an interrupt, so any code change (even
  drawing on the boot screen) shifts the random sequence. Two builds fed the
  same inputs won't replay identically; that's expected.
- Tested in MAME 0.289 with scripted play: boot, title, PRESS START,
  player select, all three characters, a forced Kyocho, and 12,000-frame
  sessions with no crashes. 59 unit tests (v2.0-v2.8) plus the v1 tests
  pass in a 68000 emulator (test_v2.py, test_unicorn.py).
- Not tested: two players at once in MAME (P2 code paths are unit-tested).
- src/ has the assembly source (omen.s), the build script and the tests.
  To rebuild: python3 build.py <dir with gu-u0127b/gu-u0129b/u086/u085>
  <out dir>  (needs m68k-linux-gnu-as/ld/objcopy, numpy).
