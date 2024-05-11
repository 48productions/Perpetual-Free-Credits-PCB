# Perpetual Free Credits PCB (a.k.a. the PFC PCB)
**A Non-Destructive Arcade Game Coinup Mod PCB**


It keeps compatible games fully credited up at all times, perfect for arcade games that either lack a Free Play mode, or are missing features in Free Play mode that are present in Credit mode.

It's designed solely for games with a **credit limit** that control a **coin blocker** relay based on this limit. If the game isn't at its credit limit, it powers the coin blocker relay (and thus the PFC PCB), which inserts credits until the credit limit is reached, and the game turns off the coin blocker relay. 

---
## Compatibility/Installation

### Compatibility List
This board is **compatible** with:
 - ✅ CHUNITHM (tested on NEW!! and many pre-NEW!! versions)
 - ✅ Middle Earth (Atari pinball)
 - ✅ crossbeats REV. (tested on SUNRISE S2)*
 - ✅ Probably a lot of others :D

This board is **incompatible** with games that have a coin blocker relay, but no credit limit:
 - ❌ SOUND VOLTEX (tested on EXCEED GEAR)
 - ❌ jubeat (tested on festo)

An alternative design is being considered for these games.

*\* crossbeats: This board will continuously insert credits in test mode, since the game always powers the coin blocker in test mode regardless of the credit limit.*

### Checking Compatibility
**For games not on the list, your game MUST:**

 - **Have a coin blocker relay** on the coin acceptor (mostly found in older or JP-import games)
 
 - Power said relay with *10-30VDC* or *5VDC*
 
 - Turn on the relay when the game enters attract mode (you'll hear it click on)
 
 - **Have a credit limit, and will turn off the Coin Blocker when this limit is reached** (this is not always the case)!

In modern games, the relay can usually be toggled on/off in the game's test mode (look for an "Output Test" menu).

---
## Alternative Designs
[ChunUp](https://github.com/progmem/ChunUp) is a very clean and cost-reduced design geared specifically for CHUNITHM cabinets.

---
## Fabrication
**[See FABRICATION.md](FABRICATION.md) for instructions on how to fabricate this design!**


---
## Installation
**[See INSTALLATION.md](INSTALLATION.md) for instructions on how to install this board in your game!**



---
## Troubleshooting
**[See TROUBLESHOOTING.md](TROUBLESHOOTING.md) for instructions on how to troubleshoot common issues!**


---
## No Really How Does This Work

This board connects to the power wires for the Coin Blocker relay on your arcade cabinet, if it has one, through voltage regulator U2. Normally, this relay is attached to the game's coin acceptor and will reject any coins (even valid ones) whenever the game is not ready to accept coins (game powered off, maximum credit limit reached, etc).

When the game is ready to accept coins, it powers the coin blocker to let coins in. This turns on the PFC board, which will repeatedly trigger the game's coin switch using timer U1 through opto isolator U3. When the game hits the maximum credit limit, it powers off the coin relay (and thus the PFC board), which stops inserting coins. This way, your game is always credited up and ready to play.

Timing of the pulses is controlled by capacitor C1, resistor R2 (20k, time between pulses), and resistor/potentiometer R1/VR1 (1k + 0-10k, pulse frequency).


---
## Credits/Disclaimers

This project came about because of a few relevant conversations in the awesome western arcade rhythm game community, and the general concept/design was discussed by several community members.

You are installing this board at your own risk, and I cannot be held liable for damages, destruction, magic smoke escaping, or otherwise.

For arcade games on an official online network, your network may not allow the use of this board or similar mods. As such, usage of this board in these circumstances isn't recommended.

*Any games mentioned are properties of their respective owners. This design was produced independently of them, and is in no way endorsed or officially supported.*
