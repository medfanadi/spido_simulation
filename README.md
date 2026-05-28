# Spido Robot Gazebo Simulation Framework (4WDS Platform)

![ROS Melodic/Noetic](https://img.shields.io/badge/ROS-Melodic%2FNoetic-blue.svg)
![Gazebo](https://img.shields.io/badge/Simulation-Gazebo-orange.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

This repository hosts the core ROS packages required to simulate the **Spido** robot (RobuFast platform) inside the Gazebo physics environment. It delivers full Unified Robot Description Format (`URDF/Xacro`) configurations, joint actuation controllers, embedded sensor suites, and low-level kinematic interfaces.

<p align="center">
  <img width="697" height="250" alt="Spido Simulation Overview" src="https://github.com/user-attachments/assets/3810c2f4-aaea-4e7e-8091-df463fb5e5a4" />
</p>

---

## 🚜 System Characteristics & Kinematics

The **Spido** robot is a high-speed, all-terrain heavy-duty mobile platform configured with **Four-Wheel Drive and Four-Wheel Steering (4WDS)**. This kinematics configuration allows for advanced locomotion capabilities (such as crabbing or zero-radius turning), making it an ideal benchmark platform for harsh off-road navigation, predictive control engineering, and dynamic stabilization algorithms.

### Technical Architecture Specifications

| Parameter | Specification |
| :--- | :--- |
| **Maximum Velocity ($v_{max}$)** | 12 m/s (~43 km/h) |
| **Total Platform Mass** | ~700 kg |
| **Suspension Geometry** | 4x Dual wishbone independent suspensions |
| **Stabilization Hardware** | 2x Active anti-roll bar actuators |
| **Localization Sensor Suite** | Real-Time Kinematic GPS (RTK-GPS) & High-Frequency IMU |
| **Perception Sensor Suite** | 3D LiDAR for spatial mapping and dynamic obstacle tracking |

---

## 📂 Repository Package Architecture

The workspace is split into four distinct, highly modular ROS packages to separate mechanical descriptions, simulation environments, and control interfaces:

```text
spido_simulation/
├── spido_control/          # ros_control plugin configs, joint trajectory tuning, and hardware managers
├── spido_gazebo/           # Virtual world scenes, physics parameters, and core simulation launch files
├── spido_description/      # URDF/Xacro kinematic profiles, meshes, odometry calculation, and transforms
└── spido_pure_interface/   # Low-level abstraction layer bridging virtual simulation to physical CAN/hardware
