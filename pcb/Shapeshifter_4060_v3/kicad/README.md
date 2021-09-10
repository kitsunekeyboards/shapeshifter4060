# Kitsune Keyboards Shapeshifter 4060 v3.0



## PCB details

### Process reminders

#### Prepping for ordering from JLCPCB

1. File > Plot
- Format = Gerber
- Output directory = ../gerber/
- Included layers = Cu,Paste,SilkS,Mask,Edge.Cuts
2. Generate Drill Files
- Excellon
- Postscript
- Absolute origin
3. Open up GerbView from kicad
- File > Open Excellon Drill Files, select the two drl files (if you open these in the wrong order, the drill holes won't sit on top of the copper so it's hard to tell if there are any pads that aren't getting drilled)
- File > Open Gerber Files, select all the gbr files
- Hide all but the drill layers and F_Cu and B_Cu
- Stare and pretend that this means something to you
- Stare particularly hard at F_Cu and B_Cu
- Perhaps check to see if there are any lines that look like they're intersecting or something

#### Rotating the board so you can do wiring nicely

1. Show all layers
2. Select all with the mouse and rotate 10 degrees. To get the thumbs, rotate 40.
3. Hide Dwgs.User, set grid to 0.01mm, and "Set the origin point for the grid" to the center of the yellow cross on Eco2.User (center of the board about 10mm below the nice!nano)
4. Set the grid back to 0.1mm
5. Do some work

#### Setting up zones

1. Use the zone tool to draw a box around the area
2. Right click the zone (may have to select the board as well, then shift click it to deselect it) and Zones > Duplicate Zone to Layer
3. Press B to fill zones

#### Generating the BOM

1. Go into the schema editor
1. Tools > Edit Symbol Fields
1. Add the fields "Designation" and "Supplier Number"
1. Find your parts from the Elecrow parts library: https://www.elecrow.com/component-library.html?page=1&cate=Switch
1. Add the part number (like B3U-1000p) to the Supplier Number, and if there is one, add the pad shape (like SOD-123) to the Designation. Also add the Datasheet link.
1. Group by Supplier Number
1. Apply and then hit OK
1. Tools > Generate BOM
1. Choose `bom2grouped_csv` and Generate
1. `mv Laptreus-v3 ../bom/Laptreus-v3.csv`
1. `rm Laptreus-v3.xml`
1. Import `bom/Laptreus-v3.csv` to google drive (not sure why it doesn't have .csv on the end)
1. Copy all the switch References into VSCode and smash them onto one line, then replace the Reference on the first switch. Do the same for Values.
1. Now delete all the extra switches and clean up the rows
1. Now delete all the rows that represent things we don't want them assembling (nice nano for instance)
1. Copy all the values and past to VSCode, this should make a tsv. Save the file to `bom/Laptreus-v3.tsv`

#### Generate the position file

1. In PCBNew, File > Fabrication Outputs > Generate footprint position files
1. Set output path to `../pcba/`, ASCII, millimeters, Separate files for front and back

