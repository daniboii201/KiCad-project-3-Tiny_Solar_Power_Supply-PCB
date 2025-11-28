# KiCad project #3: Tiny Solar Power Supply PCB
This is my third PCB design created using KiCad. Unlike my previous projects, this design is based on an existing project from Elektor Labs called Tiny Solar Supply. The original design was created by Clemens Valens for Elektor, and I recreated it in KiCad as part of my learning journey. All credit for the circuit concept goes to Elektor.

<img width="1359" height="562" alt="image" src="https://github.com/user-attachments/assets/893e9f44-6fb7-4d12-b9b2-ea6cb659442e" />

<img width="1359" height="562" alt="image" src="https://github.com/user-attachments/assets/8f777c78-684f-4a07-b8a4-4b14dbeb768b" />

<img width="1130" height="347" alt="image" src="https://github.com/user-attachments/assets/b05632a8-64c7-4b7f-9d0f-13b02f89608c" />

## Features
• Converts a single 1.2 V Ni-MH AA rechargeable battery into a regulated 3.3 V output

• Designed for solar-powered energy harvesting using small garden-light panels

• Automatic switching: disables boost converter when solar panel is charging the battery

• Compact PCB suitable for integration inside small enclosures

• Ideal for powering low-power devices like microcontrollers

### Components:
• AP3015 step-up DC/DC converter IC (boost regulator)

• Inductor (L1) for energy storage

• SS14 Schottky diodes (CR1, CR2) for efficient rectification and reverse polarity protection

• SMD capacitors (C1–C3) for filtering and stability

• SMD resistors (R1, R2) for output voltage setting

• MOSFET Transistor (T1) for automatic shutdown control

• Pin headers for solar panel, battery, and load connections

### Characteristics:
• Copper on top and bottom layers 

• Implemented vias for interconnection between layers 

• Mostly SMD components for a compact footprint 

• Silkscreen labels for easy assembly and identification 

• Mounting holes for mechanical stability 

• Output voltage set to approximately 3.3 V using feedback resistors 

• Based on Elektor’s original schematic and concept

### How It Works:
During the day, the solar panel charges a single 1.2 V Ni-MH AA rechargeable battery through a diode. At the same time, the panel pulls the gate of a transistor high, which disables the boost converter by pulling its shutdown pin low. When the solar panel voltage drops (at night), the transistor switches off, enabling the boost converter.

The heart of the circuit is the AP3015 step-up DC/DC converter. It takes the battery voltage (as low as 1 V) and boosts it to a regulated output of approximately 3.3 V. The output voltage is set by the feedback resistor ratio using the formula:

Vout = 1.23 * (1 + R1 / R2)

With the chosen resistor values, the output is close to 3.3 V, making it suitable for low-power electronics like microcontrollers.
