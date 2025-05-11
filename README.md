# 🛰️ Rover_Drone_Collab — Autonomous Drone Landing on a Rover

**Inspired by NASA’s Ingenuity and Perseverance**, this simulation demonstrates a Mars-style collaborative system between a drone and a rover. Built using ROS 2, PX4 SITL, Gazebo Harmonic, and MAVROS 2, the project showcases autonomous aerial imaging, MAVLink-based communication, and a critical final step: the **drone autonomously landing on the rover platform for simulated recharging.**

---

##  Motivation

Dust accumulation on solar panels like NASA's Ingenuity limits operational life on Mars. To combat this, we simulate a mission where the drone periodically returns to the rover for recharging and control updates — enabling longer operational time and mission sustainability.

---

## 🌐 Demo Preview

![gazebo_ui](https://github.com/user-attachments/assets/7d582a66-7f45-4b9d-bd63-80a73ddcf81e)

### 🔹 System Overview

![1](https://github.com/user-attachments/assets/578b5714-ca04-48b8-a127-ca4fc109c4a8)


### 🔹 Mission Cycle in Action

https://youtu.be/QOsOVKwhNfg

---
##  System Architecture

| Component           | Description                                                  |
|---------------------|--------------------------------------------------------------|
| **Drone**           | PX4 SITL `x500_gimbal` configured via `gz_x500_gimbal`       |
| **Rover**           | Custom Perseverance-inspired model (SDF format)              |
| **ROS 2**           | ROS 2 Humble handles coordination logic                      |
| **MAVROS 2**        | Interfaces MAVLink commands between PX4 and ROS 2            |
| **Gazebo Harmonic** | Simulates Martian terrain and rover/drone physics            |
| **QGroundControl**  | Used for preflight health checks and status monitoring       |

---

##  Mission Cycle

1. **Drone Launch**  
   PX4 SITL initializes; the drone detaches from the rover's platform and ascends.

2. **Aerial Imaging**  
   Drone captures high-resolution terrain imagery using ROS camera topics.

3. **Image Transfer**  
   Images sent to rover over MAVLink/ROS topics or simulated inter-process bridge.

4. **Rover Path Planning**  
   Rover receives and processes data to generate a safe, optimal path.

5. **Landing Signal**  
   After analysis, the rover signals the drone to return.

6. **Autonomous Drone Landing**  
   Using FSM logic, the drone performs a **precision soft landing** on the rover.

---



