---
title: Actuators & Power Systems
sidebar_position: 3
---

## Motors, Hydraulic Systems, Batteries

Actuators are the 'muscles' of a humanoid robot, responsible for generating physical motion by converting energy into mechanical force. Alongside actuators, robust power systems provide the necessary energy to drive these movements and power all onboard electronics. The choice of actuators and the design of the power system critically impact a robot's strength, speed, precision, and endurance.

### Actuators: Motors

Electric motors are the most common type of actuator in humanoid robots due to their precision, controllability, and relatively clean operation.

*   **Servo Motors**: These are typically DC or AC motors combined with a position feedback sensor (encoder) and a control circuit. They allow for very precise control over joint angles, making them ideal for the articulated joints of humanoids.
    *   **Advantages**: High precision, good torque at various speeds, relatively easy to control.
    *   **Disadvantages**: Can be heavy, limited power density compared to hydraulics for extreme forces.
*   **Brushless DC (BLDC) Motors**: Offer high efficiency, long lifespan, and good power-to-weight ratio. Often used in conjunction with sophisticated gearboxes (harmonic drives) to achieve high torque.
    *   **Advantages**: High efficiency, lower maintenance, good dynamic response.
    *   **Disadvantages**: Requires more complex electronic commutation.

### Actuators: Hydraulic & Pneumatic Systems

For robots requiring extremely high force-to-weight ratios or very fast, powerful movements, hydraulic or pneumatic systems are often employed. These systems use pressurized fluids (oil for hydraulics, air for pneumatics) to transmit force.

*   **Hydraulic Systems**: Use incompressible fluid (oil) to transmit force, offering immense power and stiffness. Best exemplified by Boston Dynamics Atlas.
    *   **Advantages**: Extremely high power density, very strong, can generate high forces.
    *   **Disadvantages**: Heavy, messy (leaks), complex plumbing, requires pumps and reservoirs, less energy efficient.
*   **Pneumatic Systems**: Use compressible fluid (air), generally for lighter-duty applications where high speed and compliant motion are desired.
    *   **Advantages**: Lightweight, clean, can be very fast.
    *   **Disadvantages**: Lower force density than hydraulics, difficult to control precisely due to air compressibility, requires compressors.

### Power Systems: Batteries

Batteries are the primary power source for untethered humanoid robots, providing the electrical energy needed for motors, sensors, and onboard computers.

*   **Lithium-ion (Li-ion) Batteries**: The most common choice due to their high energy density (energy per unit weight), good power delivery capabilities, and long cycle life.
    *   **Advantages**: Excellent power-to-weight ratio, high energy efficiency.
    *   **Disadvantages**: Can be sensitive to overcharging/discharging, safety concerns if damaged, cost.
*   **Power Management Systems**: Crucial for monitoring battery state of charge, managing power distribution to various robot components, and implementing safety cut-offs.

### Diagram: Actuator Types (Textually Described)

```
+---------------------------+
|       Robot Joint         |
| (e.g., Shoulder, Elbow)   |
+-------------+-------------+
              |
              V
+---------------------------+
|        Actuator           |
| (Converts energy to motion)|
+-------------+-------------+
    /        |         \
   /         |          \
  V          V           V
+--------+ +---------+ +----------+
| Electric | | Hydraulic | | Pneumatic|
|  Motor   | |  Cylinder | | Cylinder |
+--------+ +---------+ +----------+
|  (Precise, | | (High Force,| | (Fast,   |
| Efficient) | |  Stiff)   | | Compliant)|
+------------+-------------+------------+

// This diagram illustrates how different actuator types (Electric Motors, Hydraulic Cylinders, Pneumatic Cylinders)
// are connected to a robot joint. Each type has distinct characteristics making it suitable for different robotic requirements.
// Electric motors offer precision and efficiency, hydraulics provide high force and stiffness, and pneumatics offer fast, compliant motion.
```

### Diagram: Simplified Power Distribution (Textually Described)

```
+--------------------------------+
|          Battery Pack          |
| (e.g., Li-ion, Power Mgmt Unit)|
+--------------------------------+
                |
                V
+--------------------------------+
|      Power Distribution Bus    |
| (Voltage Regulation, Circuitry)|
+--------------------------------+
    /       |       |       \
   /        |       |        \
  V         V       V         V
+---------+ +---------+ +---------+ +-----------+
| Actuators | | Sensors | | Onboard | | Aux. Devices|
| (Motors,  | | (Cameras, | | Computer| | (LEDs, Fans)|
| Hydraulics)| | IMUs)   | | (CPU, GPU)|
+---------+ +---------+ +---------+ +-----------+

// This diagram shows a simplified power distribution system within a humanoid robot.
// The main battery pack (with a power management unit) supplies energy to a central
// power distribution bus. This bus then regulates and distributes power to all
// essential robot components: actuators, sensors, onboard computers, and auxiliary devices.
```

The careful selection and integration of actuators and power systems are critical engineering challenges, directly influencing a humanoid robot's performance envelope, operational capabilities, and overall reliability.
