# RISC-V-SoC_tapeout-WEEK5
[![RISC-V](https://img.shields.io/badge/RISC--V-Reference%20SoC-blue)](https://riscv.org/)
[![RTL → GDSII](https://img.shields.io/badge/Flow-RTL%20%E2%86%92%20GDSII-purple)](https://en.wikipedia.org/wiki/GDSII)
[![Tapeout Ready](https://img.shields.io/badge/Goal-Tapeout%20Ready-red)](https://en.wikipedia.org/wiki/Photomask)
[![Made in India](https://img.shields.io/badge/Made%20in-India-green)](https://www.makeinindia.com/)

 **Objective:** Execute OpenROAD flow up to Floorplan and Placement stages only.

---

##  Installation Verification

Commands executed and environment setup verified with:
```bash

source ./env.sh

yosys -help

openroad -help
```

<img width="866" height="629" alt="image" src="https://github.com/user-attachments/assets/d4f84217-95d1-4724-b179-7dbc81393654" />

<img width="806" height="651" alt="image" src="https://github.com/user-attachments/assets/7af65959-f286-4be6-aae7-424f8172d3cf" />


### Step 1️— Open the OpenROAD GUI

Run this inside your OpenROAD-flow-scripts folder:
```
cd ~/OpenROAD-flow-scripts/flow
make gui_final
```
This will launch the OpenROAD GUI showing your design layout.

<img width="1222" height="768" alt="image" src="https://github.com/user-attachments/assets/16a67f21-ce93-4f02-944d-51e9ce78cf53" />

### Step 2 

### 1.floor plan view 

- there will be core area (rectangular layout).

- we should see I/O pins around the borders.

This confirms: Core area & die dimensions generated.

<img width="1222" height="768" alt="image" src="https://github.com/user-attachments/assets/4f746c1e-ca44-47fd-9361-274a3062c664" />

### 2. placement view

- Zoom in — we should see lots of small standard cells placed inside the core area.

This confirms: Standard cells are placed successfully.

 <img width="1222" height="768" alt="image" src="https://github.com/user-attachments/assets/36c5aed1-69c4-48fc-92cb-42da0772cb62" />

### Step 3— Review Logs

we can check the logs to show evidence of floorplan and placement completion.

Run these:

```
cd ~/OpenROAD-flow-scripts/flow/logs/nangate45/gcd/base
ls
```
<img width="806" height="651" alt="image" src="https://github.com/user-attachments/assets/e7432b27-5d94-4d87-b5f9-2f026f23c2e3" />

```
cat 2_1_floorplan.log | tail -20
cat 3_5_place_dp.log | tail -20
```

<img width="1222" height="768" alt="image" src="https://github.com/user-attachments/assets/6febc00b-a3bc-4197-9b61-40fc5b666cbc" />

- I executed the flow up to the Floorplan and Placement stages.

- The core area, die dimensions, and standard cell placement were successfully generated and visualized in the OpenROAD GUI.
  
- Minor setup adjustments were handled by ensuring env.sh was sourced correctly.
