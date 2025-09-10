# Session 1: Design Your Own PCB


## Inspiration and Examples

### Technical
- [StickHub](https://github.com/rbtsco/StickHub) USB hub (Kicad Built-In Demo project)

### Artistic
- Samuel Mann's [PCB Tiles](https://www.instagram.com/samzmann/#)
- [PCB Jewelry](https://learn.adafruit.com/making-pcb-art-with-gingerbread-and-kicad/) 
- [Winterbloom](https://gingerbread.wntr.dev/) and [cool projects](https://speak.wntr.dev/) for artistic PCB design

### Overlap/Both!
- Eurorack modules e.g. [Q-bit Aurora](https://www.qubitelectronix.com/shop/p/aurora) or [Squid Salmple](https://busycircuits.com/alm022/)
- [Drawing with circuits – creating functional and artistic PCBs together](https://media.ccc.de/v/38c3-drawing-with-circuits-creating-functional-and-artistic-pcbs-together)

## Starting at the End: What is a PCB, why make one and how are they made?
- Why? From breadboard -> stable prototype -> product
- What? [Sparkfun PCB Basics](https://learn.sparkfun.com/tutorials/pcb-basics/all)
	- Standard material is FR4 (fibreglass), but there are other forms of PCB (e.g. flex)
	- Through hole (THT) vs surface mount (SMT)
	- PCB (just the board) vs PCBA (auto-assembled with components)
	- 2/4/6/8 layers and beyond
- For fabrication we need Gerber and drill files representing each of the layers in our design

## Fabrication Options

### Fab-it-yourself (FIY)
Not covered by this course!
- [Chemical etching](https://www.youtube.com/watch?v=tWnfnt2rNO0)
- [CNC milling](https://www.youtube.com/watch?v=TBB32mKpizs)
- [Fibre laser cutting](https://hackaday.com/2025/01/05/perfecting-20-minute-pcbs-with-laser/)

### Fab Houses
What we're designing for :)
- [JLCPCB](https://jlcpcb.com/): Zhuhai, Guangdong, China. [Factory tour!](https://www.youtube.com/watch?v=jTBOSob5MLg)
- [PCBWAY](https://www.pcbway.com/): Shenzhen, Guangdong, China
- [Aisler](https://aisler.net/en): Aachen, North Rhine-Westphalia, Germany

## PCBs We've Designed at fablab|nk
- Custom boards for Blot plotter
- "Proto-petals" for [Hackaday Europe Badge Hacking Workshop](https://hackaday.io/europe2025)
- Endless SynthLab Projects: Mixer -> Filter -> Ad Oscillator -> SynthLab badge -> Dev Hat -> Pendulum

## Why KiCad? Pros/Cons of Different PCB Design Software
- [KiCad](https://www.kicad.org/): Open-source, free, not tied to any platform/technology
- [EasyEDA](https://easyeda.com/): Cloud-based, easy to get going, tight integration with JLCPCB
- [Altium Designer](https://www.altium.com/altium-designer): pro, industry standard but expensive
- [Autodesk Fusion](https://www.autodesk.com/products/fusion-360/electronics-engineer): formerly known as Eagle

## Today's Challenge: Blinky "Hello World"

Two options, each with 10 components or less

1. BlinkyParts Unicorn:
_Choose this project if you want a super-easy start where the PCB is made and you're remaking it!_
	- Product [here](https://shop.blinkyparts.com/en/detail/2be126ff15944653973e8ab5393be2b1)
	- Repo with KiCad files [here](https://github.com/blinkyparts/unicorn)
	- Components: 4 x 5mm RGB LEDs (THT), 1 x button (SMD), 1 x CR2032 Battery Holder (SMD)

2. Adafruit WeevilEye:
_Choose this project if you want to add component footprints yourself and design/use your own graphics_
	- Repo with schematic [here](https://github.com/Binary-Kitchen/SolderingTutorial/tree/master/WeevilEye)
	- KiCad project (schematic only!) [here](https://github.com/fablabnk/PCB-SummerSchool/tree/main/WeevilEyeMod)
	- Components: 2 x Red 5mm LEDs, 2 x 220R Resistors, 2 x 47k Resistors, 1 x Light Dependant Resistor (LDR), 1 x 2N3904 Transistor, 1 x CR2032 Battery Holder

## "Workflow" Tour of KiCad 9 with JLCPCB

- You can follow along using WeevilEye project as an example
- A good starter tutorial is [here](https://solder.hackclub.com/tutorial) if you're looking at these notes from home
- Official Reference Docs are [here](https://docs.kicad.org/9.0/en/kicad/kicad.html)

0. Starting from the end: JLCPCB uploader and manufacturing specs
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
	- Export Gerber/Drill Files
	- Upload to JLCPCB
	- Perform JLC DFM check
7. Silkscreening and graphics
	- Add cool looking graphics
	- 3D Viewer can be good for final visual check
	- Export/Upload to JLCPCB, perform DFM check

## Next Week

- How to make a schematic
- Choosing a practice project

## KiCad Practice Projects
- [Trigg Mini-Games Console](https://github.com/fablabnk/trigg/tree/main/hardware/mainboard_PCB/kicad)
- One half of [Torn Keyboard](https://github.com/fablabnk/torn/tree/master/torn_left) 
- A simple Eurorack module (e.g. [SynthLab Mixer](https://github.com/fablabnk/HagiwoMixer) or [Mortiz Klein Mixer](https://www.ericasynths.lv/shop/diy-kits-1/edu-diy-mixer/))
- or something of your own - bring a (simple) schematic for next week!