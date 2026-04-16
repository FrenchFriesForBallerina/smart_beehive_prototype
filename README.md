#  Design and Development of a Smart Beehive Prototype

*A scalable, low power IoT monitoring prototype for precision apiculture.*

**Nominated for 'Best Thesis' 2025 by Clevon Academy & EEK Mainor.**

# 1. The Challenge
High winter mortality (up to 35% in Europe) is driven by critical hive thermodynamics. Manual monitoring is intrusive and causes heat loss. This project delivers a non-invasive, remote monitoring system that predicts starvation and health risks.

# 2. Hardware & Network

<p align="center">
<img src="img/architecture.png" width="850" alt="Smart Beehive System Architecture Diagram">

<em>Figure 1: High-Level System Architecture and Communication Protocols</em>
</p>

## Network Topology:
Star network using **ESP-NOW** for scalable, low-latency device-to-device communication without the need for localized LoRa at each hive.

<p align="center">
<img src="img/scalability_design.png" width="600" alt="Scalable Hive Network Structure">
<br>
<em>Figure 2: Multi-node Star Topology and Scalability.</em>
</p>

## Edge Nodes:
**ESP32-C3 Mini-1** microcontrollers utilizing deep sleep modes to optimize power for remote deployments.
## Gateway:
**ESP32-WROVER-E CAM** acting as the bridge to Firebase Firestore via WiFi.
## Closed-Loop Automation
Implemented **closed-loop automation** via actuator logic. Real-time environmental data (temperature) triggers an automated physical gate regulation simulated with **Tower Pro MG90S** servos.
## Connectivity & Resilience:
Integrated **LoRa (868 MHz)** and **ESP-NOW** protocols to ensure robust, infrastructure-independent performance in remote agricultural environments, prioritizing edge-case connectivity where standard cellular networks fail.

# 3. Software & Optimization
## Memory Management:

<p align="center">
<img src="img/detail_view.png" width="300" alt="Mobile App Detail View">
&nbsp;&nbsp;&nbsp;&nbsp;
<img src="img/list_view.png" width="300" alt="Mobile App Hive List View">

<em>Figure 3: Flutter Mobile Interface: Real-time telemetry and multi-hive management</em>
</p>

Implemented custom **C++ Structs** to minimize payload size (e.g., used uint8 and int16 instead of float to reduce DHT11 data from 14 bytes to 8 bytes), thus optimizing power efficiency.

## State Management:
Used the **BLoC pattern** in Flutter to create a reactive, scalable, and testable mobile UI.

# 4. Methodology
## User-Centric Design 
Project delivery was based on **persona research** and **iterative prototyping**. The solution was refined through multiple stages to ensure the prototype was functional, intuitive, and directly solved the specific pain points of Estonian beekeepers.