# Session 2

- Arrange seating better for collaboration
- Bring soldered blinkies
- Check links in this doc work!

## Topics for Today

- Recap of Last Week's Workflow
- Silkscreening and Other Artistic Techniques
- It's "Choose a End-Goal Project" Time :)
- How to Make a Schematic

## Recap of Workflow

1. Make schematic, perform ERC check
	- done for us today - more on this next week!
2. Plan board outline
	- This happens on the "edge cuts" layer
3. Assign footprints to components
	- Through-hole vs surface mount
	- Perform physical component check (calipers out!)
4. Layout the PCB
	- Place your components
	- Perform DRC check
5. Route traces
	- Perform DRC check (yes, again!)
6. Export, Upload and Check
	- Install Fabrication Toolkit plugin
	- Export Gerber/Drill Files, Upload to JLCPCB, Perform Online DFM check (1st time)
7. Silkscreening and graphics
	- Add cool looking graphics
	- Final visual check in 3D Viewer
	- Export Gerber/Drill Files, Upload to JLCPCB, Perform Online DFM check (2nd time)

## Silkscreening and Other Artistic Techniques

Remember that the [PCB is our palette](https://github.com/fablabnk/PCB-SummerSchool/tree/main/DesignElements/PCBPalette.png) and there are many ways to use it's features and limitations creatively.

Let's explore:
- Silkscreening
- Exposing the raw board
- Exposing copper pours
- Artistic plating
- Artistic use of holes/cutouts

- Here are some [vector graphic elements](https://github.com/fablabnk/PCB-SummerSchool/GraphicElements/TriggGraphicElements.svg) to experiment with from our fablab [Trigg Mini-Games Console](https://github.com/fablabnk/trigg/tree/main/hardware/mainboard_PCB/kicad) project

- [Inkscape](https://inkscape.org/) is the best open source tool to open/work with these elements (or Adobe Illustrator if you have it)

## Importing Vector Graphics

-  (.svg or .dxf only)
- Pick a graphic element you like
- Export it from Inkscape as a separate .svg file
- Import it into PCB Editor using: File -> Import -> Graphics
- Choose which layer you would like to import it to
- Adjust import scale (no draggable resizing possible, unbelievably!)

## Importing BitMaps as Footprints

- In Project Window choose "Image Convertor"
- Open your bitmap image (e.g. [airplane.png](https://github.com/fablabnk/PCB-SummerSchool/GraphicElements/airplane.png))
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
- Improvised [](https://github.com/fablabnk/PCB)

2. 555 Aeroplane
- A slight more advanced 'blinky' project with flashing LEDs using a 555 timer chip
- Graphic schematic [here](https://github.com/ANG13T/555-plane-pcb/blob/main/assets/schematic.PNG) and original project repo [here](https://github.com/ANG13T/555-plane-pcb)

3. Hack Club Hackpad
- A macropad (think mini-keyboard) which microcontroller
- The official design-challenge site is [here](https://hackpad.hackclub.com/)
- Graphic schematic [here](https://hackpad.hackclub.com/docs/v2/wiredcomponents.png)
- Lab Project Inspiration 1: [Torn Keyboard](https://github.com/fablabnk/torn/tree/master/torn_left) - for 
- Lab Project Inspiration 2: [Blot Control Board](https://github.com/fablabnk/blot/tree/main/hardware/motor-control-board/circuit/controller_Kicad) - for Xiao Seed

4. [Moritz Klein Wavefolder](https://www.ericasynths.lv/shop/diy-kits-1/edu-diy-wavefolder/) Eurorack Synth Module
- Involves designing to a given [physical specification](https://doepfer.de/a100_man/a100m_e.htm)
- Could also involve making a PCB-as-panel
- Lab Project Inspiration: [SynthLab Mixer](https://github.com/fablabnk/HagiwoMixer)

# How to Make a Schematic

- [Electrical symbols chart](https://storage.googleapis.com/tb-img/production/23/11/electrical%20symbols%20chart.png)

Let's cover some basics of the KiCad Schematic Editor:
- Placing symbols from the inbuilt library
- Wiring and junctions
- Adding ground, voltage and labels
- Performing an Electrical Rules Check (ERC)
- Adding Power Flags
- Important: pass ERC before moving on to laying our your PCB
- Importing symbols/symbol libraries (i.e. Seeed Xiao RP2040 Microcontroller)