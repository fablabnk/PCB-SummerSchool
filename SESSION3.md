# Session 3

## Topics for Today
- Visit from Jule: artistic PCB design process
- The next two weeks are all about completing and supporting your projects
- The aim is to order your PCB from JLCPCB during next week's session!

## Project poll and team formation
- Who's working on what? Who has a project, who doesn't?
- Let's form teams of three (ideally two people with a similar project, one person without a project)
- Each team should aim to submit one board during next week's session
- The fablab will sponsor the 5 most complete projects

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
- Click "Export to Clipboard" (easier way)
Or
- Click "Export to File..." and save
- In PCB Editor
	- Go to Preferences -> Manage Footprint Libraries
	- Select "Project Specific Libraries" tab
	- Name the library, in "Libary Path" navigate to the folder containing airplane.png, and click OK
	- Place footprint as normal (chip icon in right hand palette or keyboard shortcut 'A') 
	- Type 'airplane' to find your footprint

## Revisiting our [layer palette](https://morepcb.com/wp-content/uploads/2023/07/PCB-Surface-Finishing-Structure-1.png) (and a correction from last week!)

Elements of the layer palette:

1. PCB substrate (the raw board, in our case FR4)
2. Copper (optional)
3. Solder mask (optional)
	- Remember that the solder mask layer is subtractive (there by default unless you remove it)
	- If you draw on the solder mask layer...		
		- ...and there's no copper underneath: you will see the raw board
		- ...and there is copper underneath: it will get covered with surface finish (more below!)
	- Note that: solder mask over copper looks darker(?) compared to over raw board
4. Silkscreen ink (optional)
	- Can only be drawn on top of solder mask, not the raw board or plated copper areas

## All about [surface finishes](https://morepcb.com/pcb-surface-finishes/)

- Surface finishes coat any exposed copper areas
- Correction from last week: exposed copper is not allowed!
- They are applied [towards the end of the production process](https://youtu.be/jTBOSob5MLg?feature=shared&t=2804)
- They prevent corrosion and aid component soldering
- Traces are usually covered with mask and pads are usually left exposed

### Main Types
- The two main types of surface finish are [HASL and ENIG](https://www.globalwellpcba.com/wp-content/uploads/2024/12/Comparison-of-HASL-vs.-ENIG-surface-finishes-on-PCBs.webp)
- HASL: Hot Air Solder Leveling
	- Silver look, cheaper, somewhat even, good for hand soldering
- ENIG: Electroless Nickel Immersion Gold
	- Gold bling look, more expensive, flatter and more uniform
- And there are more...

## Design examples 

See if you can identify what the different palette elements are in the following designs:

- PCB Jewelry [Floppy Disk Earrings](https://cdn-learn.adafruit.com/assets/assets/000/120/538/large1024/components_20230428_100135.jpg?1682690661)

- Hack Club [Sprig](https://user-images.githubusercontent.com/27078897/186769641-5b1181b4-9969-4276-9fa0-9f15140e4a9b.jpg)

- Make Noise [0-Ctrl](https://cdn.webshopapp.com/shops/345009/files/428313565/make-noise-0-ctrl.jpg)

- Synthux Academy [Simple Touch 2](https://cdn.prod.website-files.com/60222aa91a44ab23049ee333/671a056e4a76a7253300fbdf_Simple-Touch-2-Synthux-Academy-crop.jpg)

## Planes and pours and their usage

- Planes: for power, ground, or artistic purposes
- Electrical benefits of planes are that they:
- Provide low-impedance paths for return currents
	- Enable robust power distribution across the board
	- Aid thermal management preventing hot spots and acting as heat sinks
	- Reduce noise and electromagnetic interference
	- Improve signal integrity (critical in high-speed or mixed-signal)
- You can still route traces on the the same copper layer as a plane!

## Routing Tracks and Vias: Tips and Tricks

- Highlighting nets using the 'nets' view
- Highlighting with the 'backtick' key
- Edit pre-defined track widths and via sizes
- Purpose of the 'U' icon
- Autorouting
- Routing modes: Highlight, shove, walkaround
