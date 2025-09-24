# Session 3

## Topics for Today

- __Important__: Next week we start at 18:00 and finish at 20:30 (sharp!)
- Reminder to join the Discord server [here](https://discord.gg/tkvjkEwR) to share tips and info

### Project Support

- The next two weeks are all about completing and supporting your projects
- The aim is to order your PCB from JLCPCB during next week's session!

Quick poll: who is working on what?

1. WeevilEye Bug Blinky
	
<img src="https://i5.walmartimages.com/seo/SparkFun-WeevilEye-Beginner-Soldering-Kit_acb6ebd9-f8cb-48f3-9e41-d059137d220a.5e5ec7d989a093506eeb3e1f1036af60.jpeg" alt="WeevilEye" style="width:30%;">

2. 555 Aeroplane

<img src="https://raw.githubusercontent.com/ANG13T/555-plane-pcb/main/assets/preview.PNG" alt="555Plane" style="width:30%;">

3. Hack Club Hackpad

<img src="https://hackpad.hackclub.com/orpheuspadpic.png" alt="Hackpad" style="width:30%;">

4. Moritz Klein Eurorack Module

<img src="https://schneidersladen.de/thumbnail/a8/07/da/1758256319/240631_mki_x_esedu_erica_synths_edu_diy_bbd_2406311_800x800.webp" alt="Moritz" style="width:30%;">

5. Something else? Tell us!

### Revisiting our [layer palette](https://morepcb.com/wp-content/uploads/2023/07/PCB-Surface-Finishing-Structure-1.png) (and a correction from last week!)

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

### All about [surface finishes](https://morepcb.com/pcb-surface-finishes/)

- Surface finishes coat any exposed copper areas
- Correction from last week: exposed copper is not allowed!
- They are applied [towards the end of the production process](https://youtu.be/jTBOSob5MLg?feature=shared&t=2804)
- They prevent corrosion and aid component soldering
- Traces are usually covered with mask and pads are usually left exposed

#### Main Types
- The two main types of surface finish are [HASL and ENIG](https://www.globalwellpcba.com/wp-content/uploads/2024/12/Comparison-of-HASL-vs.-ENIG-surface-finishes-on-PCBs.webp)
- HASL: Hot Air Solder Leveling
	- Silver look, cheaper, somewhat even, good for hand soldering
- ENIG: Electroless Nickel Immersion Gold
	- Gold bling look, more expensive, flatter and more uniform
- And there are more...

### Design examples 

See if you can identify what the different palette elements are in the following designs:

- PCB Jewelry [Floppy Disk Earrings](https://cdn-learn.adafruit.com/assets/assets/000/120/538/large1024/components_20230428_100135.jpg?1682690661)

- Hack Club [Sprig](https://user-images.githubusercontent.com/27078897/186769641-5b1181b4-9969-4276-9fa0-9f15140e4a9b.jpg)

- Make Noise [0-Ctrl](https://cdn.webshopapp.com/shops/345009/files/428313565/make-noise-0-ctrl.jpg)

- Synthux Academy [Simple Touch 2](https://cdn.prod.website-files.com/60222aa91a44ab23049ee333/671a056e4a76a7253300fbdf_Simple-Touch-2-Synthux-Academy-crop.jpg)

### Planes and pours and their usage

- Planes: for power, ground, or artistic purposes
- Electrical benefits of planes are that they:
	- Provide low-impedance paths for return currents
	- Enable robust power distribution across the board
	- Aid thermal management preventing hot spots and acting as heat sinks
	- Reduce noise and electromagnetic interference
	- Improve signal integrity (critical in high-speed or mixed-signal)
- You can still route traces on the the same copper layer as a plane!

### Routing Tracks and Vias: Tips and Tricks

- Highlighting nets using the 'nets' view
- Highlighting with the 'backtick' key
- Edit pre-defined track widths and via sizes
- Purpose of the 'U' icon
- Autorouting
- Routing modes: Highlight, shove, walkaround