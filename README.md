# DC Motor Speed Control via DC-DC Buck Converter ⚙️⚡

A closed-loop control system simulation designed to regulate the speed of a Separately Excited DC Motor under varying load torque conditions. 

This project was developed using **MATLAB & Simulink** by the Department of Electromechanical Engineering at **Addis Ababa Science and Technology University (AASTU)**.

## 🎯 Project Overview
In industrial automation (such as conveyor belt systems), sudden load variations can cause severe motor speed fluctuations, disrupting assembly lines and reducing efficiency. 

The objective of this project is to maintain a constant motor speed ($200 \text{ rad/sec}$) despite dynamic and randomized load disturbances. This is achieved by utilizing a **DC-DC Buck Converter** to regulate the motor's armature voltage, controlled by a finely tuned **PID (Proportional-Integral-Derivative) Controller**.

## 🛠️ Software & Tools
* **Simulation Environment:** MATLAB / Simulink (Simscape Electrical)
* **Control Strategy:** Closed-Loop PID Control (PWM-based voltage regulation)

## 🧩 System Architecture
1. **Power Conversion (Buck Converter):** Steps down the DC input voltage to a lower, regulated DC output voltage using an IGBT/Diode switching device and an RLC filter network.
2. **Separately Excited DC Motor:** 
   * Armature Resistance ($R_a$): $0.6 \Omega$
   * Armature Inductance ($L_a$): $0.012 H$
   * Torque Constant ($K_t$): $0.95 \text{ Nm/A}$
   * Inertia ($J$): $0.05 \text{ kg} \cdot \text{m}^2$
3. **PID Controller:** Adjusts the PWM duty cycle based on the error between the reference speed and actual motor speed. 
   * **Tuned Gains:** $K_p = 80$, $K_i = 800$, $K_d = 0$ *(Operating primarily as a PI controller to eliminate steady-state error and prevent noise instability).*
4. **Load Dynamics:** A "Random Number" block simulates unpredictable, real-world mechanical torque acting on the motor shaft (Mean: $90$, Variance: $0.5$).

## 📊 Simulation Results
The system was tested under severe, randomized load conditions over a 1-second simulation stop time. The closed-loop system successfully demonstrated:
* **Initial Acceleration:** Rapidly reaches the $200 \text{ rad/sec}$ reference speed.
* **Robust Transient Response:** Recovers almost instantly from sudden load torque disturbances without significant oscillations.
* **Steady-State Performance:** Effectively tracks and maintains the constant reference speed, proving its viability for precision conveyor belt applications.

## 🚀 How to Run the Simulation
1. Clone this repository to your local machine.
2. Open **MATLAB** and navigate to the project folder.
3. Open the Simulink model (`.slx` file).
4. Click the **Run** button to simulate the system.
5. Open the Scope blocks to view the live dynamic responses of the **Motor Speed**, **Electrical Torque**, and **Output Current**.

## 👥 Team Members
**Addis Ababa Science and Technology University (AASTU)**  
*College of Engineering | Dept. of Electromechanical Engineering*

* **Desalegn Lulie** (ID: ETS0486/14)
