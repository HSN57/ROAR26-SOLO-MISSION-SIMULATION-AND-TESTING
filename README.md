# ASU ROAR'26 – Solo Mission
## Simulation, Testing & Verification/Validation Track

---

## Timeline

| Part | Focus | Recommended Duration |
|------|-------|----------------------|
| Part 1 | Autonomous Systems Fundamentals | 2 days |
| Part 2 | Simulation (Gazebo + ROS 2) | 4 days |
| Part 3 | Testing & Validation | 2 days |
| **Total** | | **8 days** |

---

## General Notes

- **Recommendation:** It is highly recommended to start with Part 1, as the fundamental knowledge covered there is necessary to fully understand and complete Parts 2 and 3.
- **Submission Format:** A separate report must be made for each part (three reports in total). Besides your work and answers, each report **must** contain a Table of Contents and a Conclusion detailing what you learned, how you benefited from this part, and a summary of the outputs.
- **Important Note on Submission:** We fully recognize that the workload for this task is
heavy given the tight timeframe. Because of this, completeness is not strictly required for
your evaluation. Please submit whatever partial work you have completed by the deadline.
We highly appreciate all the effort you are putting into this solo mission, and your work
will be evaluated fairly based on what you are able to deliver.
- You are allowed to use AI tools; however, you must clearly understand and be able to justify everything you submit.
- Focus on clarity, structured thinking, and engineering reasoning.
- Avoid purely theoretical answers — always connect concepts to real system behavior.
- **Final Note (Important):** If you encounter errors during implementation, document them clearly and explain your debugging process. Demonstrating how you approach and resolve issues is a critical part of this assessment.

---

## Report Formatting Bonus (+5 pts)

