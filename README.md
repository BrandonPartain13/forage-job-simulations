# forage-job-simulations
Portfolio of technical projects, diagnostic reports, and code completed through Forage job simulations, including Robotics &amp; Control Engineering.
# Forage Job Simulations Portfolio

A collection of hands-on technical projects, diagnostic analyses, and deliverables completed independently through [Forage](https://www.theforage.com/) virtual job simulations.

> **Simulation Disclosure:** All projects, ticket details, and system metrics in this repository reflect independent educational training exercises and do not represent official company work or proprietary systems.

---

## Completed Simulations

| Simulation | Focus Area | Tools Used | Deliverable |
| :--- | :--- | :--- | :--- |
| **Robotics & Control Engineering** | Diagnostic Analysis & Optimization | Python, Jupyter Notebook | [Diagnostic Report (PDF)](./Robotic_Arm_Diagnostic_Report_GitHub.pdf) |

---

## Project Highlights

### 1. Robotics & Control Engineering Job Simulation
* **Date:** October 27, 2026
* **Simulated Case:** Ticket #2437 — Delayed rotation response in a simulated surgical robotic arm
* **Tools & Techniques:** Python, Jupyter Notebook, timing measurements, iterative testing

#### Problem & Investigation
Investigated the root cause of delayed positioning adjustments in a simulated robotic arm by benchmarking three core control commands: `move_arm`, `rotate_joint`, and `adjust_grip`. Initial testing revealed that `rotate_joint` had the longest response time at **0.151 seconds**, caused by a programmed `time.sleep(0.15)` delay.

#### Optimization & Results
Modified the `time.sleep()` duration in `rotate_joint` from `0.15` seconds to `0.08` seconds while leaving other command delays unchanged.

| Command | Expected Time | Initial Measured | Optimized Measured | Net Change |
| :--- | :---: | :---: | :---: | :---: |
| `move_arm` | 0.100 s | 0.100 s | 0.101 s | +0.001 s (+1.0%) |
| `rotate_joint` | 0.100 s | 0.151 s | 0.080 s | **-0.071 s (-47.0%)** |
| `adjust_grip` | 0.090 s | 0.050 s | 0.051 s | +0.001 s (+2.0%) |

* **Impact:** Reduced simulated `rotate_joint` response time by approximately **71 milliseconds (~47% improvement)**.
* **Next Steps:** Future physical testing would be required to evaluate positioning accuracy and verify performance against defined surgical safety limits.

---

## Author
**Brandon Partain**  
[GitHub Profile](https://github.com/BrandonPartain13)
