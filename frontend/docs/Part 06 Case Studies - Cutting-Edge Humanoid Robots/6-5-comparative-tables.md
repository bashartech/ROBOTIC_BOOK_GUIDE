---
title: Comparative Tables
sidebar_position: 5
---

## Features, Sensors, Actuators, AI Models

Comparing different humanoid robots is essential for understanding the diverse engineering and AI approaches taken in the field. While each robot has its unique design and purpose, a structured comparison across key features, sensor suites, actuator technologies, and underlying AI models reveals common trends and distinguishing characteristics. This section provides detailed comparative tables for prominent humanoid robots discussed in previous chapters.

### Comparative Table 1: General Features and Capabilities

| Feature/Robot | Tesla Optimus (Projected)                      | Boston Dynamics Atlas                              | Unitree H1 (Bipedal)                               | Agility Robotics Digit (Bipedal)                      |
| :------------ | :--------------------------------------------- | :------------------------------------------------- | :------------------------------------------------- | :---------------------------------------------------- |
| **Purpose**   | General-purpose labor, factory/domestic        | Research (dynamic locomotion, manipulation)        | General-purpose, versatile mobility, research        | Logistics, material handling                          |
| **Form Factor** | Human-sized, bipedal                           | Human-sized, bipedal                               | Human-sized, bipedal                               | Human-sized, bipedal                                  |
| **Actuation** | Electric (custom-designed)                     | Hydraulic                                          | Electric (high-torque servos)                      | Electric (custom-designed, compliant)                 |
| **Weight**    | ~57 kg (125 lbs)                               | ~80 kg (176 lbs)                                   | ~47 kg (103 lbs)                                   | ~65 kg (143 lbs)                                      |
| **Speed**     | ~8 km/h (5 mph)                                | ~2.5 m/s (5.6 mph) running                         | ~5 km/h (3.1 mph)                                  | ~1.5 m/s (3.4 mph)                                    |
| **Payload**   | ~20 kg (44 lbs)                                | ~11 kg (24 lbs)                                    | ~30 kg (66 lbs)                                    | ~16 kg (35 lbs)                                       |
| **Key Skills**| Factory tasks, picking, potentially domestic   | Dynamic agility, parkour, backflips, manipulation  | Robust walking, stair climbing, light manipulation  | Package handling, walking on varied terrain, stairs   |
| **Status**    | Development, prototypes                        | Research platform                                  | Commercial, research                               | Commercial, pilot deployments                         |

### Comparative Table 2: Sensors and Perception Systems

| Sensor Type   | Tesla Optimus                                  | Boston Dynamics Atlas                          | Unitree H1                                         | Agility Robotics Digit                         |
| :------------ | :--------------------------------------------- | :--------------------------------------------- | :------------------------------------------------- | :--------------------------------------------- |
| **Cameras**   | Multiple RGB cameras (FSD vision stack)        | Stereo depth cameras                           | Stereo depth cameras, RGB camera                   | Stereo depth cameras                           |
| **LIDAR**     | Minimal/None (vision-first philosophy)         | None explicitly (uses depth sensors)           | Optional/Integrated for navigation                 | Optional/Integrated for navigation             |
| **IMU**       | Yes (for pose estimation, balance)             | Yes (highly accurate, for dynamic control)     | Yes (high-frequency for balance)                   | Yes (for pose estimation, balance)             |
| **Force/Torque Sensors**| Yes (in hands, feet for manipulation/balance) | Yes (at joints, feet for whole-body control) | Yes (at feet for balance, ground contact)          | Yes (at feet, potentially hands)               |
| **Other**     | Ultrasonic (potentially), encoders             | Joint encoders                                 | Joint encoders, microphone                         | Joint encoders                                 |
| **Perception Focus**| Object detection, semantic segmentation, 3D reconstruction from vision | 3D depth for obstacle avoidance, footholds, proprioception | 3D mapping, obstacle avoidance, human detection, proprioception | 3D mapping, obstacle avoidance, proprioception |

### Comparative Table 3: Actuators and Power Systems

| Actuator/Power| Tesla Optimus                                  | Boston Dynamics Atlas                          | Unitree H1                                         | Agility Robotics Digit                         |
| :------------ | :--------------------------------------------- | :--------------------------------------------- | :------------------------------------------------- | :--------------------------------------------- |
| **Actuator Type**| Custom Electric Actuators (servo-based)        | Custom Hydraulic Actuators                     | Custom High-Torque Electric Servos                 | Custom Electric Actuators                      |
| **Joints/DOF**| High DOF, human-like range                     | High DOF (~28), human-like range               | ~40 DOF, human-like range                          | 20 DOF (total), designed for human-like movement |
| **Power Source**| Lithium-ion Battery Pack                       | Lithium-ion Battery Pack                       | Lithium-ion Battery Pack                           | Lithium-ion Battery Pack                       |
| **Power Density**| High (for electric)                            | Extremely High (hydraulic)                     | High (for electric)                                | High (for electric)                            |
| **Efficiency**| High (electric)                                | Lower (hydraulic, due to pumps/heat)           | High (electric)                                    | High (electric)                                |
| **Complexity**| Integrated, efficient design                   | Complex, fluid power management                | Integrated, compact design                         | Integrated, robust design                      |

### Comparative Table 4: AI Models and Control Strategies

| AI/Control    | Tesla Optimus                                  | Boston Dynamics Atlas                          | Unitree H1                                         | Agility Robotics Digit                         |
| :------------ | :--------------------------------------------- | :--------------------------------------------- | :------------------------------------------------- | :--------------------------------------------- |
| **Core AI Models**| End-to-end Neural Networks (vision), RL, Task Planning | Model Predictive Control (MPC)                 | Reinforcement Learning (RL), Hybrid Control        | Model Predictive Control (MPC)                 |
| **Control Strategy**| Vision-based autonomy, Real-time control      | Whole-Body Control, Dynamic Balance Control    | Robust dynamic locomotion, impedance control       | Robust walking, balance control, whole-body planning |
| **Learning Paradigms**| Supervised Learning (from FSD data), RL      | Optimization, some RL for higher-level behaviors | Reinforcement Learning (sim-to-real), Supervised   | Optimization, Model-based control              |
| **Decision Making**| AI-driven task decomposition, goal-oriented   | Reactive, real-time for dynamic maneuvers      | Reactive, adaptive to terrain, path planning       | Task-specific planning, obstacle avoidance     |
| **Autonomy**  | High, intended for independent operation       | High for dynamic tasks, often human-supervised for complex missions | High for locomotion, moderate for manipulation/interaction | High for specified logistics tasks             |
| **Simulation Used**| Internal Tesla simulators, potentially Isaac Sim | Custom simulators, MuJoCo                      | Custom physics simulators, PyBullet                | Custom simulators                              |

These comparisons highlight that while all these robots represent significant achievements in humanoid robotics, their underlying technologies and architectural choices are tailored to their specific design goals and intended applications.
