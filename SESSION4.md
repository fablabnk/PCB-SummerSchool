# Session 4

## Topics for Today

- Project Show and Tell
- Creating Your Own Symbols and Footprints
- The JLCPCB Ordering Process
- PCBA: Fully assembled PCBs (optional)
- Wrap Up and Thanks for Joining!

### Project Show and Tell

- Who has something they wouldn't mind to show us all?

### Creating Your Own Symbols and Footprints

- e.g. for battery clip
- Getting spec from AliExpress or measuring
- 21mm between pins

### The JLCPCB Ordering Process

It's good to have a deadline! So let's meet again on either
- Friday 17th 6-7pm
- Monday 20th 6-7pm

- When we reach the end of our [workflow](https://github.com/fablabnk/PCB-SummerSchool/blob/main/SESSION2.md#recap-of-workflow) and have passed KiCad DRC check and JLCPCB DFM check, we're ready to order

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

- This part is optional - if 

- JLCPCB are tightly integrated with [LCSC Electronics](https://www.lcsc.com/)
- This means they can offer 

- So when the designs get tough, the tough get lazy!
- As designs get more complex and smaller, there's a limit to what we want to do by hand
- Making assembled PCBs takes us more in the direction of a 'product'
- JLCPCB [`Pick and place` video](https://youtu.be/jTBOSob5MLg?si=vIx8LeCPXvVOmfTs)

- Mostly by PCBA we mean surface mount - but through-hole also (sweatshop)

by hand - $0.03 to $0.10 per joint

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

#### Breadboarding

Coming soon

#### Circuit simulation tools
- WokWi
- Tinkercad Circuits
- Falstad
- EveryCircuit
- SPICE

#### Wrap Up and Thanks for Joining