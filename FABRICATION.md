# Fabrication
The PFCBoard is an open-source board design - though I (at least currently) do not sell pre-made boards with this design, it's not too challenging to make your own!

All components use large footprints to make hand-soldering fairly straightforward.

## Ordering the PCBs
First, you'll need the blank PCBs - these can be obtained through a service like OSHPark, PCBWay, JLCPCB, etc.

How this is done depends on the board manufacturer, but is usually done by uploading a .zip file containing the board design in the Gerber file format. Some services can take the KiCad project files directly.

[You can find pre-made Gerber files in the Releases](https://github.com/48productions/Perpetual-Free-Credits-PCB/releases) section of this repo, but keep in mind **different board houses may have different requirements for the board design and file format.** Your best bet is to check their site for details, and re-export a new set of Gerbers from KiCad if needed.

## Ordering the Components
PFCBoard v1.0 uses the following components. Connectors aside, all components are SMD. I'll link components I've personally used, here.
 - U1: [555 timer IC, 8-SOIC](https://www.digikey.com/en/products/detail/texas-instruments/SA555DR/555957)
 - U3: [LTV-817S Optoisolator](https://www.digikey.com/en/products/detail/liteon/LTV-817S/385837)
 - C1: [10uF Capacitor, 4mmx4.5mm](https://www.digikey.com/en/products/detail/nichicon/UWJ1C100MCL1GB/2550755)
 - C3: [0.1uF Capacitor, 1206](https://www.digikey.com/en/products/detail/kemet/C1206C104K5RAC7800/411248)
 - C4: [10nF Capacitor, 1206](https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL31B103KHFNFNE/3888735)
 - D1-2: [Yellow](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/150120YS75000/4489948), [Red](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/150120RS75000/4489939) LED, ~2V/20mA max, 1206
 - J1-2: [1713017 Terminal Block](https://www.digikey.com/en/products/detail/phoenix-contact/1713017/2513977)
 - R1: [1k Resistor, 1206](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RMCF1206FT1K00/1759616)
 - R2: [20k Resistor, 1206](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RMCF1206FT20K0/1759766)
 - R3-5: [330r Resistor, 1206](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RMCF1206JT330R/1753819)
 - VR1: [TC33X-2-103E 10k Potentiometer](https://www.digikey.com/en/products/detail/bourns-inc/TC33X-2-103E/612858)

The following can be left unpopulated if the 5V regulator will be bypassed for a 5V coin blocker:
 - U2: [MC78L05FA-TP 5V Regulator, SOT-89](https://www.digikey.com/en/products/detail/micro-commercial-co/MC78L05FA-TP/13689757)
 - C2: [0.33uF Capacitor, 1206](https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL31B334KBFNNNE/3886796)

And if you're feeling really extra:
 - Board Standoffs for a 3mm hole (such as [Digikey #732-9624-ND](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/702915000/5843784))