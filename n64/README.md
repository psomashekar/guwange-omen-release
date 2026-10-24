# Guwange: Omen — the N64 Game Pak

Everything to make a physical copy of the N64 version: the instruction booklet, the cartridge label and the box.
Build the ROM itself with the kit ([`../Guwange_Omen_Kit`](../Guwange_Omen_Kit)) from your own arcade ROMs.

| Folder | Contents |
|---|---|
| [`manual/`](manual) | the instruction booklet, 117 × 173 mm (the size of a Game Pak booklet), in English and Japanese |
| [`manual/print/`](manual/print) | the same booklets imposed two pages to a sheet for a duplex printer, with crop marks |
| [`box-art/`](box-art) | the cartridge label and the box: print files, die lines and previews |

## 1. The cartridge

What the ROM needs from the board:

| | needed | why |
|---|---|---|
| ROM size | **512 Mbit (64 MB)** | the ROM is 61,194,240 bytes (58.4 MB). A 256 Mbit (32 MB) board cannot hold it. |
| Save | **EEPROM 16 Kbit** (2 KB) | settings and the three modes' scores. An EEPROM 4K board still works, but saves OMEN only. SRAM and FlashRAM boards **do not save**. |
| Lockout chip (CIC) | **6102** (NTSC) or **7101** (PAL), matching your console | the boot code is made for the 6102 / 7101 family. A board set up for 6105, 6103 or 6106 games won't boot it. |
| Region | the CIC's only | the ROM is region-free, so only the CIC has to match the console: NTSC for US / Japanese consoles, PAL for PAL ones. On UltraCIC boards that's a jumper or a firmware setting. |
| RAM | **Expansion Pak in the console** | without one the game shows EXPANSION PAK REQUIRED. |
| Extras | none | no Rumble Pak, Controller Pak, RTC or 64DD. |

### What to order

**A blank, reflashable 64 MB repro PCB, flashed by you.** The ROM holds data from your own arcade ROM set and is for
your own use, so don't send it to a shop to flash. Look for:

- **N64 repro PCB, 512 Mbit / 64 MB, reflashable**, with a flash chip that Sanni's open-source Cart Reader can write:
  Fujitsu **MSP55LV512** or **MSP55LV100S**, Spansion **S29GL512**, or Intel **4400L0ZDQ0** (64 MB version), plus the
  Altera MAX II CPLD. The CPLD only maps the upper 32 MB when the board is wired for 64 MB, so a "32/64 MB" board has
  to be set up as 64 MB.
- **EEPROM 16K** save (the 16K EEPROM chip fitted, not SRAM or FlashRAM).
- **CIC 6102 / 7101**, or an **UltraCIC**-type chip set to your region.
- A **cart reader / flasher** that writes repros: Sanni's Cart Reader (see "Reflashing N64 Repros" in its wiki), or a
  pre-built one.
- An **N64 replacement shell** (NTSC/PAL style, not the Japanese one, so the label recess fits) and a **3.8 mm
  gamebit** driver. A smoke-black or translucent-red shell suits the crimson art.

**The plug-and-play alternative:** an open-hardware **SummerCart64** (or a PicoCart64) in a standard shell. It takes
ROMs up to 64 MB, emulates EEPROM 16K and the CIC, and loads from an SD card. It isn't a single-game cart, but it needs
no flashing hardware, and the label fits it too. (SummerCart64's own tool can set it to boot a ROM directly; see its
documentation.)

After flashing, check it on the console: the WARNING screen, then the splash, then a save. Change a setting, switch
off, and check that it's kept.

## 2. The cartridge label

<img src="../images/preview_label.png" width="260" alt="Label preview" align="right">

