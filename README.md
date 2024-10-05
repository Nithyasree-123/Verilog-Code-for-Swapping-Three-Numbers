# VERILOG-CODE-FOR-SWAPPING-THREE-NUMBERS

## AIM:

To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

## APPARATUS REQUIRED:

Vivado 2023.1 or equivalent Verilog simulation tool.

## PROCEDURE:

Launch Vivado 2023.1:

Open Vivado and create a new project.
Write the Verilog Code for Swapping:

Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
Create the Testbench:

Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
Add the Verilog Files:

Add the Verilog module and the testbench file to the Vivado project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the swapping operation.
Observe the Waveforms:

Examine the waveform to confirm that the values of the three numbers are swapped as expected.
Save and Document Results:

Capture the waveform output and include the results in your report for verification.

## VERILOG CODE:

~~~

module swap_three_numbers ( a_in,b_in,c_in,a_out,b_out,c_out);
    input wire [7:0] a_in;
    input wire [7:0] b_in;
    input wire [7:0] c_in;
    output reg [7:0] a_out;
    output reg [7:0] b_out;
    output reg [7:0] c_out;
    always @(*) begin
        a_out = b_in; 
        b_out = c_in; 
        c_out = a_in; 
    end
endmodule

~~~

## OUTPUT:

![image](https://github.com/user-attachments/assets/ab43271c-80ef-4cc0-835b-5607b0dd67c6)

![image](https://github.com/user-attachments/assets/02f65b03-1e29-4744-aa48-94d5ab022ce3)

![image](https://github.com/user-attachments/assets/09e78fe5-1af5-475a-9333-3c34481625ac)


## TESTBENCH FOR SWAPPING THREE NUMBERS:

~~~


`timescale 1ns / 1ps

module swap_three_numbers_tb;

    reg [7:0] a;
    reg [7:0] b;
    reg [7:0] c;
    wire [7:0] a_out;
    wire [7:0] b_out;
    wire [7:0] c_out;
    swap_three_numbers uut (
        .a_in(a),
        .b_in(b),
        .c_in(c),
        .a_out(a_out),
        .b_out(b_out),
        .c_out(c_out)
    );
    initial begin
        a = 8'd10; 
        b = 8'd20; 
        c = 8'd30; 
        #10;
        $display("Before Swap: a = %d, b = %d, c = %d", a, b, c);
        #10;
        $display("After Swap: a = %d, b = %d, c = %d", a_out, b_out, c_out);
        #10 $stop;
        end
        endmodule

~~~

## OUTPUT:

![Screenshot 2024-10-05 170324](https://github.com/user-attachments/assets/e20bbcf9-98a4-4652-8d30-df96369f0e64)



## CONCLUSION:

In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
