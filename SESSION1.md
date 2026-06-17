Session 1: Hello Hardware World and the KiCad Workflow

# Introduction

- About the class
- Share Wifi pass!

# What's in the box? Check out some PCBs designed by lab members

- See [inspirational projects](./INSPIRATIONAL_PROJECTS.md) for some of the design files

# Trip to China: Virtual tour of a PCB factory 

[JLCPCB Factory tour!](https://www.youtube.com/watch?v=jTBOSob5MLg)

# The PCB Design Continuum: between the functional and the artistic

- Functional = "pure" electronics 
- Artistic = no electronics (simply using PCBs as a design material)
- Most projects are somewhere inbetween

## Examples:

- Artistic-only: [PCB Floppy Disk Earrings](https://learn.adafruit.com/making-pcb-art-with-gingerbread-and-kicad/)
- Functional-only: [Kick Eurorack Synth Module](https://github.com/fablabnk/HagiwoKick_THT)
- Hybrids: [Electromagnetic Explorer Badge](https://darcyneal.com/emf-explorer-badge/)
- Hybrids: [Q-bit Aurora Eurorack Synth module](https://www.qubitelectronix.com/shop/p/aurora)
- Hybrids: [Tildagon badge](https://tildagon.badge.emfcamp.org/)
- Recommended talk: [Drawing with circuits – creating functional and artistic PCBs together](https://media.ccc.de/v/38c3-drawing-with-circuits-creating-functional-and-artistic-pcbs-together)

# Anatomy of a PCB: Why make one and how are they made?
- Why make one at all?
	- Go from breadboard -> stable prototype -> product
- What are they? [Sparkfun PCB Basics](https://learn.sparkfun.com/tutorials/pcb-basics/all)
	- How to treat a PCB as your [design palette](./PCBPalette.png)
	- Standard material is FR4 (fibreglass), but there are other forms of PCB (e.g. flex)
	- Through hole (THT) vs surface mount (SMT)
	- PCB (just the board) vs PCBA (auto-assembled with components)
	- 2/4/6/8 layers and beyond
- For fabrication we need Gerber and drill files representing each of the layers in our design

# Fabrication Options

## Fab-it-yourself (FIY)
Not covered by this course!
- [Chemical etching](https://www.youtube.com/watch?v=tWnfnt2rNO0)
- [CNC milling](https://www.youtube.com/watch?v=TBB32mKpizs)
- [Fibre laser cutting](https://hackaday.com/2025/01/05/perfecting-20-minute-pcbs-with-laser/)

## Fab Houses
What we're designing for in this course :)
- [JLCPCB](https://jlcpcb.com/): Zhuhai, Guangdong, China
- [PCBWAY](https://www.pcbway.com/): Shenzhen, Guangdong, China
- [Aisler](https://aisler.net/en): Aachen, North Rhine-Westphalia, Germany

# Why KiCad? Pros/Cons of Different PCB Design Software
- [KiCad](https://www.kicad.org/): Open-source, free, not tied to any platform/technology
- [EasyEDA](https://easyeda.com/): Cloud-based, easy to get going, tight integration with JLCPCB
- [Altium Designer](https://www.altium.com/altium-designer): pro, industry standard but expensive
- [Autodesk Fusion](https://www.autodesk.com/products/fusion-360/electronics-engineer): formerly known as Eagle

# Today's Challenge: Design your own Blinky Badge

Two options, each with 10 components or less

1. BlinkyParts Unicorn:
_Choose this project if you want a super-easy start where the design is already made and you're remaking it!_
	- Your starting point is [here](https://github.com/fablabnk/PCB-SummerSchool/tree/main/Project1_BlinkyPartsUnicorn)
	- Original KiCad files for comparison [here](https://github.com/blinkyparts/unicorn)
	- Product [here](https://shop.blinkyparts.com/en/detail/2be126ff15944653973e8ab5393be2b1)
	- Components: 4 x 5mm RGB LEDs (THT), 1 x button (SMD), 1 x CR2032 Battery Holder (SMD)

2. Adafruit WeevilEye:
_Choose this project if you want to add component footprints yourself and design/use your own graphics_
	- Your starting point (schematic only!) is [here](https://github.com/fablabnk/PCB-SummerSchool/tree/main/Project2_WeevilEyeMod)
	- Original KiCad files for comparison [here](https://github.com/Binary-Kitchen/SolderingTutorial/tree/master/WeevilEye)
	- Components: 2 x Red 5mm LEDs, 2 x 220R Resistors, 2 x 47k Resistors, 1 x Light Dependant Resistor (LDR), 1 x 2N3904 Transistor, 1 x CR2032 Battery Holder

# KiCad Workflow (using JLCPCB)

- You can follow along using WeevilEye project as an example
- A good KiCad starter tutorial is [here](https://solder.hackclub.com/tutorial) if you're looking at these notes from home
- Official KiCad reference docs are [here](https://docs.kicad.org/)

The workflow goes like this:

0. Starting from the end: visit [JLCPCB uploader](https://cart.jlcpcb.com/quote)
	- Decide on your board type and check manufacturing specs
1. Make your schematic and perform ERC check
	- Alreay done for us today - more on this next week!
2. Draw your board outline
	- This happens on the "edge cuts" layer
3. Assign footprints to components
	- Through-hole vs surface mount
	- Perform physical component check (calipers out!)
	- Update the board to populate the design with your components
4. Layout the PCB
	- Place your components (front, back, side-to-side)
	- Perform Design Rules check [DRC]
5. Route traces
	- Decide on trace widths
	- Systematically route the "rats-nest"
	- Perform DRC check (yes, again!)
6. Export, Upload and Check
	- Install Fabrication Toolkit plugin
	- Export .zip file (Gerber/Drill Files)
	- Upload to JLCPCB
	- Perform JLC Design for Manufacture (DFM) check
7. Add silkscreening and graphics
	- Add cool looking graphics
	- 3D Viewer can be good for final visual check
	- Export/Upload to JLCPCB, perform DFM check

# Next Week

- Before leaving, please sign up again for Session 2 (from next week become a "closed group")

- Deeper-dive into the schematics and board designs
	- Creating schematics and passing the Electrical Rules Check
	- Board design, footprints and traces

- Choosing a project for the next three sessions. 
	- Main idea: turning a 555 Airplane into a Tildagon badge Hexpansion
	- Your ideas! (keep it fairly simple for your first project)

- See [inspirational projects](./INSPIRATIONAL_PROJECTS.md) for some cool projects