# Rebus Controller
![rebus](https://github.com/benlhy/DC-motor-control/blob/master/rebus.jpg)

This a DC motor controller built around the TI TIVA TM4C123 chip. It has position and velocity control and can be linked up to form a multi-axis system. 

# Layouts

Layout for the standalone board is here:

![layout](https://github.com/benlhy/DC-motor-control/blob/master/Layout.JPG)

Boost board layout:

![boost](https://github.com/benlhy/DC-motor-control/blob/master/boost.JPG)

# Programming

To program this board you will need Launchpad that has the programming pins broken out. Please see the [programming repo](https://github.com/benlhy/DC-Control-Module) for more details.

# Design Decisions

## Motor Driver
TB6612FNG - 2.5 ~ 13.5V, 1.3A per channel, max 3.2A
DRV8848 - 4 ~ 18V, 1A per channel, max 2A

## Regulator
MIC5219 - 20V input range, and comes in 5V flavour and 3.3V flavour

## Crystal
NDK (NX3325SA) was chosen because guidelines indicated that Max DI(uW) > 200, and most of Abracon's crystals had a max DI of 100. Anything with CL greater than 18uF was also not acceptable. From Table 30-24, the recommended component values were 12pF for the capacitors and Rs of 2k. This was the smallest crystal that was recommended. Note that it is NX3225GA that was recommended, but the difference appears to be ordering information.

## Reset
A 100R resistor is placed in series with the reset switch to prevent ringing as suggested in the design guide.

# References
1. http://www.ti.com/lit/ds/symlink/tm4c123gh6pm.pdf
2. http://www.ti.com/lit/an/spma059/spma059.pdf
