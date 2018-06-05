# 31 May 2018 IHU Conference Call Minutes

A conference call was held on 31 May 2018. Presenting was Jonathan Brandenburg, concerning his IHU project that he wishes to publish. Open Research Institute will support publishing this open source Integrated Housekeeping Unit (IHU) design intended for amateur radio satellite service payloads. An IHU is a flight computer, controlling all the elements of the payload.

The call was held courtesy of National Instruments conference bridge. Thank you to Neel Pandeya for making it possible and for supporting open source hardware and software designs. 

The design team for this IHU consists of Zach Metzinger, Jordan Trewitt, Bill Reed, and Jonathan Brandenburg. This started in earnest about a year ago. It it not radiation hardened by design, but is entirely appropriate for low earth orbit (LEO) use. 

Initial design work was presented at the 2017 AMSAT Symposium. 

This is a failover IHU design. It has two fault-tolerant processors. The processor is TI Hercules and the part number is TMS570LS0914PGE. Each processor has two cores, and each core operates in lock-step. There is some flight heritage with this part from the ICI Radar Satellite and a NASA Robotic ARM. 

Included in the design are twin transceivers. The transceiver selected is the [AX5043](http://www.onsemi.com/PowerSolutions/product.do?id=AX5043).
A power amplifier design is in progress. 

There is error correction on the memories. 

This IHU has two *sides*, with one Hercules and one transceiver on each side. There is diversity in the voltage regulators, with the primary side powered by a MAX1556A regulators and a secondary side powered with LTI963As. The diversity in voltage regulators is intended to provide additional resilience. For each side, there is a 3.3volt rail and a 1.2volt rail.

Software development has only just begun. Layout is approximately 80% complete. 

The board has 4 layers and relatively good power consumption based on prototype measurement. 

[UPSat from Libre Space](https://libre.space/projects/upsat/) was also introduced and referenced.

[OreSat](http://oresat.org/) is interested in collaborating and learning more about this design.

Our consensus is CANbus or Ethernet for flight hardware.

Jonathan has also made a Raspberry Pi daughterboard for the AX5043. This allows development with the transceiver independent of the Hercules or IHU. 

The drawbacks to the Hercules include terrible documentation and a cumbersome parameterized code generation process for development. Jonathan believes he is getting a handle on this and there is the possibility of him producing improved documentation for this design. 

We also discussed the [VA10820 - Radiation Hardened ARM® Cortex®-M0 MCU](https://www.voragotech.com/products/va10820). This is approximately $700, but has good stats and a well-documented toolchain. There is at least one design that is open source that could be used as a basis for an IHU. 

* Jonathan to publish the IHU at https://github.com/phase4space/payload-IHU
* Jonathan and Michelle to press for review of the design.
* Michelle to publish minutes.
* Michelle to arrange for additional IHU conference calls. 

Microsemi’s SmartFusion2 and PolarFire devices were brought up outside of the meeting.  They are actively advertising radiation hardening for these parts and they may be available now and should be discussed. 