- **2 pts** for using LaTeX to compile your reports. *(Hint: You can use AI to generate the LaTeX code; we don't expect you to learn LaTeX from scratch. Feel free to use an online compiler like [TeXpage](https://www.texpage.com) or [Overleaf](https://www.overleaf.com/).)*
- **3 pts** for general quality: formal format, professional structure, and well-detailed explanations.

---

## Environment Specification

| Item | Required Value |
|------|----------------|
| OS | Ubuntu 22.04 |
| ROS 2 distro | Humble |
| Gazebo version | Ignition |

**Installation Guides:**
- [WSL Installation Guide](https://www.youtube.com/watch?v=Rzg144v3hfo&t=69s&ab_channel=KskRoyal)
- [ROS 2 Installation Guide](https://www.youtube.com/watch?v=flT3LIIR5qo&ab_channel=RoboticsBack-End)


---

## Scoring Summary

| Section | Questions / Tasks | Points |
|---------|-------------------|--------|
| **Part 1 — Fundamentals** | | **35 pts** |
| General | Q1–Q4 | 8 pts |
| ROS 2 | Q1–Q2 | 5 pts |
| Path Planning | Q1–Q5 | 8 pts |
| Control | Q1–Q5 | 6 pts |
| Localization | Q1–Q3 | 4 pts |
| Perception | Q1–Q3 | 4 pts |
| **Part 2 — Simulation** | | **40 pts** |
| Robot Setup | URDF + TF tree | 10 pts |
| Sensor Integration | IMU + camera topics | 8 pts |
| Sensor Validation | IMU analysis | 6 pts |
| Environment Setup | Gazebo world + markers | 6 pts |
| Perception Integration | ArUco + RViz | 6 pts |
| System Verification | Tools + evidence | 4 pts |
| **Part 3 — Testing & Validation** | | **25 pts** |
| Q1 | V&V distinction | 3 pts |
| Q2 | Module limitations | 4 pts |
| Q3 | Environmental corner cases | 4 pts |
| Q4 | Test scenario design | 4 pts |
| Q5 | Stress testing | 4 pts |
| Q6 | Benchmarking strategy | 3 pts |
| Q7 | Quantitative metrics | 3 pts |
| **Total** | | **100 pts** |
| Bonus B1 | Test script | +8 pts |
| Bonus B2 | Mock ROS 2 nodes | +7 pts |
| Bonus B3 | Report Formatting | +5 pts |
| **Max with bonus** | | **120 pts** |

---

## Part 1 – Autonomous Systems Fundamentals
**Section total: 35 pts**

### Objective
Evaluate your understanding of the core concepts behind autonomous systems and your ability to reason about their behavior in real-world scenarios.

---

### General
*Subtotal: 8 pts*

**Q1.** `— 2 pts`

Provide a structured explanation of what it means for a system to be autonomous. In your answer, identify the main software modules that form an autonomous system (such as perception, localization, planning, and control), and explain how data flows between these modules during operation.

**Q2.** `— 2 pts`

Explain the role of simulation and testing throughout the development lifecycle of an autonomous system. Your answer should describe how simulation contributes to system design, validation, and risk reduction before real-world deployment.

**Q3.** `— 2 pts`

Discuss the limitations of simulation environments when modeling real-world systems. Provide specific technical reasons why a simulated system may behave differently from its real-world counterpart, including aspects related to physics, sensing, and timing.

**Q4.** `— 2 pts`

In the context of Gazebo or similar simulators, explain what it means for a sensor model to be unrealistic. Your answer should include how inaccuracies in noise, bias, update rate, or environmental interaction can affect system performance.

---

### ROS 2
*Subtotal: 5 pts*

**Q1.** `— 3 pts`

Explain the following ROS 2 concepts: node, topic, publisher, subscriber, message, and launch file. Rather than giving isolated definitions, describe how these components work together to form a distributed robotic system.

**Q2.** `— 2 pts`

Explain Quality of Service (QoS) policies in ROS 2. Describe the role of reliability and durability settings and how a mismatch between publisher and subscriber QoS can cause communication failures.

---

### Path Planning
*Subtotal: 8 pts*

**Q1.** `— 2 pts`

Define path planning and explain its role within the navigation stack of an autonomous robot. Your answer should describe how a robot determines a feasible trajectory from its current position to a goal while respecting environmental and kinematic constraints.

**Q2.** `— 2 pts`

Explain the difference between global and local path planners. In your answer, describe how each planner operates, what type of information it uses, and how both planners interact during real-time navigation.

**Q3.** `— 2 pts`

Compare occupancy grid maps and height maps as methods for representing an environment. Discuss the advantages, limitations, and appropriate use cases for each representation.

**Q4.** `— 1 pt`

Explain the A\* algorithm in detail, including how it uses cost functions and heuristics to find an optimal path. Discuss the conditions under which A\* guarantees optimality.

**Q5.** `— 1 pt`

Explain the Artificial Potential Field (APF) method for local path planning. In your answer, describe how attractive and repulsive forces are used, and discuss the main limitations of this approach.

---

### Control
*Subtotal: 6 pts*

**Q1.** `— 1 pt`

Define control theory in the context of physical systems and explain its purpose in robotics applications.

**Q2.** `— 1 pt`

Explain the difference between open-loop and closed-loop control systems. Your answer should include how feedback influences system behavior and performance.

**Q3.** `— 1 pt`

Describe what it means for a controller to be stable. Provide an explanation in practical terms, focusing on system behavior over time.

**Q4.** `— 2 pts`

Explain the Pure Pursuit algorithm and describe the geometric principle behind how it guides a robot along a path.

**Q5.** `— 1 pt`

Compare standard Pure Pursuit with Adaptive Pure Pursuit. Explain why adaptation is necessary and how it affects performance under different operating conditions.

---

### Localization
*Subtotal: 4 pts*

**Q1.** `— 1 pt`

Explain the concept of sensor fusion and describe why it is necessary in autonomous systems.

**Q2.** `— 2 pts`

Describe the structure and function of an IMU. Explain the type of data it produces and how this data is used within a localization pipeline, including the effects of noise and drift.

**Q3.** `— 1 pt`

Explain the Kalman Filter and the Extended Kalman Filter. Highlight the key differences between them and describe when each should be used.

---

### Perception
*Subtotal: 4 pts*

**Q1.** `— 2 pts`

Explain how LiDAR sensors and cameras capture information from the environment. Compare the type of data they produce, their processing requirements, and their typical failure conditions.

**Q2.** `— 1 pt`

Explain the difference between monocular and stereo camera systems, particularly in terms of depth estimation and computational complexity.

**Q3.** `— 1 pt`

Explain what ArUco markers are and how they are detected. Describe what information can be extracted from a detected marker and how this information could be used in a localization or manipulation task.

---

## Part 2 – Simulation (Gazebo + ROS 2)
**Section total: 40 pts**

### Objective
Build a simulated robotic system and demonstrate your ability to validate its behavior and debug its integration.

> **Reference Guides (Starting Point):** The following video tutorials are provided as a helpful starting point. **You are not limited to these specific methods.** You are highly encouraged to explore and implement your work in this part in any way you see fit.
> - [Tutorial 1](https://youtu.be/BcjHyhV0kIs)
> - [Tutorial 2](https://youtu.be/IjFcr5r0nMs)

> **Submission format:** You are required to submit a narrated video demonstrating and explaining all of your work. In addition, you must provide the specific deliverables outlined in each section: all screenshots, plots, and text explanations must be included directly in your **written report**, while all other files (e.g., code, rosbag files, recorded RViz sessions) must be organized within your submitted **part folder**.

---

### Robot Setup
*Subtotal: 10 pts*

Design and implement a custom robot model using URDF. Your submission must include:

| Deliverable | Points |
|-------------|--------|
| Complete `.urdf` or `.xacro` file — syntactically valid and spawnable in Gazebo | 4 pts |
| Screenshot or exported image of the complete TF tree via `rqt_tf_tree` | 3 pts |
| Written explanation of each coordinate frame and its relationship to adjacent frames | 3 pts |

> **Scoring guide:** Full marks for a working URDF with at least base link + wheel links + sensor links. TF tree must be consistent (no broken transforms). Frame explanation must address parent-child relationships and axis conventions.

---

### Sensor Integration
*Subtotal: 8 pts*

Integrate an IMU and a camera into your robot model. Ensure both sensors publish data correctly to ROS 2 topics.

| Deliverable | Points |
|-------------|--------|
| Screenshot for IMU plugin correctly configured and publishing to a ROS 2 topic | 3 pts |
| Screenshot for Camera plugin correctly configured and publishing image data | 3 pts |
| Written justification of sensor placement based on realistic design reasoning | 2 pts |

---

### Sensor Validation
*Subtotal: 6 pts*

Analyze the IMU data generated in simulation and discuss its characteristics.

| Deliverable | Points |
|-------------|--------|
| Quantitative or qualitative analysis of IMU noise and bias in simulation | 2 pts |
| Discussion of drift behavior over time | 2 pts |
| Comparison to real-world IMU behavior and assessment of simulation fidelity | 2 pts |

---

### Environment Setup
*Subtotal: 6 pts*

Create a custom Gazebo world and place 4 ArUco marker poles ([provided in the assets folder](https://github.com/HSN57/ROAR26-SOLO-MISSION-SIMULATION-AND-TESTING/tree/master/assests/Part%202%20-%20ArUco%20Marker%20Poles)) at four different coordinates that form a square shape *(a pole at each square vertex)*.

| Deliverable | Points |
|-------------|--------|
| Custom `.world` file loads without errors | 2 pts |
| Screenshot showing ArUco marker poles placed with the specified pattern | 2 pts |
| Screenshot showing at least two markers visible to the robot's camera at startup | 2 pts |

---

### Perception Integration
*Subtotal: 6 pts*

Run the provided ArUco marker detection node ([in assets folder](https://github.com/HSN57/ROAR26-SOLO-MISSION-SIMULATION-AND-TESTING/tree/master/assests/Part%202%20-%20ArUco%20Marker%20Detection%20and%20Tracking%20Node)) and visualize results in RViz.

| Deliverable | Points |
|-------------|--------|
| Screenshot for ArUco detection node running and publishing marker pose data | 2 pts |
| Screenshot showing robot TF frames visible in RViz | 2 pts |
| Screenshot for detected marker frames overlaid correctly in RViz | 2 pts |

---

### System Verification
*Subtotal: 4 pts*

Demonstrate correct end-to-end system operation using ROS 2 tools.

| Deliverable | Points |
|-------------|--------|
| Screenshot for `rqt_graph` showing all nodes and topic connections | 1 pt |
| TF tree exported via `ros2 run tf2_tools view_frames` with no broken transforms | 1 pt |
| Evidence of correct sensor-to-perception data flow (topic echo or plot) | 1 pt |
| Written summary identifying any anomalies found and how they were resolved | 1 pt |

---

## Part 3 – Testing & Validation
**Section total: 25 pts**

### Objective
Evaluate your ability to reason about system reliability, failure modes, and structured testing methodology.

> **System Context:** To answer the questions in this section, you must base your analysis on the specific rover system architecture, environmental conditions (Poland scenario), and micro-ROS integration specifics provided in the case study.
>
> **Case Study:** [Case Study PDF](https://github.com/HSN57/ROAR26-SOLO-MISSION-SIMULATION-AND-TESTING/blob/master/assests/Part%203%20-%20Case%20Study/ROAR%20-%20Case%20Study.pdf)

---

**Q1.** `— 3 pts`

Explain the difference between verification and validation in the context of autonomous systems. Provide practical examples of each within the system described in this assignment.

**Q2.** `— 4 pts`

For each major module — Perception, Localization, Path Planning, and Control — identify its key limitations and describe the specific conditions under which it may fail or degrade in performance. Relate your answer to the rover system described above.

**Q3.** `— 4 pts`

Analyze the environmental challenges that could affect the autonomous system operating in the described scenario (e.g., weather conditions, terrain variability, visibility constraints). Explain how these factors can produce corner cases that are difficult to handle.

**Q4.** `— 4 pts`

Design simulation test scenarios that specifically target the corner cases identified in Q3. For each scenario:
- Name the subsystem being stressed
- Describe the simulated conditions
- Explain what assumption or failure mode is being probed

**Q5.** `— 4 pts`

Describe how you would perform stress testing on each module to push it to its operational limits. Explain what indicators or signals you would monitor to detect performance degradation or failure.

**Q6.** `— 3 pts`

Define a benchmarking strategy for evaluating the system across multiple test runs or software versions. Your answer should include how tests are structured, how results are stored, and how performance is compared across runs.

**Q7.** `— 3 pts`

Define quantitative metrics for each module. For each metric, specify:
- What it measures (e.g., localization RMSE, planning latency, detection recall)
- How it is measured in simulation
- What threshold constitutes acceptable performance
- How it would be tracked over time or across software versions

> **Scoring guide:** 1 pt for defining at least one metric per module (4 modules covered = full point); 1 pt for specifying measurement method for each; 1 pt for providing a threshold and a tracking mechanism.

---

## Bonus
**Max bonus: +15 pts**

---

**B1.** `— up to +8 pts`

Implement at least one test script for a scenario described in Part 3, Q4. Your script should be runnable and include comments explaining each step.

| Criteria | Points |
|----------|--------|
| Script runs without errors | 2 pts |
| Scenario matches one defined in Q4 | 2 pts |
| Code is well-commented and self-explanatory | 2 pts |
| Script produces a measurable pass/fail result or logged output | 2 pts |

**B2.** `— up to +7 pts`

Create one or more mock or simulated ROS 2 nodes to support your testing workflow. Explain how each mock node replaces or supplements a real system component.

| Criteria | Points |
|----------|--------|
| Node(s) run and publish/subscribe to correct topics | 2 pts |
| Mock behavior is realistic (correct message types, update rates) | 2 pts |
| Written explanation of what real component each mock replaces and why | 2 pts |
| Mock node is integrated with the test script from B1 (if completed) | 1 pt |

---

*Remember, if your system works perfectly in Gazebo on the first try, you should probably be terrified — enjoy the autonomous debugging! :)*
