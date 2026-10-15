# Cable Harness Specifications

## System Overview
This slide set contains the electrical schematics, pinout diagrams, cable harness routing plans, and interconnect specifications for the Habitat Mapping Camera System (HabCam).

As a continuously towed underwater imaging vehicle operating near the seabed, the HabCam relies on oceanographic sensors, imaging systems, and acoustic tools. The cable harnesses described herein provide the link between the centralized vehicle telemetry housing, power distribution manifolds, and individual payload sensors.

## Cable Harness Design
All HabCam cable assemblies are engineered to withstand prolonged immersion in seawater under hydrostatic pressure, high tension, and continuous vibration. Design criteria include:

- **Wet-Pluggable Connectors:** Utilize marine-grade wet-mate circular connectors (e.g., SubConn, Impulse, Glenair) rated for deep-water hydrostatic pressures.
- **Mechanical Protection:** Cables feature heavy-duty polyurethane or neoprene outer jackets with embedded water-blocking compounds and Kevlar strain-relief strength members.
- **Noise Mitigation:** High-speed data pairs and sensitive optical feedback lines utilize individual foil wrapping, tinned-copper braided shielding, and isolated analog/digital ground returns to eliminate EMI and crosstalk from power lines.
- **Color-Coded Conductor Wiring:** Standardized color coding (following marine instrumentation standards) is maintained across all sub-assemblies to facilitate rapid deck repairs.

## Maintenance
To ensure system reliability during sea trials and survey operations, technicians must adhere to the following servicing guidelines:

**Connector Care & Lubrication:**
- Inspect rubber faces and O-rings for grit, salt crystals, or hair prior to deployment.
- Apply a light coating of Dow Corning 111 silicone grease to neoprene connector faces.
- Never use petroleum-based lubricants, as they degrade neoprene seals.

**Bend Radius & Mechanical Anchoring:**
- Maintain a minimum static bend radius of 6x the cable diameter, and a dynamic bend radius of 10x the cable diameter.
- Secure all cables along the 304 Stainless Steel frame using rubber-lined P-clamps and heavy-duty UV-resistant cable ties.

**Dummy Plug Usage:**
- Always cap un-mated bulkhead connectors with protective dummy plugs immediately upon disconnect on deck to protect pin contacts from salt spray.

---

## Cable Harness Master

| Schematic Reference | Connector Model (Vehicle &rarr; Device Side) | Pin Count | Primary Protocol / Signal | Operating Voltage |
| :--- | :--- | :--- | :--- | :--- |
| **HabCamV4 - Chanos Cable** | 13-Pin Circular &rarr; 13-Pin Circular | 13 &rarr; 13 | Biogeochemical Data + Dual Power Rails | +12 VDC |
| **HabCamV4 Wiring - Camera Power Ethernet Cable** | 13-Pin Circular &rarr; 13-Pin Rectangular | 13 &rarr; 13 | Ethernet Data + Camera Power + Strobe Sync | System Power / Strobe Voltage |
| **Cable Wiring - A-Sphere** | SubConn MCIL4F &rarr; SubConn MCIL6F | 4 &rarr; 6 | RS232 Serial Data (Moxa Interface) + Power | +24 VDC |
| **Microstrain 3DM-GX3-25 AHRS** | SubConn MCIL6F &rarr; SubConn MCIL4F | 6 &rarr; 4 | RS232 Serial Data (Moxa Interface) + Power | +12 VDC |
| **HabCamV4 - BlueView Cable** | SubConn DIL13M &rarr; Teledyne Impulse Titan | 13 &rarr; 10 | Sonar TX/RX Differential + Power | 12-48 VDC |
| **Cable Wiring - Benthos PSA916 Sonar Altimeter** | SubConn MCIL6F &rarr; Impulse RMG-6FS | 6 &rarr; 6 | RS-232 Serial Data (Moxa Interface) + Power | +12 VDC (+6–24V Range) |
| **Cable Wiring - HabCam V4 Eco-Triplet** | SubConn MCIL6F &rarr; SubConn MCIL6F | 6 &rarr; 6 | RS232 Serial Data (Moxa Interface) + Power | +12 VDC |

---

## Individual Cable Specs

### Chanos Cable 

