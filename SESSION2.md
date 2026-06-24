# Session 2

## Intro

- Let's get the seating right!
- Join the Discord server [here](https://discord.gg/7TVYa3dYY) to share tips and info
- It's encouraged to work in teams & collaborate (and a disclaimer)
- Levelling up to use microcontrollers

## Today's Topics

6:30pm

- Case Study: Artistic Round Tripping with Hilary and the Disarray Desnarler
- Kicad Workflow Recap Demo (Building a Aeroplane Badge Expansion)
	-- https://github.com/ANG13T/555-plane-pcb
	-- https://github.com/emfcamp/badge-2024-hardware/tree/main/hexpansion
- Creating your first KiCad schematic
	1. Understand and replicate a schematic from a PDF: Unicorn / WeevilEye / 555 Plane
	2. Pass the ERC check
	3. Assign footprints
- Choose your own project time!

7:40pm

- Short Break 

9:00pm

- Individual practice time
- Tips for importing graphics from design software (e.g. Inkscape)

## How 555 flasher circuit works

https://everycircuit.com/circuit/4998831909634048/flashing-led-with-555-timer

In this circuit, the 555 timer is configured as an oscillator to create a continuous square wave output that switches the LED on and off, as follows:

1. **Charging (LED ON):** Current flows through resistors R2 and R2 to charge capacitor C1. During this time, **Pin 3 (Output)** is HIGH, turning the LED on.
2. **The Switch:** When the capacitor voltage reaches 2/3 of the supply voltage, **Pin 6 (Threshold)** triggers the timer to flip its state.
3. **Discharging (LED OFF):** Pin 3 goes LOW (turning the LED off), and **Pin 7 (Discharge)** opens an internal path to ground. The capacitor discharges through R2 only.
4. **The Reset:** When the capacitor voltage drops to 1/3 of VCC, **Pin 2 (Trigger)** resets the timer, turning the LED back on and repeating the cycle indefinitely.

## How to Make a Schematic

- We use [standard electrical symbols](https://storage.googleapis.com/tb-img/production/23/11/electrical%20symbols%20chart.png)
- We can also make our own symbols or import them from external libraries

Let's cover some basics of the KiCad Schematic Editor:
- Placing symbols from the inbuilt library
- Wiring and junctions
- Adding ground, voltage and labels
- Performing an Electrical Rules Check (ERC)
- Adding Power Flags
- Important: pass ERC before moving on to laying our your PCB
- Importing symbols/symbol libraries (i.e. Seeed Xiao RP2040 Microcontroller)

## Changes in our version of the circuit

We:
- use a potentiometer to dynamically adjust the resitance and change the on/off switching time
- flash three LEDS not one (2 red on wings, 1 green on taillight)
- use 3V3 not 9V (so we'll need to change our 300Ohm resistor)

### Microcontroller mods

To control this 555 timer circuit using a microcontroller GPIO pin, you have a few concise options depending on how you want to manipulate it:

### 1. Hard On/Off Control (via Pin 4 - Reset)

Disconnect **Pin 4 (Reset)** from the positive supply VCC and connect it directly to your GPIO pin.

* **GPIO HIGH:** The 555 timer runs normally, and the LED flashes.
* **GPIO LOW:** The 555 timer is forced into reset mode. Pin 3 stays LOW, and the LED stays completely off.

### 2. Flash Rate Modulation (via Pin 5 - Control Voltage)

Connect your GPIO pin configured to output **PWM (Pulse-Width Modulation)** through a low-pass filter (or a smooth analog voltage) to **Pin 5**.

* Changing the voltage on Pin 5 alters the upper threshold 2/3 VCC internal limit.
* **Higher GPIO voltage** slows down the flashing; **lower GPIO voltage** speeds it up.

## It's "Choose a End Goal" Project Time" :)

- Below are some project ideas along with [schematic graphics](https://github.com/fablabnk/PCB-SummerSchool/tree/main/SchematicGraphics) (to blatantly copy!)
- Your own projects are also totally welcome!
- Decide which is most feasible/achievable for you in the next two weeks
- Would be great to work in groups, with different variations on the same project

1. WeevilEye Blinky
- Graphic schematic [here](https://cdn.sparkfun.com/datasheets/Kits/Weevil_Eye-v16.pdf)
- Start from scratch and work on your own creative board design

2. 555 Aeroplane Badge Hexpansion
- A slight more advanced 'blinky' project with flashing LEDs using a 555 timer chip
	-- https://github.com/ANG13T/555-plane-pcb
- Can be combined with a 'badge hexpansion'
	-- https://github.com/emfcamp/badge-2024-hardware/tree/main/hexpansion

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