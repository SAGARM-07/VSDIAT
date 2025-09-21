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


