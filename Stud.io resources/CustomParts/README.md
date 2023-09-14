Here you can find part files that can be used with [LDraw](https://www.ldraw.org/) based editors.

# How to use the files

## Bricklink Stud.io

After you installed [Stud.io](https://www.bricklink.com/v3/studio/download.page), you need to copy contents of parts under CustomParts/parts and connectivity into CustomParts/connectivity.
Once this is done, the Revolution Robotics parts should show up in the toolbox.

### How to build

Drag and drop some items into the view.
Our parts have to types of connections: Pins and Axles. They have both their holes and connectors.
To make a connection:
1. Select the Connect tool
2. Select the part you want to move by clicking on it
3. Little turqoise cylinders will light up where the connection points are.
       
   NOTE: Each cylinder is divided into 5 parts. Pick the middle one.
4. Now select the target cyliner with which you want to make a connection.

   Remember: Each cylinder is divided into 5 parts. Pick the middle one.
5. TADA
6. You might need to rotate the items first, so they align in direction. Cylinders with different alignment are considered incompatible, hence not showing up in the connection process.

### Location of CustomParts directory

MAC: Users > YOUR USERNAME > .local > share > Stud.io > CustomParts (Note: to see the hidden folders in your user folder(.local), press Shift+Cmd+>.)

Windows: find it under \Users\{UserName}\AppData\Local\Stud.io\CustomParts

# About the files

## How the files were created

- STEP files were converted into ASCII STL files.
- stl2dat -raw -scale 2.5
	
  `raw` is used to avoid extra operations of the tool, some of which caused bugs
	
  `scale 2.5` is used as STL files are in mm, but LDraw files use LDU as unit (0.4mm)
- assign color for DAT file (replaced 16 with actual color to be used)
- complex models:
	Used Bricklink's PartDesigner to combine complex models with multiple per-color DAT files.
- rotate model into proper position
- move (normalize) into the first octant (all coordinates on each axes are >=0)
- Create connectivity info in PartDesigner

### Tools
The tools we used for processing the parts:
- [stl2dat](http://marc.klein.free.fr/lego/stl2dat/stl2dat.html) used for converting from stl to dat
- [ldrawtweaker.py](https://github.com/vhermecz/LDrawTweaker) used for rotating, flipping, normalizing the models
- [PartDesigner](https://www.bricklink.com/v3/studio/partdesigner.page) used for combining multifile parts, and assigning connectivity

## Colors used

To remain compliant with LDraw based editors and renderers, we used colors defined in [LDConfig.ldr](https://www.ldraw.org/article/547)

Colors:
- black - 0
- blue - 1
- red - 4
- dark grey - 8
- white - 15
- yellow - 226
- black rubber - 256
- glass - 47
- metal - 383 (chrome)

# Known issues

The S24x2 and BR files cannot be edited in the PartDesigner, as it crashes. (Starts allocating memory in an endless loop.)
