##  WEEK-01
# DAY-01
____________________________________________________________________
**LAB**

step 1

Clone the repo in your local space
<div >

```
https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```

</div>

Open the root shell in the terminal using
<div >

```
sudo -i
```

</div>

you can find the folder structure like

<img width="210" height="246" alt="Image" src="https://github.com/user-attachments/assets/984d6039-147e-4b49-849e-c663524d1284" />

step 2

Inside the /verilog_files/ folder u can find the files of RTL code and their equivalent testbench codes 
<img width="456" height="255" alt="Image" src="https://github.com/user-attachments/assets/e866e2f3-c540-4b40-b9ab-d6b62e5ae0a2" />

source to the /verilog_files/ folder 

Time to run Icarus verilog

use the code
<div >

```
https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```

<div >

```
iverilog good_mux.v tb_good_mux.v
```

</div>>

an executable file a.out will be created at the same folder

<img width="456" height="255" alt="Image" src="https://github.com/user-attachments/assets/e866e2f3-c540-4b40-b9ab-d6b62e5ae0a2" />

now execute the file using
<div >

```
./a.out
```

<div >
now a dumpfile tb_good_mux.vcd will be obtained

use the code
<div >

```
gtkwave tb_good_mux.vcd
```

<div >
this code will generate a simulation output for the rtlcode and the testbench

<img width="59" height="20" alt="Image" src="https://github.com/user-attachments/assets/6bf6ba65-f376-4f9d-a969-3d4efa3c6635" />

step 3

open yosys using 
<div >

```
yosys
```

<div >
add the liberty file obtained from cloning
<div >

```
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

<div >

then add verilog code file /good_mux_v/
<div >

```
read_verilog good_mux.v
synth -top good_mux
```

<div >
now the hierarchy of the design will be obtained

<img width="369" height="223" alt="Image" src="https://github.com/user-attachments/assets/4f3e68aa-369f-44b6-8ea8-148fbb0700b3" />

then use 
<div >

```
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

<div >
here the ABC results will be shown

<img width="514" height="125" alt="Image" src="https://github.com/user-attachments/assets/7cdb1900-25ec-4956-89e4-b5da7c003cae" />

step 4
to see the netlist 

use the command

<div >

```
show
```

<div >
then the netlist is generated


