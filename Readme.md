# Smart Water Purification and Monitoring System



A smart water-treatment and monitoring system designed for mining areas where water may contain suspended particles, dissolved contaminants, and potentially radioactive contaminants such as uranium and radium.



# 1. Overview

Mining activities can affect nearby water resources through the release of suspended particles and dissolved contaminants.

Our proposed system combines **multi-stage water purification** with **real-time electronic monitoring**.

The system follows:

Raw Water
↓
Sand Filtration
↓
Chitosan Filtration
↓
RO Filtration
↓
UV Disinfection
↓
Water Quality Monitoring
↓
Final Decision

The ESP32 continuously collects water-quality readings and sends the information to a monitoring dashboard through Wi-Fi.

If a monitored parameter exceeds its predefined limit, the system generates an alert



# 2. Key Features

### Multi-Stage Purification

The system combines sand filtration, chitosan filtration, RO filtration, and UV disinfection to provide multiple treatment stages.

### Real-Time Monitoring

pH, TDS, and turbidity are continuously monitored after treatment.

### ESP32-Based Control

The ESP32 collects sensor data, processes the readings, and manages communication with the monitoring system.

### Wireless Monitoring

Sensor readings can be transmitted to a dashboard through Wi-Fi.

### Automatic Alert System

When a monitored parameter crosses its predefined limit, the system generates an alert.

### Modular Design

Individual treatment and monitoring stages can be maintained or upgraded independently.



# 3. System Workflow

### Step 1 — Raw Water Collection

Water from the mining area enters the purification system.

The incoming water may contain suspended particles and dissolved contaminants.

### Step 2 — Sand Filtration

The first stage uses a sand filter to reduce suspended particles.

This also helps reduce the load on the downstream RO membrane.

### Step 3 — Chitosan Filtration

The filtered water passes through chitosan beads.

The proposed purpose of this stage is to provide additional adsorption and filtration.

Its effectiveness for contaminants such as uranium and radium must be validated through laboratory testing.

### Step 4 — Reverse Osmosis

The water then passes through an RO membrane.

This stage reduces dissolved salts and other dissolved substances.

### Step 5 — UV Disinfection

UV treatment is used as a disinfection stage to help inactivate microorganisms.

### Step 6 — Water Quality Monitoring

The treated water is monitored using:

• pH Sensor
• TDS Sensor
• Turbidity Sensor

### Step 7 — ESP32 Processing

The ESP32:

• Collects sensor readings
• Processes the measured values
• Compares readings with predefined limits
• Sends data to the monitoring dashboard
• Generates alerts when required

### Step 8 — Final Decision

If the monitored parameters remain within the required limits, the water can proceed toward the intended use.

If a monitored parameter exceeds its limit, the system generates an alert and the required corrective action can be taken.



# 4. Hardware Components

### Sand Filter

Used to reduce suspended particles in the incoming water.

### Chitosan Beads

Used as an additional filtration and adsorption stage.

### RO Membrane

Used to reduce dissolved salts and other dissolved contaminants.

### UV Unit

Used for the disinfection stage.

### ESP32

Acts as the central controller for sensor data collection, processing, and communication.

### pH Sensor

Measures the acidity or alkalinity of the water.

### TDS Sensor

Measures the concentration of dissolved substances.

### Turbidity Sensor

Measures the presence of suspended particles in the water.



# 5. Software and Communication

### Arduino IDE / Embedded C

Used for ESP32 programming, sensor interfacing, data processing, and control logic.

### Monitoring Dashboard

Displays real-time sensor readings and system alerts.

### Wi-Fi Communication

The ESP32 transfers the collected sensor information to the monitoring dashboard.



# 6. Monitoring Logic

The monitoring system evaluates the water-quality parameters continuously.

The basic decision structure is:

pH Condition 
TDS Condition 
Turbidity Condition ----→ OR Gate → ALERT
Other Condition 

