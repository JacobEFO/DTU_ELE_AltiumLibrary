# Contributing
Any DTU ELE student can feel free to contribute to the communal DTU ELE Library. However we have a set of guidelines for the components and the footprints.

In order to have a coherent structure please follow the upcomming rules and requirements for schematic symbols, footprints and integrated libraries.

If these guidelines are not followed, the pull request will be declined.

## Rules and Requirements
Update this with some text.

### Schematic Symbols
This section contains the rules and guidelines for the schematic symbols.
* Always drawn in mils
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

### Footprints

[Vendor Codes](https://techdocs.altium.com/display/ADOH/Vendor+Codes)

#### Layers

| Layer         | Description                                                       | Line Width 	|
| --- 			| --- 																| --- 			|
| Overlay		| Silkscreen														| 0.2 mm 		|
| Mechanical 1  | 3d model and component outline                                    | 0.1 mm 		|
| Mechanical 15 | Component courtyard and reference origin							| 0.1 mm 		|
| Mechanical 25 | Top placement, component outline and .Designator string in middle | 0,1 mm 		|
| Mechanical 26 | Bottom placement, same as top layer if applicable 				| 0.1 mm 		|

##### Mechanical 1 - 3d model and component outline
The 3d model is often made with a "place -> 3d body" and can either be a simple "box" with the width, lenght and height of the actual component. The component outline outlines with 0.1 mm wide lines where the 3d body ends.

##### Mechanical 15 - Courtyard & Reference origin
The courtyard is used to describe the distance from the component and land patterns to components around. [IPC-7251](http://www.ipc.org/committee/drafts/1-13_d_7251WD1.pdf) is a standard for land patterns and describes the point and requirements for courtyard excess.

In the DTU Altium Library nominal courtyard excess is used: 0.25 mm from the outer bondaries of the component.


### Integrated

### Naming Convention


## Licenses
Under no circumstances must any licensed content excluding academic OR commercial use be used in the building of the components. This in general applies to especially 3d models found on the internet.

## Online Guides

We suggest you read:

[Component Development best practices - Part 1](https://resources.altium.com/pcb-design-blog/component-development-best-practices-part-1)

[What's in a Name - Component Development Part 2](https://resources.altium.com/pcb-design-blog/whats-in-a-name-component-development-part-2)

[What's the best way to make a library searchable? Parameters - Component Development Part 3](https://resources.altium.com/pcb-design-blog/whats-the-best-way-to-make-a-library-searchable-parameters-component-development-part-3)
