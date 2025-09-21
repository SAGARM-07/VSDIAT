## 📅 WEEK-01

# 🚀 DAY-01 – LEARNING
---
## 🛠️ **Icarus Verilog (iverilog)**

- It's a **free tool** that lets you **simulate Verilog code**.
- Think of it like a "Verilog compiler" — it checks your design and runs it to see how it behaves.
- You write your Verilog code, compile it with `iverilog`, and run the output to test your circuit.

```bash
iverilog design.v testbench.v   # Compile
./a.out                         # Run simulation
```

---

## 🧪 **Design & Testbench**

- **Design**: Your actual digital circuit written in Verilog (e.g., a multiplexer, adder, etc.).
- **Testbench**: A separate Verilog file that **feeds inputs** to your design and **checks outputs**.

### Simple Analogy:
- Design = Washing machine
- Testbench = Person pressing buttons and checking if clothes are clean

---

## 👀 **GTKWave**

- A **waveform viewer**.
- After simulation, you get a `.vcd` file (like a log of signal changes).
- GTKWave shows how signals change over time — like a graph of your circuit’s behavior.

```bash
gtkwave simulation.vcd
```

---

## ⚙️ **Yosys Commands**

Yosys is a tool that **converts Verilog code into gates** (logic synthesis).

### 🔹 `read_verilog`
- Loads your Verilog file into Yosys.

```yosys
read_verilog design.v
```

### 🔹 `read_liberty`
- Loads a `.lib` file — this contains info about the gates (like speed, power, etc.).

```yosys
read_liberty -lib path/to/library.lib
```

### 🔹 `synth`
- Converts your Verilog design into a gate-level version using the library.

```yosys
synth -top design_name
```

---

## 🔧 **Logic Synthesis**

- It's the process of **turning your Verilog code into actual gates** (AND, OR, NOT, etc.).
- The result is a **netlist** — a list of gates and how they’re connected.
- This is what goes onto a chip!

---

## ⏱️ **Setup Time & Hold Time**

These are **timing rules** for flip-flops (memory elements):

### 🕒 Setup Time
- Data must be **stable before** the clock edge.
- If it's changing too close to the clock, the flip-flop might miss it.

### 🕒 Hold Time
- Data must stay **stable after** the clock edge.
- If it changes too soon, the flip-flop might get confused.

### Simple Diagram:
```
         |<-- Setup -->|<-- Hold -->|
Data ----|============|============|---->
         ↑            ↑            ↑
       Clock Edge   Clock Edge   Clock Edge
```

> Violating these can cause **errors** or **unpredictable behavior** in your circuit.

---

## 🧠 Summary

| Concept         | What It Means                                |
|----------------|-----------------------------------------------|
| Icarus Verilog | Simulates Verilog code                        |
| Design         | Your digital circuit                          |
| Testbench      | Feeds inputs and checks outputs               |
| GTKWave        | Shows signal changes over time                |
| Yosys          | Converts Verilog to gate-level netlist        |
| Setup Time     | Data stable **before** clock edge             |
| Hold Time      | Data stable **after** clock edge              |
| Logic Synthesis| Turns code into real gates for chip design    |

---

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