| file (in `box-art/`) | use |
|---|---|
| `guwange_omen_n64_label.pdf` | for a print shop: art only, 54.5 × 62.5 mm trim + **2 mm bleed** (TrimBox / BleedBox set) |
| `guwange_omen_n64_label_cut.pdf` / `_cut.svg` | the die-cut contour alone (magenta), on the same page size |
| `guwange_omen_n64_label_proof.pdf` | the art with the cut line and the 2 mm safe area (cyan dashes), for checking |
| `guwange_omen_n64_label_600dpi.png` | the art at 600 dpi with its bleed, for sticker shops that take PNG |
| `guwange_omen_n64_label_sheet_letter.pdf` / `_a4.pdf` | eight labels with gray cut lines and a 50 mm scale bar, for sticker paper at home |

- **Shape:** the US / PAL N64 front label is **54.5 mm wide × 62.5 mm tall**. Its top edge is an arc of 325 mm
  diameter (2.3 mm higher in the middle than at the corners), with **4 mm** radius top corners and **3 mm** bottom
  corners.
- **Stock:** gloss or semi-gloss white vinyl (or paper) sticker with permanent adhesive, laminated if you can. Order it
  **die-cut to the contour**.
- **At home:** print the sheet at **100 % / Actual size** on full-sheet sticker paper. Measure the 50 mm bar before
  you cut, then cut on the gray lines. A 3–4 mm corner punch helps with the corners.

## 3. The box

<p align="center"><img src="../images/preview_box_front.png" width="520" alt="Box front preview"></p>

| file (in `box-art/`) | use |
|---|---|
| `guwange_omen_n64_box.pdf` | the flat sheet, art only: **275 × 320 mm trim, 281 × 326 mm with the 3 mm bleed** |
| `guwange_omen_n64_box_dieline.pdf` | the same with the dieline on top, as a proof (cut = magenta solid, fold = cyan dashed) |
| `guwange_omen_n64_box_dieline.svg` | the dieline alone, for the die maker or a cutting plotter |
| `panels/box_*.png` | each face alone at 600 dpi with 3 mm bleed (front, back, both spines, both ends), for a shop that has its own N64 template |
| `preview_*.png` | previews only, not for print |

- **Size:** the NTSC-U N64 box, a landscape carton **179 × 124 × 30 mm** (7 1/16 × 4 7/8 × 1 3/16 in) that opens at
  the two short ends. The style is **reverse tuck end**: a tuck flap on each end, dust flaps on the spines, and a 12 mm
  glue flap inside the top spine.
- **Stock:** 350–400 gsm (16–18 pt) **SBS / C1S** paperboard, printed CMYK on the white side, **gloss or matte
  lamination** outside. The sheet fits on 12 × 18 in or SRA3 (320 × 450 mm).
- **Inside:** retail N64 boxes have a cardboard tray that holds the cartridge and booklet. Reproduction **N64 cardboard
  inserts** are sold ready-made and fit this box size.
- **Before a big run:** these sizes come from collectors' measurements of retail boxes. Order one proof, or ask the
  shop to check them against their own N64 template. If they have one, send them `panels/` instead of the flat sheet.

The artwork is RGB, so the shop converts it to CMYK and the deep crimson may come out a little duller. Ask for a
printed proof if the color matters.

The back of the box says it is a homebrew Game Pak, not licensed by Nintendo, ATLUS or CAVE. Some print shops ask for
that line when a box carries another company's marks, so keep it.

## 4. The instruction booklet

| file (in `manual/`) | use |
|---|---|
| `guwange_omen_manual_n64.pdf` | English, page by page at 117 × 173 mm, for a print shop or for reading |
| `guwange_omen_manual_n64_ja.pdf` | Japanese, the same |
| `print/guwange_omen_manual_n64_letter.pdf` | English, imposed on US Letter for printing at home |
| `print/guwange_omen_manual_n64_ja_a4.pdf` | Japanese, imposed on A4 for printing at home |

**At home:** print the `print/` file duplex, **flip on the short edge**, at **100 % / Actual size**. Cut at the crop
marks, fold, and staple at the spine.