![Chanos Cable Schematic](https://github.com/user-attachments/assets/1adccfc7-2298-4c57-984e-4bfab114408a){width="90%"}

**Schematic Reference:** HabCamV4 - Chanos Cable  
**Primary Function:** Connects the Chanos in-situ biogeochemical analyzer to the HabCamV4 system for ocean chemistry data collection and sensor power.

**Key Specifications:**
- **Connector Configuration:** 13-pin circular connector on the vehicle hub end (P1) to a 13-pin circular connector on the Chanos sensor end (P2).
- **Power Conductors:** Dual +12 VDC power rails using 18 AWG conductors (#18 WHT and #18 RED) paired with dual 18 AWG ground returns (#18 BLK and #18 GRN).
- **Data & Signal Lines:** 24 AWG color-coded twisted pairs for differential communications and control lines.
- **Cable Shielding:** Pin 2 on both ends is dedicated to the cable screen/shield grounding.

**Pin Allocation Callouts:**
- **Power Supply (+12V DC):** P1 Pins 3 & 12 (#18 WHT & #18 RED) &rarr; P2 Pins 3 & 12
- **Power Ground (GND):** P1 Pins 1 & 13 (#18 BLK & #18 GRN) &rarr; P2 Pins 1 & 13
- **Screen / Cable Shield:** P1 Pin 2 &rarr; P2 Pin 2
- **Signal Lines (24 AWG):**
  - P1 Pin 4 (#24 BRN) &rarr; P2 Pin 4
  - P1 Pin 5 (#24 BRN/WHT) &rarr; P2 Pin 5
  - P1 Pin 6 (#24 BLU) &rarr; P2 Pin 7
  - P1 Pin 7 (#24 BLU/WHT) &rarr; P2 Pin 6
  - P1 Pin 8 (#24 ORN) &rarr; P2 Pin 8
  - P1 Pin 9 (#24 ORN/WHT) &rarr; P2 Pin 9
  - P1 Pin 10 (#24 GRN) &rarr; P2 Pin 10
  - P1 Pin 11 (#24 GRN/WHT) &rarr; P2 Pin 11

---

### Camera Power Ethernet Cable

![Camera Power Ethernet Cable Schematic](https://github.com/user-attachments/assets/1adccfc7-2298-4c57-984e-4bfab114408a){width="90%"}

**Schematic Reference:** HabCamV4 Wiring - Camera Power Ethernet Cable  
**Primary Function:** Delivers primary system power, strobe synchronization signals, and high-speed Ethernet data between the central telemetry hub and the main camera system.

**Key Specifications:**
- **Connector Configuration:** 13-pin circular connector on the hub end (P1) to a 13-pin rectangular connector on the camera housing end (P2).
- **Power & Strobe Conductors:** Heavy-gauge 18 AWG conductors dedicated to camera power delivery and strobe pulse timing:
  - Camera Power: #18 RED (Camera Power) paired with #18 BLK (Camera Ret)
  - Strobe Control: #18 WHT (Strobe Signal) paired with #18 GRN (Strobe Ret)
- **Ethernet Data Lines:** 8 color-coded 24 AWG conductors forming four twisted pairs for high-speed Ethernet telemetry.
- **Cable Shielding:** Pin 2 on both connectors connects directly to the cable screen/shield for noise suppression.

**Pin Allocation Callouts:**
- **Camera Return (GND):** P1 Pin 1 (#18 BLK) &rarr; P2 Pin 1
- **Screen / Cable Shield:** P1 Pin 2 &rarr; P2 Pin 2
- **Strobe Signal:** P1 Pin 3 (#18 WHT) &rarr; P2 Pin 3
- **Ethernet Data Lines (24 AWG):**
  - P1 Pin 4 (#24 BRN/WHT) &rarr; P2 Pin 4
  - P1 Pin 5 (#24 BRN) &rarr; P2 Pin 5
  - P1 Pin 6 (#24 BLU) &rarr; P2 Pin 6
  - P1 Pin 7 (#24 BLU/WHT) &rarr; P2 Pin 7
  - P1 Pin 8 (#24 ORN/WHT) &rarr; P2 Pin 8
  - P1 Pin 9 (#24 ORN) &rarr; P2 Pin 9
  - P1 Pin 10 (#24 GRN) &rarr; P2 Pin 10
  - P1 Pin 11 (#24 GRN/WHT) &rarr; P2 Pin 11
- **Camera Power:** P1 Pin 12 (#18 RED) &rarr; P2 Pin 12
- **Strobe Return:** P1 Pin 13 (#18 GRN) &rarr; P2 Pin 13

---

### A-Sphere Cable Wiring

![A-Sphere Cable Schematic](https://github.com/user-attachments/assets/7b16fff8-3262-47b5-923d-b643877b3de8){width="90%"}

**Schematic Reference:** Cable Wiring - A-Sphere  
**Primary Function:** Connects the A-Sphere instrument to the HabCam system to supply system power (+24V DC) and handle RS232 serial data communication.

**Key Specifications:**
- **Connector Configuration:** SubConn 4-pin inline female connector (MCIL4F) with lock collar and snap ring (MCDLS-M / MCDLS Snap Ring) on the HabCam side (P1) to a SubConn 6-pin inline female connector (MCIL6F) on the A-Sphere instrument side (P2).
- **Power Lines (P1 - HabCam Side):** Dual 18 AWG conductors for +24V DC power (#18 RED & #18 GRN) and dual 18 AWG conductors for Power Ground (#18 BLK & #18 WHT).
- **Serial Communication (P2 - Instrument Side):** 20 AWG color-coded conductors providing RS232 transmit, receive, and signal ground connections between the instrument and the internal Moxa serial server.

**Pin Allocation Callouts:**
- **P1 (HabCam Side - Power):**
  - Pins 1 & 2 (#18 BLK & #18 WHT): Power Ground
  - Pins 3 & 4 (#18 RED & #18 GRN): +24V DC
- **P2 (A-Sphere Side - RS232 Serial Data):**
  - Pin 1 (BLK #20): RS232 RX (Instrument)
  - Pin 2 (WHT #20): RS232 TX (Instrument)
  - Pin 3 (GRN #20): RS232 TX (Moxa)
  - Pin 4 (ORN #20): RS232 RX (Moxa)
  - Pin 5 (BLU #20): RS232 Signal Ground

---

### Microstrain Cable

![Microstrain Cable Schematic](https://github.com/user-attachments/assets/c90159af-3fc6-4f7c-897f-2826acea4ef9){width="90%"}

**Schematic Reference:** Cable Wiring - Microstrain 3DM-GX3-25 AHRS  
**Primary Function:** Connects the Microstrain 3DM-GX3-25 AHRS (Attitude and Heading Reference System) bottle to the HabCam telemetry bottle for real-time roll, pitch, and orientation tracking via an internal Moxa serial server.

**Key Specifications:**
- **Connector Configuration:** SubConn 4-pin inline female connector (MCIL4F) on the AHRS Bottle side (P1) to a SubConn 6-pin inline female connector (MCIL6F) on the HabCam Bottle side (P2). Both connectors utilize locking collars and snap rings (MCDLS-M / MCDLS Snap Ring).
- **Power Supply:** +12 VDC power rail and dedicated power ground bridging the two bottles.
- **Serial Communication:** RS232 serial telemetry links the AHRS instrument transmit/receive lines directly to the Moxa serial port interface.

**Pin Allocation Callouts:**
- **P1 (AHRS Bottle Side):**
  - Pin 1 (#18 BLK): Power Ground
  - Pin 2 (#18 WHT): +12V DC
  - Pin 3 (#18 RED): Instrument RS232 TX (signals to Moxa RX)
  - Pin 4 (#18 GRN): Instrument RS232 RX (signals from Moxa TX)
- **P2 (Electronics Bottle Side):**
  - Pin 1 (BLK #20): Power Ground
  - Pin 2: Unused / No Connection (NC)
  - Pin 3 (RED #20): +12V DC
  - Pin 4 (GRN #20): Moxa RS232 RX
  - Pin 5 (ORN #20): Moxa RS232 TX
  - Pin 6 (BLU #20): Moxa RS232 GND

---

### BlueView Cable

![BlueView Cable Schematic](https://github.com/user-attachments/assets/a90c4bdc-8003-4ed6-a2f9-6bcc87025911){width="90%"}

**Schematic Reference:** HabCamV4 - BlueView Cable  
**Primary Function:** Connects the BlueView Mk2 multibeam acoustic imaging sonar to the HabCam central telemetry hub for real-time forward obstacle avoidance and seabed monitoring.

**Key Specifications:**
- **Connector Configuration:** SubConn 13-pin circular male connector (DIL13M) with a locking sleeve collar (DLSA-M / DLSA-Snap Ring) on the vehicle hub end (P1) to a Teledyne Impulse Titan Series 10-pin right-angle connector (MKS(W)-10-CCP-RA) on the sonar end (P2).
- **Cable Stock:** Underwater ethernet-rated cable (D-P4TP24#SW or equivalent).
- **Signal Protocol:** Differential Sonar TX/RX data communications using 24 AWG color-coded conductors.
- **Operating Voltage:** Wide-range input (12–48 VDC) utilizing 18 AWG primary power conductors feeding split 24 AWG pin terminations at the sonar connector.

**Pin Allocation Callouts:**
- **Power Ground:** P1 Pin 1 (#18 BLK) &rarr; P2 Pins 7 & 8 (#24 YEL/WHT & YEL)
- **Power Supply (12–48 VDC):** P1 Pins 2 & 3 (#18 WHT) &rarr; P2 Pins 4 & 5 (#24 BLU/WHT & BLU)
- **Sonar RX+ / RX-:** P1 Pin 8 (#24 ORN) & Pin 9 (#24 ORN/WHT) &rarr; P2 Pin 1 & Pin 2
- **Sonar TX+ / TX-:** P1 Pin 11 (#24 GRN/WHT) & Pin 10 (#24 GRN) &rarr; P2 Pin 3 & Pin 6
- **Unused Terminations:** P1 Pins 4, 5, 6, 7, 12, 13; P2 Pins 9, 10

---

### Sonar Altimeter Cable

![Sonar Altimeter Cable Schematic](https://github.com/user-attachments/assets/a46ecd7c-a77a-49b4-9b27-b9b9f1c37974){width="90%"}

**Schematic Reference:** Cable Wiring - Benthos PSA916 Sonar Altimeter  
**Primary Function:** Connects the Teledyne Benthos PSA-916 Sonar Altimeter directly to the electronics bottle to deliver height-above-seabed measurements to an internal Moxa serial interface.

**Key Specifications:**
- **Connector Configuration:** Impulse 6-pin female connector with locking sleeve (RMG-6FS -w/ Sleeve) on the altimeter end (P1) to a SubConn 6-pin inline female connector (MCIL6F) with snap ring and locking collar (MCDLS Snap Ring / MCDLS-F) on the electronics bottle end (P2).
- **Power Supply:** Accepts wide input range (+6 to 24V) at the altimeter, powered via a +12V DC rail and external power ground line from the electronics bottle.
- **Serial Communication:** RS-232 input/output lines route directly to the Moxa serial port interface (Rx, Tx, and RS-232 GND).

**Pin Allocation Callouts:**
- **P1 (Altimeter Side - Impulse RMG-6FS):**
  - Pin 1: RS-232 Input / External Key Input
  - Pin 2: External Power GND
  - Pin 4: RS-232 Output / Error Output
  - Pin 5: External Power (+6–24V)
  - Pins 3 & 6: Unused / No Connection (NC)
- **P2 (Electronics Bottle Side - SubConn MCIL6F):**
  - Pin 1: Power GND
  - Pin 2: Unused / No Connection (NC)
  - Pin 3: +12V DC
  - Pin 4: Moxa RS-232 Tx
  - Pin 5: Moxa RS-232 Rx
  - Pin 6: RS-232 GND

---

### Eco-Triplet Cable

![Eco-Triplet Cable Schematic](https://github.com/user-attachments/assets/6b8aa09c-f0d6-455f-8388-0fbc7dcf5e35){width="90%"}

**Schematic Reference:** Cable Wiring - HabCamV4 Eco-Triplet  
**Primary Function:** Connects the Sea-Bird / WET Labs ECO Triplet fluorometer bulkhead directly to the HabCam electronics bottle for environmental optical sampling and data transmission.

**Key Specifications:**
- **Connector Configuration:** SubConn 6-pin inline female connector (MCIL6F) on the ECO Triplet bulkhead side (P1) to a matching SubConn 6-pin inline female connector (MCIL6F) on the electronics bottle side (P2). Both ends are secured with locking collars and snap rings (MCDLS-M / MCDLS Snap Ring).
- **Power Supply:** Delivered over a +12 VDC power line with a shared power ground return using 20 AWG conductors.
- **Serial Communication:** RS232 serial interface routing instrument transmit and receive lines to the internal Moxa serial server.

**Pin Allocation Callouts:**
- **P1 (ECO Triplet Bulkhead Side):**
  - Pin 1 (#20 BLK): Power Ground
  - Pin 2 (#20 WHT): Instrument RS232 RX (connects to Moxa TX)
  - Pin 3: Unused / No Connection (NC)
  - Pin 4 (#20 GRN): +12V DC
  - Pin 5 (#20 ORN): Instrument RS232 TX (connects to Moxa RX)
  - Pin 6: Unused / No Connection (NC)
- **P2 (Electronics Bottle Side):**
  - Pin 1 (BLK #20): Power Ground
  - Pin 2: Unused / No Connection (NC)
  - Pin 3 (RED #20): +12V DC
  - Pin 4 (GRN #20): Moxa RS232 TX
  - Pin 5 (ORN #20): Moxa RS232 RX
  - Pin 6 (BLU #20): Moxa RS232 GND

