# Contributing
Any DTU ELE student can feel free to contribute to the communal DTU ELE Library. However we have a set of guidelines for the components and the footprints.

In order to have a coherent structure please follow the upcomming rules and requirements for schematic symbols and footprints.

## Rules and Requirements

### Schematic Symbols
This section contains the rules and guidelines for the schematic symbols.
* Always drawn in mils on a 50 mil grid
* Symbol comment and desciption must be filled

#### Must have parameters
The following parameters are a bare minimum, and must be written in the given format.
<!-- Give a link to my Altium script -->
* Manufacturer
* Manufacturer part number
* Published (when was this model released, yyyy-mm-dd)
* Publisher (who created it, initials or full name)
* Datasheet version (write as given in datasheet)
* Link to used datasheet (preferably the given manufacturer)

#### Nice-to-have parameters
These are nice-to-have parameters, used for quick and easy BOM generation and symbol assessment.
* LatestRevisionNote
* LatestRevisionDate
* LatestRevisionAuthor
* PackageDescription
* PackageReference
* Farnell part number
* Digikey part number
* Mouser part number
* RSonline part number
* Tolerance
* Voltage rating (note if AC or DC)
* Dielectric/material (dielectric if capacitor, material if a specific resistor)
* Alternative parameters such as current, voltage, operating temperature and etc

#### Designators
All components must in general include a meaningful designator.

| Designator    | Component Type						|
| --- 			| --- 									|
| BT 			| Battery								|
| C 			| Capacitor 							|
| D 			| Diode/LED								|
| DS 			| Display 								|
| F 			| Fuse 									|
| FB 			| Ferrite bead  						|
| FD 			| Fiducial 								|
| H 			| Hardware (mounting screws, etc) 		|
| IC 			| Generic ICs 							|
| J 			| Jack, fixed part of a connector pair 	|
| JP 			| Jumper / link 						|
| K 			| Relay  								|
| L 			| Inductor 								|
| LS 			| Loudspeaker or buzzer 				|
| MT 			| Motor 								|
| MK 			| Microphone 							|
| P 			| Connector 							|
| R				| Resistor								|
| RN 			| Resistor network 						|
| RT 			| Thermistor 							|
| RV 			| Varistor 								|
| SW 			| Switch 							 	|
| T 			| Transformer						 	|
| TC 			| Thermocouple 							|
| TP 			| Test point						 	|
| TR 			| Transistor						 	|
| Y 			| Crystal / oscillator 					|
| Z 			| Zener diode 							|

#### Font size
#### Symbol outline and fill

#### Other guidelines for schematic symbols
* Logic components such as AND, NAND, NOR, Opamp, Comparators etc should be drawn as individual parts. That way a single AND of a QUAD-AND can be placed individually. This improves the schematic readability.
* Optocouplers and current-mirror integrated components can be drawn as individual parts or in the same package
* Make the component as detailed as possible. For instance MOSFET body-diode, NPN/PNP BJT gate-resistor for logic devices.

#### Safety critical components
If the component is safety critical (X/Y capacitor for instance) it must be clearly marked, and it should note that the component is safety critical requiring at least xxxx of voltage/tolerance/standard. An X/Y capacitor should for instance include a parameter called “Suppression Class” for the required class, say Y2.

The safety mark could look like this:

<p align="center">
	<img src="figures/safetycritical.png" alt="Drawing" style="width: 60%;"/>
</p>


In this manner, the user/designer will easily catch on to the importance of the safety rated component.

#### Confidential components
FIND A WAY TO DEAL WITH CONFIDENTIAL STUFF!!! Maybe they should not be included in the Altium library at all.

### Footprints

#### Naming convention
For manufacturer specific footprints or footprints made according to a given manufacturer's specifics, the naming must carry the manufacturer name according to Altium's default [Vendor Codes](https://techdocs.altium.com/display/ADOH/Vendor+Codes).

| Company         	| Abbreviation 	|
| Nexperia 			| NEXP 			|

#### Layers

| Layer         | Description                                                       | Line Width 	|
| --- 			| --- 																| --- 			|
| Overlay		| Silkscreen														| 0.2 mm 		|
| Mechanical 1 (and 2 maybe)  | 3d model and component outline (maybe as a layer pair)                                   | 0.1 mm 		|
| Mechanical x-x  | Text/ruler notes for each signal layer maybe                    | 0.1 mm 		|
| Mechanical 15 | Top component courtyard and center point							| 0.1 mm 		|
| Mechanical 16 | Bottom component courtyard and center point						| 0.1 mm 		|
| Mechanical 25 (Could use Draftsman instead) | Top placement, component outline and .Designator string in middle | 0,1 mm 		|
| Mechanical 26 (Could use Draftsman instead) | Bottom placement, same as top layer if applicable 				| 0.1 mm 		|
| Mechanical 27 | Reserved for PCB board outlines 					 				| N/A 	 		|

##### Mechanical 1 - 3d model and component outline
The 3d model is often made with a "place -> 3d body" and can either be a simple "box" with the width, lenght and height of the actual component. The component outline outlines with 0.1 mm wide lines where the 3d body ends.

##### Mechanical 15/16 - Courtyard and center point
Mechanical 15 and 16 layers must be setup as a layer pair, so the component courtyard and reference origin automatically switches layers as well.

The courtyard is used to describe the distance from the component and land patterns to components around. [IPC-7251](http://www.ipc.org/committee/drafts/1-13_d_7251WD1.pdf) is a standard for land patterns and describes the point and requirements for courtyard excess.

In the DTU Altium Library nominal courtyard excess is used: 0.25 mm from the outer bondaries of the component. This value is measured from the center of the 3d-outline line. The center point is made of a "cross" with 0.1mm wide 1mm lines.

##### Mechanical 25/26 - Placement layer
This layer is used for a PDF printout of where which components must be placed. This way people can easily assess that this one is IC1, R32 here and the like without the need for bulky silkscreen.

The placement layer must contain a special string ".Designator" in the middle of the placement body assigning the designator of the component. The standard size for this is 0.5 mm height.

Special attention must be brought to components like polarized capacitors, diodes and ICs with numbers. Said packages' placement layers must easily assess in which direction pin 1 (or cathode) is oriented.


### Integrated

### Naming Convention


## Licenses
Under no circumstances must any licensed content excluding academic OR commercial use be used in the building of the components. This in general applies to especially 3d models found on the internet.

## Online Guides
If you are interesed in further knowledge in the proper way of handling large scale libraries, we can recommend the following links:

[KiCad Library Conventions](http://kicad-pcb.org/libraries/klc/)

[Component Development best practices - Part 1](https://resources.altium.com/pcb-design-blog/component-development-best-practices-part-1)

[What's in a Name - Component Development Part 2](https://resources.altium.com/pcb-design-blog/whats-in-a-name-component-development-part-2)

[What's the best way to make a library searchable? Parameters - Component Development Part 3](https://resources.altium.com/pcb-design-blog/whats-the-best-way-to-make-a-library-searchable-parameters-component-development-part-3)


