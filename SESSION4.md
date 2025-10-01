# Session 4

## Topics for Today

- _Project Show and Tell_
- Creating Your Own Symbols
- Creating Your Own Footprints
- The JLCPCB Ordering Process
- PCBA: Fully assembled PCBs (optional)
- Wrap Up and Thanks for Joining!

### Project Show and Tell

- Quick demos of progress

### Creating Your Own Symbols

_This part is optional - if you prefer to keep working on your designs please do so!_

- New symbols need to be added to a library
- They can be placed in a project specific library or added to the global library
- I prefer the former, as if someone clones your project they have everything they need

- Let's make a symbol for a fake 6-pin integrated-circuit (IC) called RandomChip!

#### Step-By-Step

Open the Symbol Editor and create a symbol library
- File -> New Library
- Choose "Project"
- Name the library i.e. MyLibrary
- Libraries have the extension `.kicad_sym`

Create a new symbol
- File -> New Symbol
- Give it at least a Name and Reference Designator
- Draw a box, make it's fill colour the background colour
- Add pins one-by-one connecting to the box, flipping where needed
- Name and number each pin and set it's type (Input, Output, Power Input, Power Output)
- Once done, save and test giving it a footprint (e.g. DIP6)

### Creating Your Own Footprints

_This part is optional - if you prefer to keep working on your designs please do so!_

- Jule kindly brought in some [C2032 coin battery clips](https://de.aliexpress.com/item/32739802992.html) for us all! \o/
- But we don't have a footprint for them - so let's make one!
- There are three options when this happens to you (from least to most effort):
	- 1. Find and import an existing external library e.g. [Digikey library](https://github.com/Digi-Key/digikey-kicad-library)
	- 2. Get the measurements from [the datasheet](https://ae01.alicdn.com/kf/HTB1pw2IXlfxLuJjy0Fnq6AZbXXaA.jpg?size=64584&height=520&width=923&hash=5e6cf8149ff9b1e77a5ec2acea47be58)
	- 3. Measure it yourself. Most, but the vital thing is the 21mm between the two hole that the pins will go into.

#### Step-By-Step

- Go into PCB Editor
- Open the Footprint Editor
- Steal where possible - work from a similar existing footprint
	In our case `BatteryHolder_Multicomp_BC-2001_1x2032`
- Click "Save as Editable Copy"
- In dialog that appears, click "New Library" -> Project then name your library (e.g. `MyLibrary.pretty`)
- Edit the footprint referring to the [the datasheet](https://ae01.alicdn.com/kf/HTB1pw2IXlfxLuJjy0Fnq6AZbXXaA.jpg?size=64584&height=520&width=923&hash=5e6cf8149ff9b1e77a5ec2acea47be58)
- Pay most attention to placement of the two holes
- Pay attention to Courtyard, Silkscreen and Fab layers
- Save and use it in your design like any other footprint

### The JLCPCB Ordering Process

#### When to Order

It's good to have a deadline! So let's meet again on either
- Friday 17th 6-7pm
- Monday 20th 6-7pm
Order so that your board arrives before this date (take 10-14 days)

#### Things to Pay Attention To in JLCPCB Ordering Inferface 

- When we reach the end of our [workflow](https://github.com/fablabnk/PCB-SummerSchool/blob/main/SESSION2.md#recap-of-workflow) and have passed KiCad DRC check and JLCPCB DFM check, we're ready to order!

- Most of the standard settings are what we need, so:
	- FR4 material, 2 layers, 5 PCBs (minimum order), 1.6mm thick
- Some to pay special attention to:
	- PCB Color (less common colours take a few days longer)
	- Surface Finish: HASL (silver finish), ENIG (gold finish)
	- Minimum via sizes (non-standard options cost more)
	- Mark on PCB: Order Number (Specify Position)

- Costs and Shipping
	- stay under 150 Euros to avoid customs extortion (customs fees and taxes get pre-paid)
		- Business to Consumer (B2C)
		- Import One-Stop Shop (IOSS)
	- choose `Global Direct Standard Line` or `Europacket` as shipping option
	- use coupons!

### PCBA: Fully assembled PCBs - Putting the 'why' in DIY

_This part is optional - if you prefer to keep working on your designs please do so!_

- JLCPCB are tightly integrated with [LCSC Electronics](https://www.lcsc.com/)
- This allows them to be a 'one-stop-shop' for fully assembled boards
- JLCPCB [`Pick and place` video](https://youtu.be/jTBOSob5MLg?si=vIx8LeCPXvVOmfTs)
- Mostly by PCBA we mean surface mount components but manual through-hole possible can also be done (sweatshop-style - by hand - $0.03 to $0.10 per joint plus setup fees)

Why PCBA?
- When the designs get tough, the tough get lazy!
- As designs get more complex and smaller, there's a limit to what we want to do by hand
- Making assembled PCBs takes us more in the direction of a 'product'

#### Case Study: Eurorack Resonant EQ

Let's run through the PCBA process using an equaliser we made for SynthLab (the repo is private, ask me if interested)

- You can also try with a public project such as [Blot](https://blot.hackclub.com/) [power delivery board](https://github.com/hackclub/blot/tree/main/hardware/motor-control-board/circuit/power-delivery)

- Workflow is:
	1. Complete your schematic and pass ERC
	2. Assign SMT footprints based on component availbility and size at [JLCPCB parts](https://jlcpcb.com/parts).
		- BOM Tool is super useful here, making suggesting based on the Bill of Materials output by our Fabrication Toolkit
	3. Optimise for `basic` parts where possible (saves one-time loading fees)
	4. Layout your board, deciding on economic or standard assembly and no. of boards
		- Economic: single-sided, low cost, minimum board dimension is 10x10mm
		- Standard: double-sided, more expensive, minimum board dimension is 70x70mm
	5. Pass DRC and DFM checks,  
	6. Upload your board, choose PCB options
	7. Choose PCBA toggle, choose economic or standard assembl
	8. Upload BOM and CPL files as output by our Fabrication Toolkit (bom.csv and positions.csv)
	9. Select components and check placement/orientation is correct
	10. Select category for customs and shipping
		- EuroPacket shipping not available
		- Monthly coupons for PCBA to waive setup fees

#### Circuit simulation tools

- Falstad
- WokWi
- Tinkercad Circuits
- EveryCircuit
- SPICE

#### Wrap Up and Thanks for Joining

I hope you enjoyed the summerschool and it gave you the confidence to get making your own boards. Let's meet in a couple of weeks to see the results :)