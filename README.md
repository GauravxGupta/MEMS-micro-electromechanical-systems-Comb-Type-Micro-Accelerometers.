# MEMS-micro-electromechanical-systems-Comb-Type-Micro-Accelerometers.
My summer internship at DRDO's Solid State Physics Laboratory, I worked on the sensitivity analysis of a comb-type MEMS micro-accelerometer. I analyzed how design parameters like beam width and beam length affect device sensitivity, and performed MATLAB-based simulations to study performance metrics including range, bandwidth and noise levels

# Sensitivity Analysis and Design Optimization of a Folded-Beam MEMS Comb-Type Capacitive Micro-Accelerometer

## 📌 Project Overview
This repository focuses on the design optimization, analytical modeling, and sensitivity analysis of a **Poly-Silicon Surface-Micromachined MEMS Comb-Type Capacitive Micro-Accelerometer**. Engineered primarily for low-$g$ safety-critical automotive implementations (e.g., airbag deployment systems), this device maps structural parameters to physical performance boundaries. 

The design addresses critical performance parameters such as sensitivity, mechanical bandwidth, noise floors, and structural limits, using **ANSYS Finite Element Method (FEM) simulation** to cross-validate analytical spring-mass formulations.

---

## 🛠️ Design Architecture & Working Principle
The accelerometer layout utilizes a differential capacitive comb configuration modeled similarly to the standard ADXL 150 architecture.

* **Suspension System:** Employs a folded-beam structure anchored at only two points, which mitigates thin-film package stress issues inherent to straight-beam sensors while increasing mechanical compliance.
* **Transduction Mechanism:** When subject to an external acceleration ($a$), the central proof mass undergoes an inertial displacement ($x$), changing the nominal air gaps ($d_0$) between interlocking movable and fixed comb fingers.
* **Electrical Output:** This displacement translates directly into a measurable change in differential capacitance ($\Delta C = C_1 - C_2$), which is linearly proportional to the applied acceleration under small-deflection thresholds.
* **Built-In Self-Test (BIST):** Features dedicated electrostatic driving fingers that permit complete in-field functionality testing via target voltage inputs.

---

## 📊 Technical Specifications & Optimized Geometries

| Design Parameter | Value / Metric |
| :--- | :--- |
| **Proof Mass Dimensions ($W_m \times L_m$)** | $500\,\mu\text{m} \times 800\,\mu\text{m}$ |
| **Suspension Beam Dimensions ($W_b \times L_b$)** | $2\,\mu\text{m} \times 290\,\mu\text{m}$ |
| **Device Thickness ($t$)** | $30\,\mu\text{m}$ |
| **Nominal Air Gap ($d_0$)** | $2\,\mu\text{m}$ |
| **Sensing Finger Groups ($N_s$)** | 24 |
| **Driving (Self-Test) Fingers ($N_d$)** | 8 |
| **Structural Material** | Poly-Silicon ($E = 150 \times 10^9\,\text{N/m}^2$, $\rho = 2330\,\text{kg/m}^3$) |
| **Measurement Operational Range** | $\pm 10g$ |
| **Total System Spring Constant ($K_{\text{total}}$)** | $2788.6\,\text{N/m}$ |

---

## 📈 Key Sensitivity Analysis Insights
Analytical modeling established explicit structural scaling laws governing sensor design:
1. **Beam Width Effects ($W_b$):** Displacement sensitivity scales inversely with the cube of the width ($S_d \propto 1/W_b^3$), making beam width the most sensitive parameter to control mechanical response. A minimum threshold of $2\,\mu\text{m}$ was maintained to prevent component breakage during fabrication.
2. **Beam Length Effects ($L_b$):** Device sensitivity scales proportionally with length ($S_d \propto L_b^3$), presenting a design trade-off against overall die surface consumption.
3. **Mass Geometry:** Sensitivity retains a direct linear scaling relation with mass width and length ($S_d \propto W_m \cdot L_m$).

---

## 🔬 Core Evaluation Categories Modeled
* **Mechanical Bandwidth:** Derived directly from structural resonance and damping metrics to preserve flat frequency responses over active intervals.
* **Non-Linearity Constraints:** Modeled curvature errors introduced at extensive mass displacements, targeting an optimization goal of keeping non-linearity under $1\%$.
* **Noise Limits:** Characterized the dominant thermal-mechanical noise floors (Brownian motion of the proof mass) to resolve baseline Noise-Equivalent Acceleration (NEA).

---

## 💻 Simulation and Modeling Tools
* **Analytical Modeling:** Hand-derived spring-mass-damper algorithms and capacitive equations.
* **FEM Simulation:** ANSYS (Used to execute parametric sweeps, structural displacement runs, and electromechanical capacitive tracking).
