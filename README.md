# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**

1.Open Quartus Prime and create a new project named SISO_ShiftRegister.

2.Create a new Verilog file (exp10.v), enter the given code, and add it to the project.

3.Compile the project to check for syntax errors and ensure successful compilation.

4.Open the Simulation Waveform Editor, assign clock and serial input signals, and run simulation.

5.Observe outputs q[0]–q[3] to verify that input bits shift correctly on each clock pulse.

6.Generate RTL schematic using Netlist Viewer, capture waveforms/screenshots, and record results.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: N.lakshmi pranay
RegisterNumber:25017706

*/
```
module exp10(clk, sin, q);
input clk;
input sin;
output [3:0] q;
reg [3:0] q;
always @(posedge clk)
begin
q[0] <= sin;
q[1] <= q[0];
q[2] <= q[1];
q[3] <= q[2];
end
endmodule
```

**RTL LOGIC FOR SISO Shift Register**

<img width="774" height="305" alt="image" src="https://github.com/user-attachments/assets/73121bf4-885c-43ac-861d-e7a640e325a0" />

**TIMING DIGRAMS FOR SISO Shift Register**

<img width="826" height="313" alt="image" src="https://github.com/user-attachments/assets/283d3353-64a7-4cd7-8d7b-baf201c25462" />

**RESULTS**
The input bits applied at sin were successfully shifted through q[0]–q[3] on each clock pulse. After four clock cycles, the serial input appeared correctly at the final output q[3].
