## 📅 WEEK-01

# 🚀 DAY-01 – LAB

---

### ✅ Step 1: Clone the Repository

Clone the workshop repository to your local machine:

```bash
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```

Switch to the root shell (if needed):

```bash
sudo -i
```

You’ll now see the folder structure similar to this:

![Folder Structure](https://github.com/user-attachments/assets/984d6039-147e-4b49-849e-c663524d1284)

---

### ✅ Step 2: RTL Simulation Using Icarus Verilog

1. **Navigate** to the `/verilog_files/` directory where RTL and testbench files are stored.

   ![Verilog Files](https://github.com/user-attachments/assets/e866e2f3-c540-4b40-b9ab-d6b62e5ae0a2)

2. **Compile** using Icarus Verilog:

```bash
iverilog good_mux.v tb_good_mux.v
```

This will generate an executable file named:

```bash
a.out
```

3. **Run the Simulation**:

```bash
./a.out
```

This produces a waveform dump file:

```bash
tb_good_mux.vcd
```

4. **View Waveform in GTKWave**:

```bash
gtkwave tb_good_mux.vcd
```

This opens the simulation output for both the RTL and testbench.

![GTKWave Example](https://github.com/user-attachments/assets/6bf6ba65-f376-4f9d-a969-3d4efa3c6635)

---

### ✅ Step 3: Logic Synthesis Using Yosys

1. **Start Yosys**:

```bash
yosys
```

2. **Read Liberty File** (from cloned repo):

```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

3. **Read and Synthesize Verilog Code**:

```bash
read_verilog good_mux.v
synth -top good_mux
```

You will now see the synthesized design hierarchy.

![Hierarchy Output](https://github.com/user-attachments/assets/4f3e68aa-369f-44b6-8ea8-148fbb0700b3)

4. **Run ABC for Technology Mapping**:

```bash
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

ABC optimization results will appear:

![ABC Results](https://github.com/user-attachments/assets/7cdb1900-25ec-4956-89e4-b5da7c003cae)

---

### ✅ Step 4: View the Netlist

To view the generated synthesized netlist in Yosys:

```bash
show
```

This will bring up a graphical view of the gate-level netlist.

<img width="1847" height="656" alt="Image" src="https://github.com/user-attachments/assets/7bbb65be-ddcc-4e92-a785-6f4fa602b1bb" />


---

### 📌 Summary

| Tool               | Purpose                      |
| ------------------ | ---------------------------- |
| **Icarus Verilog** | RTL compilation & simulation |
| **GTKWave**        | View simulation waveform     |
| **Yosys**          | RTL synthesis                |
| **ABC**            | Technology mapping           |

---




