# PrinterInterfaceNabuExtensionRelaY (PINERY)
PINERY - A hardware interface device between the NABU PC (http://www.nabu.ca) and a Centronics/PC-compatible printer.

![PCB](/pcb.png) ![Schematic](/Schematic.png)

The NABU's parallel port is a DB-15-pin connector. Although it obviously does not match the DB-25 connector of the IBM PC/Centronics connector, most pins match, and interfacing them is a matter of mapping pins.

See https://en.wikipedia.org/wiki/Parallel_port for the Centronics parallel port protocol, and https://cloud.nabu.ca/docs/Nabu_PC_Technical_Specifications.pdf "Printer Interface" (p.7) for the NABU parallel port protocol.

## Pinouts
| Signal | NABU | DB-25 |
| ------ |-----:| -----:|
| STROBE |    1 |     1 |
| Data 0 |    2 |     2 |
| Data 1 |    3 |     3 |
| Data 2 |    4 |     4 |
| Data 3 |    5 |     5 |
| Data 4 |    6 |     6 |
| Data 5 |    7 |     7 |
| Data 6 |    8 |     8 |
| Data 7 |    9 |     9 |
| Busy   |   11 |    11 |
| Ground |   15 | 18-25 |

## Unused PC/Centronics Pins
These are optional 2.54mm connectors to allow for expanded use with fancy printers, and can be controlled via a NABU Option Card or other control.
They are  **Ack**, **Paper-Out**, **Select**, **Linefeed**, **Error**, **Reset** and **Select-Printer**.

## Unused NABU Pins
These are optional 2.54mm connectors to expose the unused NABU pins. There is no documented connection. In case they are in fact usable, or can be made usable, they can be mapped to the unused Centronics pins, or wired for some other nefarious purpose. They are pins 10 and 12-14.

## Containment Unit
This has been sized to fit the [Hammond 1551mini box](https://www.digikey.ca/en/products/detail/hammond-manufacturing/1551FBK/1090719?utm_adgroup=General&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_Zombie%20SKUs&utm_term=&productid=1090719&gclid=CjwKCAjwzuqgBhAcEiwAdj5dRs3rq5Sxppuy35osANsapgPSYujJgOChvvt58ERvUnlV1GkpL7u4-hoCjrUQAvD_BwE). Doing so, with the connector tabs external to the box, should bolster the PINERY against the forces of plugging and unplugging. The box will need to be trimmed to allow the connectors to fit.

## ENID Compatibility
Although [ENID] ((https://github.com/mackiea/ExternalNabuInterfaceDevice) also uses a DB-25 interface, it is *not* compatible and is not related to this project.

## So have we tested the dang thing?
Not yet! But the pin mapping is proven to work for an [Apple Dot-Matrix (C Itoh) Printer](https://en.wikipedia.org/wiki/Apple_Dot_Matrix_Printer).
