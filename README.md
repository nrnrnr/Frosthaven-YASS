# Frosthaven YASS Layout Sheets

This repo contains LaTeX source code and additional images needed to
make box labels for the [YASS (Yet Another Storage
Solution)](https://boardgamegeek.com/thread/1726878/yss-yet-another-storage-solution)
for Frosthaven.  If you just want US Letter sheets, they are here:

  - [`monsters2.pdf`](https://nrnrnr.github.io/Frosthaven-YASS/monsters2.pdf) contains labels for the monsters.
  
  - [`overlays2.pdf`](https://nrnrnr.github.io/Frosthaven-YASS/overlays2.pdf) contains labels for overlay
    tiles.
    
Each PDF is two-sided on US letter paper and can simply be printed.
For other paper size or to customize your layout, read on.

## Rationale and Notes

The sheets are set up for 4 shallow tackle boxes each holding up to 36 small
compartments (Plano 3600 or similar).  This is not a great setup because the Frosthaven
standees are significantly larger than the Gloomhaven standees, which means that many standee sets take up two or even three compartments—if I had it to do over again, I would have bought deeper boxes.

The monsters are grouped by the order in which the stat cards ship.   This order groups together monsters that are often encountered together or that share similar themes.  In order to help find enemies quickly, I've named and labeled some groups: "Water Hazards" for enemies found in or near water, "Deadly Mechanisms" for Ancient Artillery and other mechanical enemies, and so on.

Overlay tiles are grouped in a way that I hope makes things easy to find:

  - Large corridor tiles are mostly grouped together in the same compartment so that you can find the one you want by color.
  
  - Other tiles that share compartments are, when possible, of different shapes.

  - Doors are in two different compartments; if you have the right compartment, you have the door you want.

Other notes:

  - Each group of monster standees gets its own compartment. By using diagonal separators or other tricks to create oddly shaped compartments, it might be possible to cram all the enemies into just two boxes.  I have not tried it.

  - Although treasure tiles aren't technically overlay tiles, I've included them in the overlay box.
  
  - Not all the overlay tiles are correctly named.  I didn't want to scan the entire scenario book looking for the right names, and attempts to crowdsource the names encountered limited success.
  
  - Images of some monster portraits and all overlay tiles are made from photographs of my game.  Cephalofair has granted permission for me to post them for nonprofit purposes.
  
## Making your own PDFs

To make your own PDFs, you will need the contents of this repository, plus the following:

  - [Images of the monster stat cards from Frosthaven](https://github.com/any2cards/frosthaven/tree/master/images/monster-stat-cards/frosthaven)
  
  - The [Gloomhaven Creator Pack](https://drive.google.com/open?id=1A3Budnzy2L225DvVQY9_9z2HvvXb3Bio) which was [provided by Isaac Childres](https://boardgamegeek.com/thread/1733586/files-creation)
  
To build the PDFs, follow these steps:

 1. Ensure that you have [TeXLive](https://www.tug.org/texlive/) installed.

 2. Download and install these fonts:
 
      - Germania One
      - High Tower Text
      - High Tower Text Bold

    All should be available from free sites.

 3. Download and install the two image sets above (in the locations of your choice).
 
 4. Alter the first two lines of `monsters.tex` to point to the locations where you installed the image sets in step 3.  (If you don't have a `crushed` directory, open an issue and I'll try to help.  If I created it, I don't remember how.)
 
 5. Build both PDFs:
 
        xelatex monsters
        xelatex overlays

 6. To create two-sided PDFs, if on Linux:
 
        pdftk monsters.pdf cat 1 1 2 2 3 3 output monsters2.pdf
        pdftk overlays.pdf cat 1 1 2 2 3 3 output overlays2.pdf

To change names or layouts, you'll need to edit these files:

 - `monsters.tex` is self-contained and has layouts for all monsters.
 
 - `tiledefs.tex` defines the name and count of every set of overlay tiles.
 
 - `tilenames.tex` shows all the overlay tiles with their names.
 
 - `overlays.tex` lays out the overlay tiles to fit in one box.

If you need to change paper size or box size, focus on `monsters.tex` and `overlays.tex`.