If any monitored condition becomes abnormal, the OR gate produces an alert signal.

This allows the system to respond to abnormal conditions instead of relying only on manual inspection.



# 7. Simulink Model

The Simulink model represents the monitoring and decision-making logic of the proposed system.

Multiple water-quality conditions are evaluated and combined using logical operations.

The OR-gate logic provides a simple method for detecting whether at least one monitored condition has crossed its specified limit.

The simulation can be used to verify the control logic before implementing it on the physical ESP32-based system.



# 8. Feasibility

The proposed treatment sequence is:

**Sand → Chitosan → RO → UV**

Each stage performs a different function within the overall treatment process.

Sand filtration is placed before RO to reduce suspended particles reaching the membrane.

The ESP32-based monitoring system provides continuous measurement of pH, TDS, and turbidity.

The prototype can initially be tested using prepared water samples before progressing toward field-level testing.



# 9. Challenges

### Variable Water Contamination

Water quality can vary between different mining locations and over time.

### Uranium and Radium Removal

The effectiveness of the proposed chitosan stage for radioactive contaminants requires laboratory validation.

### Sensor Limitations

pH, TDS, and turbidity sensors provide general water-quality information.

They do not directly measure uranium or radium concentration.

### RO Membrane Fouling

Suspended particles and dissolved materials can reduce RO membrane performance over time.

### Filter Maintenance

Filtration materials require periodic cleaning, replacement, or maintenance.

### Radioactive Waste Handling

If radioactive contaminants accumulate in filtration materials, appropriate safety and waste-handling procedures are required.



# 10. Strategies to Address the Challenges

• Place sand filtration before the RO stage.

• Perform laboratory testing for uranium and radium.

• Continuously monitor pH, TDS, and turbidity.

• Regularly maintain the filters and RO membrane.

• Design the system as modular stages for easier maintenance.

• Test the system using controlled water samples before field deployment.

• Follow appropriate safety procedures for potentially contaminated filtration materials.



# 11. Expected Impact

### Social Impact

Provides a technological approach for monitoring and treating water in mining-affected areas.

### Environmental Impact

Supports better management of potentially contaminated water before discharge or reuse.

### Technical Impact

Combines water purification with real-time electronic monitoring in a single system.

### Economic Impact

Continuous monitoring can help identify treatment problems earlier and reduce dependence on frequent manual checking.

### Health Impact

Early identification of abnormal monitored water-quality conditions can support safer water management.



# 12. Project Limitations

The pH, TDS, and turbidity sensors are indicators of general water quality.

They cannot directly determine uranium or radium concentration.

Therefore, radioactive contaminant detection and removal must be validated using appropriate laboratory testing.

The effectiveness of the chitosan filtration stage must also be experimentally evaluated for the specific water composition being treated.



# 13. References

### Reference 1

Coyte et al.

"Large-Scale Uranium Contamination of Groundwater Resources in India"

Environmental Science & Technology Letters, 2018.

DOI:
https://doi.org/10.1021/acs.estlett.8b00215

### Reference 2

Aparna Pallavi.

"Uranium mine waste imperils villages in Jaduguda"

Down To Earth, 15 March 2008.

https://www.downtoearth.org.in/environment/uranium-mine-waste-imperils-villages-in-jaduguda-4306

### Reference 3

National Green Tribunal.

All Dimasa Students Union Dima Hasao District Committee v. State of Meghalaya & Ors.

O.A. No. 73/2014, order dated 17 April 2014.

https://www.downtoearth.org.in/mining/the-unregulated-lethal-and-corrupt-world-of-meghalaya-s-rat-hole-mines-62507



# 14. Disclaimer

This README describes the proposed system presented for Smart India Hackathon 2026.

The actual treatment performance, particularly for radioactive contaminants such as uranium and radium, must be experimentally validated before real-world deployment.

The proposed system should not be considered a certified method for radioactive contaminant removal without appropriate laboratory testing and validation.
