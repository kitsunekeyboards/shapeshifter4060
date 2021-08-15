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
