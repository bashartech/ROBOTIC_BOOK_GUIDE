---
title: Appendices
sidebar_position: 3
---

## Formulas, Algorithms, Pseudocode, Diagrams

This appendix provides a compilation of fundamental formulas, algorithms, pseudocode snippets, and textually described diagrams that underpin many of the concepts discussed in "PHYSICAL AI AND HUMANOID ROBOTICS." It serves as a quick reference for readers seeking to revisit the mathematical and algorithmic foundations of humanoid robot design, control, and AI.

### A.1 Kinematics Formulas

Kinematics describes the motion of a robot without considering the forces. Here are fundamental transformations.

*   **Homogeneous Transformation Matrix (HTM)**: Combines rotation and translation into a single 4x4 matrix, representing the pose (position and orientation) of one frame relative to another.
    ```
    T = [ R  p ]
        [ 0  1 ]
    ```
    Where `R` is a 3x3 rotation matrix, `p` is a 3x1 position vector, `0` is a 1x3 zero vector, and `1` is a scalar.

*   **Rotation Matrix (2D Rotation around Z-axis)**:
    ```
    R_z(θ) = [ cos(θ) -sin(θ) 0 ]
             [ sin(θ)  cos(θ) 0 ]
             [   0       0    1 ]
    ```

*   **Forward Kinematics (General)**:
    `P_tool = FK(q)`
    Where `P_tool` is the pose of the end-effector and `q` is the vector of joint variables.

*   **Inverse Kinematics (General)**:
    `q = IK(P_tool)`
    Calculates the joint variables `q` needed to achieve a desired end-effector pose `P_tool`. This is often non-linear and may have multiple solutions or no solution.

### A.2 PID Control Pseudocode (Revisited)

The PID controller is a cornerstone of feedback control systems in robotics.

```
pseudocode
// Initialize variables outside the loop
integral_sum = 0.0
previous_error = 0.0
Kp = proportional_gain
Ki = integral_gain
Kd = derivative_gain

function PID_Control_Loop(setpoint, measured_value, delta_time):
    // Calculate current error
    error = setpoint - measured_value

    // Proportional term
    P_term = Kp * error

    // Integral term: sum of past errors
    integral_sum = integral_sum + error * delta_time
    I_term = Ki * integral_sum

    // Derivative term: rate of change of error
    derivative = (error - previous_error) / delta_time
    D_term = Kd * derivative

    // Combine terms for total control output
    output = P_term + I_term + D_term

    // Store current error for next iteration's derivative calculation
    previous_error = error

    return output

// This pseudocode describes a single PID control loop often run at high frequency
// for each controlled variable (e.g., joint angle, motor speed).
```

### A.3 Simplified Q-learning Algorithm Pseudocode (Revisited)

Q-learning is a fundamental reinforcement learning algorithm for discrete state-action spaces.

```
pseudocode
// Parameters
learning_rate (α) = 0.1 // How much to update Q-value based on new information
discount_factor (γ) = 0.9 // Importance of future rewards
exploration_rate (ε) = 1.0 // Initial exploration vs. exploitation trade-off
exploration_decay_rate = 0.001 // Rate at which ε decreases
min_exploration_rate = 0.01

Initialize Q-table: Q[state, action] with zeros or small random values

for each episode (e.g., 1 to num_episodes):
    current_state = environment.reset() // Get initial state
    done = false

    while not done:
        // Choose action using ε-greedy strategy
        if random() < exploration_rate:
            action = choose_random_action()
        else:
            action = choose_action_with_max_Q(current_state) // Exploit

        // Take action, observe reward and new state
        new_state, reward, done = environment.step(action)

        // Update Q-value using Bellman equation
        old_q_value = Q[current_state, action]
        max_future_q = max(Q[new_state, :]) // Max Q-value for next state

        new_q_value = old_q_value + α * (reward + γ * max_future_q - old_q_value)
        Q[current_state, action] = new_q_value

        current_state = new_state

    // Decay exploration rate
    exploration_rate = max(min_exploration_rate, exploration_rate * (1 - exploration_decay_rate))

// The learned Q-table can then be used by the robot to make optimal decisions.
```

### A.4 Textually Described Diagram: Sensor Fusion Data Flow

This diagram illustrates how data from multiple sensors can be combined to produce a more robust and accurate perception of the environment.

```
+-----------------------+   +-----------------------+   +-----------------------+
|      Camera Data      |   |       LIDAR Data      |   |         IMU Data      |
| (2D Image, Color)     |   | (3D Point Cloud, Depth) |   | (Orientation, Velocity) |
+-----------+-----------+   +-----------+-----------+   +-----------+-----------+
      |                         |                         |
      V                         V                         V
+----------------------------------------------------------------------------------+
|                             Data Pre-processing                                  |
| (Noise Filtering, Calibration, Time Synchronization, Coordinate Transformation)  |
+----------------------------------------------------------------------------------+
      |
      V
+----------------------------------------------------------------------------------+
|                             Sensor Fusion Algorithm                              |
|        (e.g., Kalman Filter, Extended Kalman Filter, Particle Filter, DNN Fusion)|
+----------------------------------------------------------------------------------+
      |
      V
+----------------------------------------------------------------------------------+
|                         Fused Perception Output                                  |
|      (e.g., Robust 3D Map, Accurate Robot Pose, Integrated Object List)          |
+----------------------------------------------------------------------------------+
      |
      V
+----------------------------------------------------------------------------------+
|                       High-Level AI and Control Systems                          |
|             (Navigation, Manipulation, Task Planning, Balance Control)           |
+----------------------------------------------------------------------------------+

// This diagram shows how raw data from disparate sensors (Camera, LIDAR, IMU) undergoes
// pre-processing (filtering, synchronization, transformation) before being fed into a Sensor Fusion Algorithm.
// The algorithm then produces a more accurate and comprehensive Fused Perception Output,
// which is critical input for the robot's High-Level AI and Control Systems.
```

This appendix provides a concise summary of essential technical details that underpin the advanced concepts in humanoid robotics, serving as a practical aid for deeper understanding and implementation.
