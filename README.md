# DC-motor-control

Schematic for the board is here.

# Design Decisions

## Regulator
MIC5219 - 20V input range
MIC 

## Crystal
NDK (NX3325SA) was chosen because guidelines indicated that Max DI(uW) > 200, and most of Abracon's crystals had a max DI of 100. Anything with CL greater than 18uF was also not acceptable. From Table 30-24, the recommended component values were 12pF for the capacitors and Rs of 2k. This was the smallest crystal that was recommended. Note that it is NX3225GA that was recommended, but the difference appears to be ordering information.

## Reset
A 100R resistor is placed in series with the reset switch to prevent ringing as suggested in the design guide.

# References
1. http://www.ti.com/lit/ds/symlink/tm4c123gh6pm.pdf
2. http://www.ti.com/lit/an/spma059/spma059.pdf
