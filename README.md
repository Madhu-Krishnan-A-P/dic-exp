# 🔬 Digital Integrated Circuits Lab – 90nm CMOS Technology

**Student:** Madhu Krishnan A P  
**Subject Code:** 24-509-0105  
**University:** Cochin University of Science and Technology (CUSAT)  
**Technology Node:** 90nm CMOS | **VDD = 1V**  
**EDA Tool:** Cadence Virtuoso  

This repository contains schematics, simulation results, and reports for three major Digital IC lab experiments:

- Experiment 1: MOSFET Characterization  
- Experiment 2: Static CMOS Inverter  
- Experiment 3: Combinational Logic Gates  

Each experiment was simulated and analyzed using Cadence Virtuoso using the 90nm GPDK library.

---

## 🧪 Experiment 1 – MOSFET Characteristics

### 📌 Questions

1. Place a long-channel NMOS with L = W = 1 + RollNumber/5 (μm). (e.g., RollNo = 10 → L = W = 3μm)  
2. Plot ID vs VDS for varying VGS with VSB = 0. Extract VT₀, µnCox, and λ.  
3. Repeat with VSB = 0.25V, 0.5V, 0.75V. Observe and explain VTH variation.  
4. Repeat using a short-channel NMOS (L = 200nm). Extract VT₀, µnCox, VDSAT.  
5. Repeat for L = 100nm. Compare parameter changes.  
6. Place a PMOS (L = 200nm, W = 3μm). Plot characteristics.  
7. Compare extracted values with those in the model library.

### 📈 Key Results

#### Long-channel NMOS (L = W = 3μm)
- VT₀ = 238 mV  
- µnCox = 331.29 µA/V²  
- λ = 0.0296751 V⁻¹  

#### VTH vs VSB (Body Effect)
| VSB (V) | VTH (mV) |
|---------|----------|
| 0.00    | 238      |
| 0.25    | 271      |
| 0.50    | 301      |
| 0.75    | 328      |

#### Short-channel NMOS (L = 200nm)
- VT₀ = 139 mV  
- µnCox = 182.69 µA/V²  
- VDSAT ≈ 0.568 V  

#### Short-channel NMOS (L = 100nm)
- VT₀ = 62 mV  
- µnCox = 154.98 µA/V²  
- VDSAT ≈ 0.606 V  

#### PMOS (L = 200nm, W = 3μm)
- DC characteristics plotted  
- Matches library behavior

📎 [`MOSFET Chara.pdf`](./MOSFET%20Chara.pdf)

---

## ⚙️ Experiment 2 – Static CMOS Inverter

### 📌 Questions

1. Draw minimum-width CMOS inverter. Plot VTC and measure VM, VOH, VOL, VIL, VIH.  
2. Apply 2ns square wave input. Measure tPHL and tPLH.  
3. Double PMOS and NMOS widths independently. Measure delays. Derive delay equations.  
4. Add 10fF load. Measure delays. Estimate R for PMOS and NMOS.  
5. Increase load to 20fF. Compare theoretical and simulated delays.  
6. Parametrize PMOS width. Plot VM vs PMOS width. Find width for VM = VDD/2.  
7. Resize for symmetric delays. Vary S from 1 to 5. Estimate delays.  
8. Load with identical inverter. Measure delay. Estimate gate capacitance.  
9. Design inverter chain for 1pF load. Measure and compare delay for N, N+1, N−1 stages.  
10. Estimate dynamic and leakage power for S = 1 to 2 and VDD = 1.0V & 1.1V. Add 10fF load.

### 📈 Key Results

#### Static Performance
- VM ≈ 0.49 V  
- VOH ≈ 0.99 V, VOL ≈ 0.05 V  
- VIH ≈ 0.59 V, VIL ≈ 0.38 V  

#### Delays (Unloaded)
| Configuration  | tPHL (ps) | tPLH (ps) |
|----------------|-----------|-----------|
| Minimum        | ~121      | ~157      |
| PMOS ×2        | ~133      | ~113      |
| NMOS ×2        | ~77       | ~186      |

#### Delays with Load = 10fF
- Delays increase as expected  
- Resistance (R) and Capacitance (C) estimated from slopes

#### Dynamic Power (1ns period, 10fF load)
| S | VDD (V) | Dynamic Power (µW) | Leakage Power (pW) |
|---|---------|---------------------|---------------------|
| 1 | 1.0     | 1.31                | 84.6                |
| 2 | 1.0     | 2.55                | 131.6               |
| 1 | 1.1     | ~1.59               | Higher than 1.0V    |

📎 [`Digital Integrated Circuits Lab Report Exp 3.pdf`](./Digital%20Integrated%20Circuits%20Lab%20Report%20Exp%203.pdf)

---

## 🔧 Experiment 3 – Combinational Logic Gates

### 📌 Questions

1. Draw 2-input CMOS NAND gate. Plot DC characteristics for:  
   i) A = 1, B: 0→1  
   ii) A: 0→1, B = 1  
   iii) A, B: 0→1  
2. Plot transient responses for the above three cases. Measure tPHL and tPLH.  
3. Calculate theoretical delays using RC values from Experiment 2. Compare.  
4. Resize using µn/µp mobility ratio. Measure delays again.  
5. Design pseudo-NMOS NAND. Plot DC and transient responses. Measure delay.  
6. Design dynamic NAND. Plot transient and observe charge leakage.  
7. Design pass-transistor 2:1 MUX. Plot transient. Check if output reaches VDD.  
8. Design transmission gate 2:1 MUX. Plot transient. Check for full swing.

### 📈 Key Results

- CMOS NAND shows expected pull-up/pull-down behavior  
- Delays vary with input pattern due to stacked NMOS  
- Pseudo-NMOS NAND shows degraded high due to weak pull-up  
- Dynamic NAND leaks charge during long precharge intervals  
- Pass transistor MUX fails to reach VDD (threshold drop)  
- Transmission gate MUX has full swing at output  

📎 [`Digital Integrated Circuits Lab Report Exp 4.pdf`](./Digital%20Integrated%20Circuits%20Lab%20Report%20Exp%204.pdf)

---

## 🧠 Concepts Applied

- Transistor-level parameter extraction (VT₀, µnCox, λ)
- Short-channel effect and body effect
- Inverter switching delay and VM tuning
- Load-dependent delay scaling
- Power estimation (dynamic + leakage)
- Logic family comparison (CMOS, pseudo-NMOS, dynamic)
- Delay modeling using RC approximations

---

## 👨‍💻 Author

**Madhu Krishnan A P**  
M.Tech in VLSI & Embedded Systems  
Cochin University of Science and Technology (CUSAT)  
📧 [madhukrishnan@pg.cusat.ac.in](mailto:madhukrishnan@pg.cusat.ac.in)  
🔗 [GitHub](https://github.com/Madhu-Krishnan-A-P) • [LinkedIn](https://www.linkedin.com/in/madhu-krishnan-ap)
