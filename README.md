# VLSI-LAB-EXP-5
SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

AIM: To simulate and synthesis finite state machine using Xilinx ISE.

APPARATUS REQUIRED:

Vivado™ ML 2023.2

PROCEDURE: 

1.Open Vivado: Launch Xilinx Vivado software on your computer.

2.Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3.Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4.Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5.Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6.Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7.Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8.Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9.View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design


Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)



### FINITE STATE MACHINE
~~~
module fsm_moore( clk, rst, inp, outp);

input clk, rst, inp;

output outp;

reg [1:0] state;

reg outp;

always @(posedge clk, posedge rst)

begin

if(rst)

state<=2'b00;

else

begin

case(state)

2'b00:

begin

if(inp) state <=2'b01;



else state <=2'b10;
end

2'b01:

begin

if (inp) state <=2'b11;
else state<=2'b10;
end

2'b10:
begin
if (inp) state<=2'b01;
else state <=2'b11;
end

2'b11:

begin

if (inp) state <=2'b01;
else state <=2'b10;

end

endcase

end

end

always @(posedge clk, posedge rst)

begin

if(rst)

outp <= 0;

else if(state == 2'b11)

outp <= 1;

else outp<= 0;

end

endmodule

~~~

OUTPUT:

SIMULATION:![image](https://github.com/Madhan0302/VLSI-LAB-EXP-5/assets/160517887/fe95cc6e-84da-4c00-84a5-5e87087ee392)


ELABRATED DIAGRAM:![image](https://github.com/Madhan0302/VLSI-LAB-EXP-5/assets/160517887/22a3d891-75b8-481b-b67a-a58736215bf6)


RESULT:

Simulation And Synthesis Finite State Machine is Successfully Verified using Vivado Software.
