# Session 2

## Topics for Today

- _Introduction Round_
- Join the Discord server [here](https://discord.gg/tkvjkEwR) to share tips and info
- Recap of Last Week's Workflow
- Silkscreening and Other Artistic Techniques
- It's "Choose a End-Goal Project" Time :)
- How to Make a Schematic
- _Session Break_
- Supported Project Work

## Recap of Workflow

1. Make a schematic, perform ERC check
	- More on this today!
2. Assign footprints to components
	- Through-hole vs surface mount
	- Perform physical component check (calipers out!)
3. Setup your board
	- In PCB Editor go to "File -> Board Setup" and pay attention to:
		- Board Stackup: "Board Editor Layers" and "Physical Stackup" pages
		- Design Rules: Constraints (ideally should match [JLCPCB capabilities](https://jlcpcb.com/capabilities/pcb-capabilities))
4. Draw/import board outline
	- On the "edge cuts" layer!
5. Layout the PCB
	- Place your components
	- Perform DRC check
6. Route traces/create planes
	- Perform DRC check (yes, again!)
7. Export, upload and check
	- Install Fabrication Toolkit plugin
	- Export Gerber/Drill Files, Upload to JLCPCB, Perform Online DFM check (1st time)
8. Add and position silkscreening and graphics
	- Position component references for hand soldering
	- Add cool looking graphics
	- Perform final visual check in 3D Viewer
	- Export Gerber/Drill Files, Upload to JLCPCB, Perform Online DFM check (2nd time)

## Silkscreening and Other Artistic Techniques

Remember that the [PCB is our palette](https://github.com/fablabnk/PCB-SummerSchool/tree/main/PCBPalette.png) and there are many ways to use it's features and limitations creatively.

Let's explore:
- Silkscreening
- Exposing the raw board
- Exposing copper pours
- Artistic plating
- Artistic use of holes/cutouts

## Importing Vector Graphics

- Here are some [vector graphic elements](https://github.com/fablabnk/PCB-SummerSchool/tree/main/GraphicElements/TriggGraphicElements.svg) to experiment with from our fablab [Trigg Mini-Games Console](https://github.com/fablabnk/trigg/tree/main/hardware/mainboard_PCB/kicad) project
- Vector graphics means .svg or .dxf files
- [Inkscape](https://inkscape.org/) is probably the best open source tool to open/work with these elements (or Adobe Illustrator if you have it)

### The Import Process

- Pick a graphic element you like from the elements provided.
- Export it from Inkscape as a separate .svg file
- For this example I will use an [aeroplane .svg](https://staging.svgrepo.com/svg/47678/aeroplane) file imported as a board outline. My edited version is in our repo [here](https://github.com/fablabnk/PCB-SummerSchool/tree/main/GraphicElements/BoardOutlinePlane.svg)
- Import it into PCB Editor using: "File -> Import -> Graphics"
- Choose which board layer you would like to import it to (in our case "Edge Cuts" for board outline)
- To size it, you may have to keep reimporting and adjusting "import scale" parameter (no draggable resizing possible, unbelievably!)

## Importing BitMaps as Footprints

- In Project Window choose "Image Convertor"
- Open your bitmap image (e.g. [airplane.png](https://github.com/fablabnk/PCB-SummerSchool/tree/main/GraphicElements/airplane.png))
- Set black/white threshold and check result in "Black & White Picture" tab
- Select Output Format: Footprint
- Click "Export to File..." and save
- In PCB Editor
	- Go to Preferences -> Manage Footprint Libraries
	- Select "Project Specific Libraries" tab
	- Name the library, in "Libary Path" navigate to the folder containing airplane.png, and click OK
	- Place footprint as normal (chip icon in right hand palette or keyboard shortcut 'A') 
	- Type 'airplane' to find your footprint

## It's "Choose a End Goal" Project Time" :)

- Below are some project ideas along with [schematic graphics](https://github.com/fablabnk/PCB-SummerSchool/tree/main/SchematicGraphics) (to blatantly copy!)
- Your own projects are also totally welcome!
- Decide which is most feasible/achievable for you in the next two weeks
- Would be great to work in groups, with different variations on the same project

1. WeevilEye Blinky
- Graphic schematic [here](https://cdn.sparkfun.com/datasheets/Kits/Weevil_Eye-v16.pdf)
- Start from scratch and work on your own creative board design

2. 555 Aeroplane
- A slight more advanced 'blinky' project with flashing LEDs using a 555 timer chip
- Graphic schematic [here](https://github.com/ANG13T/555-plane-pcb/blob/main/assets/schematic.PNG) and original project repo [here](https://github.com/ANG13T/555-plane-pcb)

3. Hack Club Hackpad
- A macropad (think mini-keyboard!) which uses a microcontroller as it's brain (Seeed Xiao RP2040)
- The official design-challenge site is [here](https://hackpad.hackclub.com/)
- Graphic schematic [here](https://hackpad.hackclub.com/docs/v2/wiredcomponents.png)
- Lab Project Inspiration 1: [Torn Keyboard](https://github.com/fablabnk/torn/tree/master/torn_left) - lots of switches!
- Lab Project Inspiration 2: [Blot Control Board](https://github.com/fablabnk/blot/tree/main/hardware/motor-control-board/circuit/controller_Kicad) - uses a Seeed Xiao

4. [Moritz Klein Wavefolder](https://www.ericasynths.lv/shop/diy-kits-1/edu-diy-wavefolder/) Eurorack Synth Module
- Involves designing to a given [physical specification](https://doepfer.de/a100_man/a100m_e.htm)
- Could also involve making a PCB-as-panel
- Lab Project Inspiration: [SynthLab Mixer](https://github.com/fablabnk/HagiwoMixer)

# How to Make a Schematic

- We use [standard electrical symbols](https://storage.googleapis.com/tb-img/production/23/11/electrical%20symbols%20chart.png)
- We can also make our own symbols or import them from external libraries
- For today, we will largely just practise recreating existing schematics, to not fall too deep into the electronics theory hole :)

Let's cover some basics of the KiCad Schematic Editor:
- Placing symbols from the inbuilt library
- Wiring and junctions
- Adding ground, voltage and labels
- Performing an Electrical Rules Check (ERC)
- Adding Power Flags
- Important: pass ERC before moving on to laying our your PCB
- Importing symbols/symbol libraries (i.e. Seeed Xiao RP2040 Microcontroller)