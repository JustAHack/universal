New design for universal automation. Improves upon the design in the EV+ branch. Discussion at https://discord.com/channels/181078474394566657/1336361218205814977.
## Features
- Low (or minimal) switching time
- Minimal impact on server performance
- Compact design
- Simple setup and relocation
- Upgrades automatically with better hatches
## Requirements
- Advanced Stocking Input Bus (ME)
- Slightly Larger Chest
- Microcontroller with:
   - Memory (Tier 1)
   - Central Processing Unit (CPU) (Tier 1)
   - Transposer
   - EEPROM flashed with universal program
- ME Components:
   - ME Interface (part)
   - ME Storage Bus
   - ME Drive
   - ME Storage Cell
## Optional Components for Fluid Handling
- Advanced Stocking Input Hatch (ME) and ME Fluid Storage Cell, or any Input Hatch
## Installation Steps
1. Flash the universal program to an EEPROM using a computer running OpenOS.
   - Note: only the first EEPROM needs flashing; the rest can be copied (see NEI).
2. Assemble the Microcontroller in an Electronics Assembler.
3. Position the Microcontroller between:
   - ME Interface
   - ME Drive
   - Slightly Larger Chest
   - (Optional) Input Hatch
4. Insert the storage cells into the ME Drive:
   - Slot 1: ME Storage Cell
   - Slot 2: ME Fluid Storage Cell (if using fluid support)
5. Connect the Slightly Larger Chest to the subnet via an ME Storage Bus set to priority 1, filtered to the relevant non-consumed items.
6. Configure the Advanced Stocking Bus to automatically pull and recipe-check.
   - Do the same for the Advanced Stocking Hatch .
7. For fluid support, set the Input Hatch next to the Microcontroller to priority 1.
## How to Use
Pattern as usual, but include the non-consumed item in the inputs. Ensure the non-consumed items are filtered on the ME Storage Bus going into the Slightly Larger Chest.
## Tips
- You can recycle non-consumed items by adding them to both the input and output of patterns.
   - To allow AE2 to use multiple machines for processing, continuously export these non-consumed items back into the system.
- The storage bus filter can be copy-pasted using a data stick for easier setup.
- The ME Interface can be shared in a wallshared setup since it does *not* have to face into the Microcontroller.
  - Make sure to use cable anchors to keep the main and subnet disconnected.
## Pitfalls
- AE2 Channels Pass Through the Microcontroller
   - Ensure it does not interfere with other network components.
- Dynamic Interface Detection
   - Only one ME Interface should be placed next to the Microcontroller.
- Tank Detection Behavior
   - The Microcontroller detects any neighboring `gt.blockmachines` with tanks as an Input Hatch.
   - Only one Input Hatch should be placed next to it.