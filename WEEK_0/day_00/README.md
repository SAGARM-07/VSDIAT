# VSD-Tapeout

# WEEK 0

**TASK-1**

-----------------------------------------------------------------------------

# ASIC/SoC Design Flow 🚀

This repository demonstrates the complete flow of designing a chip — from high-level modeling to real-world application. The design process is broken into four key stages:

- ✅ O1: C-based Chip Specification
- ✅ O2: RTL Design using Verilog
- ✅ O3: SoC Integration and Synthesis
- ✅ O4: Final Fabricated Chip in Products

---

# Complete SoC/ASIC Design Flow (O1 → O4)
# 🔹 O1 – Chip Modeling (C-Level Specification)
The journey starts with specifying the chip's behavior using a C model.

A testbench (also in C) is used to simulate and verify the model.

**✅ Purpose:** To define what the chip is supposed to do.

-----------------------------------------------------------------------------

# 🔹 O2 – RTL Architecture (Design Using Verilog)
The behavior from O1 is now translated into RTL code (Verilog).

This is the soft copy of hardware — the blueprint of logic circuits.

**Key components:**

1. Processor

2. Peripherals/IPs
   

Verified again with the same C testbench to ensure behavior is preserved.

**✅ Goal:** RTL design behaves exactly like the C model (O1 = O2).

-----------------------------------------------------------------------------

# 🔹 O3 – SoC Integration (Synthesized & Combined)

The RTL is synthesized into gate-level netlists.

**Includes:**

1. Macros (Synthesized modules like memory, DSPs)

2. Analog IPs (functional analog blocks)

3. SoC Integration (combining everything incl. GPIOs)

4. Now the design is physically mapped — ready for layout.

Verified again to ensure no behavioral change post-synthesis.

**✅ Target: Integrated hardware still matches the specs (O1 = O2 = O3)**

-----------------------------------------------------------------------------

**🔹 RTL2GDS – Physical Design**

**Steps:** Floorplanning, Placement, Clock Tree Synthesis (CTS), Routing

**Outputs a GDSII file** — the final layout to send for fabrication.

**Runs checks:** DRC (Design Rule Check) and LVS (Layout vs Schematic)

-----------------------------------------------------------------------------

# 🔹 O4 – Fabricated Chip in Real Products

The final chip is fabricated and installed in actual devices:
|---------------------------------------|
|⌚ iWatch                              |
|                                       |
|🔌 Arduino boards                      |
|                                       |
|📺 TV panels                           |
|                                       |
|❄️ AC appliances                       |


Functionality is verified again via C testbench, confirming:

✅ O1 = O2 = O3 = O4
(i.e., final chip behaves exactly like the initial spec)

-----------------------------------------------------------------------------

## 📌 Flow Overview

| Stage | Description                                | Verified With     |
|-------|--------------------------------------------|--------------------|
| O1    | Chip modeled in C                          | C Testbench        |
| O2    | RTL logic using Verilog                    | C Testbench        |
| O3    | Synthesized gate-level netlist + SoC       | C Testbench        |
| O4    | Final chip in devices (iWatch, Arduino...) | Real-world testing |

All stages ensure `O1 = O2 = O3 = O4` ✅

------------------------------------------------------------------------

  **Task-2:**    Install Tools

  **Welcome to the first week of your journey! Before we dive into the exciting world of VLSI design, we'll get your virtual workspace set up with all the essential tools.**

Before you begin, ensure your virtual machine meets the following requirements:

    Operating System: Ubuntu 20.04+
    RAM: 6GB
    HDD: 50 GB
    vCPU: 4

  ( Even u can do it in windows through virtual machine )

  **Install the Tools**

Start by opening your terminal and updating your system's package list. This ensures you're installing the latest versions of all software. 
<div >

```
sudo apt-get update
```

</div>

<img width="859" height="270" alt="Image" src="https://github.com/user-attachments/assets/6fa08007-bc14-48eb-a725-ab735d82eff8" />


------------------------------------------------------------------------

**1.Yosys**

**Yosys synthesizes Verilog code, converting a circuit's behavioral description into an optimized netlist of logic gates.**


First, clone the Yosys repository from GitHub:
<div >

```
git clone https://github.com/YosysHQ/yosys.git
```

</div>

<img width="777" height="148" alt="Image" src="https://github.com/user-attachments/assets/b22993d4-bebf-44c1-972f-9b3bb8fe6b53" />


Next, navigate into the new directory and install the necessary dependencies and build the tool:
<div >

```
git clone https://github.com/YosysHQ/yosys.git cd yosys
sudo apt install make (If make is not installed please install it)
sudo apt-get install build-essential clang bison flex \libreadline-dev gawk tcl-dev libffi-dev git \graphviz xdot pkg-config python3 libboost-system-dev \libboost-python-dev libboost-filesystem-dev zlib1g-dev
make config-gcc
make
sudo make install
```

</div>
These commands will compile and install Yosys and all its required libraries.

<img width="737" height="442" alt="Image" src="https://github.com/user-attachments/assets/f3d48cf9-92ed-47d8-8822-400c1e9e9a38" />

**Now you are done with Yosys**

------------------------------------------------------------------------

**2.Iverilog**

**Icarus Verilog (iverilog) is a Verilog compiler and simulator used to verify the functionality of a digital circuit design.**

Just run the commands
<div >

```
sudo apt-get update
sudo apt-get install iverilog
```

</div>

This will download and install the latest version of Iverilog, making it ready for your simulations.
<img width="784" height="569" alt="Image" src="https://github.com/user-attachments/assets/50f3eba8-d5a6-494f-bda5-fb08a7cfbd73" />

**Now you are done with Iverilog**

------------------------------------------------------------------------

**3.gtkwave**

**GTKWave is an open-source waveform viewer used in digital circuit design.**

Just run the commands
<div >

```
sudo apt-get update
sudo apt install gtkwave
```

</div>

This will download and install the latest version of gtkwave, making it ready for your simulations.
<img width="678" height="91" alt="Image" src="https://github.com/user-attachments/assets/814fabb8-0737-4a6a-80da-adcea0dc31b1" />

**Now you are done with gtkwave**






