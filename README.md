<details>
<summary>Lab 1 (16/07/24)</summary>
<br>

## ASIC Lab 1 - TASK 1: Compile a C program of sum from 1 to n natural numbers using gcc compiler. ##

Step 1: Create a C file named sum1ton.c using leafpad editor.

Step 2: Now write a C program for sum from 1 to n natural numbers and save it,here i kept n=50.

Step 3 : Use gcc compiler to compile the program & run it using ./a.out to observe the output.

![Task1](https://github.com/user-attachments/assets/37aa36d8-14b2-40d6-b801-4d060e5a2c57)

## TASK 2: Compile the same program using riscv compiler. ##

Step 1: Open the code & run it using -O1.

![Task2](https://github.com/user-attachments/assets/6d5c380a-adaf-4ce5-987c-c2fb83a24970)

Step 2: Check for number of instructions in main function.
![Task2(2)](https://github.com/user-attachments/assets/bbeb57b0-08f1-406b-84f0-eb503ebc1603)
Now we can calculate the number of instructions by subtracting the address of first instruction of main section from address of the first instruction of the next section and divide the result by 4 since each instruction requires 4 memory locations.

No. of instructions = (101bc - 10184)/4 = 56/4 = 14 instructions

Step 3: Now compile using -Ofast:
![Task2(3)](https://github.com/user-attachments/assets/5b7b5781-51a7-45e1-8e64-29f51b6f34fc)

No. of instructions = (100dc - 100b0)/4 = 44/4 = 11 instructions

</details>

<details>
<summary>Lab 2 (19/07/24)</summary>
<br>
  
## ASIC Lab 2 - Task : Verify the instructions in riscv compiler for sum1ton.c code 
  
**Step 1:** Verify the output of the C program first using gcc compiler and then using spike simulator for riscv. Output must be same in both cases.

![image](https://github.com/user-attachments/assets/88ef0353-aec4-44af-91b6-c6edc24f3026)


**Step 2:** Open the spike debugger and run the program counter until the first address of the main function.

![Lab2(2)](https://github.com/user-attachments/assets/782450ca-266d-452f-a554-76b290a292a2)


**Step 3:** Read the initial contents of the register a0 and then press enter to run the instruction.

**Step 4:** Verify that the instruction is executed properly.

**Step 5:** Now read the initial contents of sp register & run the next instruction.

![image](https://github.com/user-attachments/assets/27066f46-fdb1-4fee-b79f-72900340f564)

**Step 6:** Using calculator ensure that the difference between initial and final contents of the sp register should be as per the intruction set.

![Lab2(3)](https://github.com/user-attachments/assets/6cc649f3-a33d-46b1-877e-97c5eee4d17f)
</details>

<details>
<summary>Lab 3 (22/07/24)</summary>
<br>
  
## ASIC Lab 3: 
  
## Task 1: "Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions. 

| Instruction       | Type | Hexadecimal | 32-bit Representation             | Description                                       |
|-------------------|------|-------------|-----------------------------------|---------------------------------------------------|
| ADD r6, r7, r8    | R    | 0x00C38333  | 0000000 01000 00111 000 00110 0110011 | Adds contents of r7 and r8, stores in r6          |
| SUB r8, r6, r7    | R    | 0x40E30333  | 0100000 00111 00110 000 01000 0110011 | Subtracts contents of r7 from r6, stores in r8    |
| AND r7, r6, r8    | R    | 0x00C37333  | 0000000 01000 00110 111 00111 0110011 | Bitwise AND of r6 and r8, stores in r7            |
| OR r8, r7, r5     | R    | 0x00A3A333  | 0000000 00101 00111 110 01000 0110011 | Bitwise OR of r7 and r5, stores in r8             |
| XOR r8, r6, r4    | R    | 0x00A32333  | 0000000 00100 00110 100 01000 0110011 | Bitwise XOR of r6 and r4, stores in r8            |
| SLT r10, r2, r4   | R    | 0x00A10333  | 0000000 00100 00010 010 01010 0110011 | Sets r10 to 1 if r2 is less than r4, else 0       |
| ADDI r12, r3, 5   | I    | 0x00518193  | 000000000101 00011 000 01100 0010011  | Adds immediate 5 to r3, stores in r12             |
| SW r3, r1, 4      | S    | 0x00418223  | 0000000 00100 00011 010 00001 0100011 | Stores word in r3 at memory address r1 + 4        |
| SRL r16, r11, r2  | R    | 0x0025B393  | 0000000 00010 01011 101 10000 0110011 | Logical right shift of r11 by r2 bits, stores in r16 |
| BNE r0, r1, 20    | B    | 0x00A0B0E3  | 0000000 01010 00001 001 00000 1100011 | Branches to PC+20 if r0 is not equal to r1        |
| BEQ r0, r0, 15    | B    | 0x00F08063  | 0000000 01111 00000 000 00000 1100011 | Branches to PC+15 if r0 is equal to r0            |
| LW r13, r11, 2    | I    | 0x0025A293  | 000000000010 01011 010 01101 0000011  | Loads word from memory address r11 + 2 into r13   |
| SLL r15, r11, r2  | R    | 0x0025D193  | 0000000 00010 01011 001 01111 0110011 | Logical left shift of r11 by r2 bits, stores in r15 |


## Task 2 : By making use of RISCV Core: Verilog Netlist and Testbench, perform an experiment of Functional Simulation and observe the waveforms  ##

Use following instructions in the terminal for simulation:
![image](https://github.com/user-attachments/assets/7ee8f475-a70e-4171-ab2d-fdc4d819fb90)

Given hardcoded instructions:

![image](https://github.com/user-attachments/assets/291ef3d2-91eb-405f-933f-bda2d8b451ca)


There are some differences between RISCV ISA and Hardcoded ISA.So for the above Instructions the difference between RISCV ISA and Hardcoded ISA is:
| Operation           | Standard RISC-V ISA | Standard RISC-V ISA (Binary)               | Hardcoded ISA     | Hardcoded ISA (Binary)                  |
|---------------------|---------------------|--------------------------------------------|-------------------|-----------------------------------------|
| ADD R6, R2, R1      | 32'h00110333        | 000000000001 00010 000 00110 0110011       | 32'h02208300      | 000000100010 00000 100 00000 01100000  |
| SUB R7, R1, R2      | 32'h402083b3        | 010000000010 00000 000 00111 0110011       | 32'h02209380      | 000000100010 01000 100 10000 01100000  |
| AND R8, R1, R3      | 32'h0030f433        | 000000000011 00000 111 01000 0110011       | 32'h0230a400      | 000000100011 01000 101 00100 01100000  |
| OR R9, R2, R5       | 32'h005164b3        | 000000000101 00010 110 01001 0110011       | 32'h02513480      | 000000100101 00010 110 10100 01100000  |
| XOR R10, R1, R4     | 32'h0040c533        | 000000000100 00000 100 01010 0110011       | 32'h0240c500      | 000000100100 00000 100 11000 01100000  |
| SLT R1, R2, R4      | 32'h0045a0b3        | 000000000100 00010 010 00001 0110011       | 32'h02415580      | 000000100100 00010 101 01010 01100000  |
| ADDI R12, R4, 5     | 32'h004120b3        | 000000000101 00010 010 01100 0010011       | 32'h00520600      | 000000100100 00010 010 00010 01100000  |
| BEQ R0, R0, 15      | 32'h00000f63        | 000000000000 00000 000 00000 1100011       | 32'h00f00002      | 000000000000 00000 000 00000 11000000  |
| SW R3, R1, 2        | 32'h0030a123        | 000000000011 00000 010 00001 0100011       | 32'h00209181      | 000000100010 00000 010 00001 01100000  |
| LW R13, R1, 2       | 32'h0020a683        | 000000000010 00000 010 01101 0000011       | 32'h00208681      | 000000100010 00000 010 01100 01100000  |
| SRL R16, R14, R2    | 32'h0030a123        | 000000000011 00000 010 00001 0100011       | 32'h00271803      | 000000100010 00000 011 00110 01100000  |
| SLL R15, R1, R2     | 32'h002097b3        | 000000000010 00000 111 01111 0110011       | 32'h00208783      | 000000100010 00000 111 01111 01100000  |

``` Instruction 1: ADD R6,R2,R1 ```
![image](https://github.com/user-attachments/assets/c6ef8348-72dc-462f-8f08-d9043875bed5)

``` Instruction 2: SUB R7, R1, R2 ```
![image](https://github.com/user-attachments/assets/87109f12-8144-4675-b669-de3f78c9a71a)

``` Instruction 3: AND R8, R1, R3 ```
![image](https://github.com/user-attachments/assets/1a6afd06-3680-4a07-9338-a555472fb04e)

``` Instruction 4: OR R9, R2, R5 ```
![image](https://github.com/user-attachments/assets/faf38e74-2921-40be-8beb-0cecdd79bea0)

``` Instruction 5: XOR R10, R1, R4 ```
![image](https://github.com/user-attachments/assets/b8f85e68-83a5-417c-8a70-7df205d081f4)

``` Instruction 6: SLT R1, R2, R4 ```
![image](https://github.com/user-attachments/assets/a66c57d4-c6f5-4c2a-aa42-e0b04ebaa4a2)

``` Instruction 7: ADDI R12, R4, 5 ```
![image](https://github.com/user-attachments/assets/d6652985-275d-484f-8ea2-5971b5032dd7)

``` Instruction 8: BEQ R0,R0,15 ```
![image](https://github.com/user-attachments/assets/e71570f9-5983-43d7-b393-24ce6e1ad25d)
</details>

<details>
<summary>Lab 4 (13/08/24)</summary>
<br>
  
## ASIC Lab 4: ##
## Task: Compile a C application with GCC and RISC-V GCC ##
### Application : 4-to-2 priority encoder ###
**Description :** Simulates a priority encoder that encodes the highest-priority active input.In a 4-to-2 priority encoder, there are 4 input lines and 2 output lines. The priority is assigned such that if multiple inputs are active, the encoder will output the binary code corresponding to the highest-priority active input. 

## Step 1: C Program ##
```c
#include <stdio.h>

// Function to simulate a 4-to-2 priority encoder
void priorityEncoder(int inputs[4], int *out1, int *out0) {
    // Check for the highest priority active input
    if (inputs[3] == 1) {
        *out1 = 1;
        *out0 = 1;
    } else if (inputs[2] == 1) {
        *out1 = 1;
        *out0 = 0;
    } else if (inputs[1] == 1) {
        *out1 = 0;
        *out0 = 1;
    } else if (inputs[0] == 1) {
        *out1 = 0;
        *out0 = 0;
    } else {
        *out1 = -1; // Invalid output (no active input)
        *out0 = -1;
    }
}

int main() {
    int inputs[4];
    int out1, out0;

    // Get input values from the user
    printf("Enter the 4 inputs (0 or 1) for the priority encoder:\n");
    for (int i = 0; i < 4; i++) {
        printf("Input %d: ", i);
        scanf("%d", &inputs[i]);
        if (inputs[i] != 0 && inputs[i] != 1) {
            printf("Invalid input. Only 0 or 1 are allowed.\n");
            return 1;
        }
    }

    // Simulate the priority encoder
    priorityEncoder(inputs, &out1, &out0);

    // Display the results
    if (out1 != -1 && out0 != -1) {
        printf("Priority Encoder Output: %d%d\n", out1, out0);
    } else {
        printf("No active input.\n");
    }

    return 0;
}
```

## Step 2: Compile the program using gcc compiler ##
![image](https://github.com/user-attachments/assets/cd6e8496-a398-44e2-9514-449e65f39d37)

## Step 3: Compile the program using risc-v compiler ##
![image](https://github.com/user-attachments/assets/a1dcd445-5961-4027-8d6a-ebf1d3a7a48b)

**Output result :** Priority Encoder Output: 10 (Because Input 2 has the highest priority and is active)

**Observation:** Output matches for both gcc and risc-v compiler.
</details>

<details>
<summary>Lab 5 (15/08/24)</summary>
<br>

<details>
<summary>Day 3:Digital Logic with TL Verilog & Makerchip:</summary>
<br>

**TL Verilog:** Transaction Level Verilog is a higher-level abstraction of Verilog that allows designers to write hardware descriptions with fewer lines of code. It's used to define hardware designs at a more abstract level than traditional Verilog, making the design and simulation process more efficient.

**Makerchip:** The Makerchip platform is an online integrated development environment (IDE) designed for developing, simulating, and verifying digital hardware designs, particularly in the context of RISC-V processors and open-source hardware.

# Combinational Circuit Implementations: 

## 1.Inverter:
Implementation of a simple inverter using TL Verilog:
![Inverter](https://github.com/user-attachments/assets/7ba81cf1-b0f5-46f8-aa63-af67193868e6)

## 2.NOR Gate:
Implementation of a NOR Gate using TL Verilog:
![NOR](https://github.com/user-attachments/assets/77939606-86bc-430a-9d79-168ab10a26db)

## 3.MUX 2to1 using 8 bit vectors:
Implementation of a 2*1 MUX using TL Verilog:
![MUX 2to1](https://github.com/user-attachments/assets/fda1f0f3-3ecb-4d64-a455-3ebbf7e044cb)

## 4.Combinational Calculator:
The combinational calculator is implemented using a 4*1 MUX.The calculator is implemented to perform basic operations like addition, subtraction, multiplication & division. 

TL Verilog code & waveform for the combinational calculator:
```
\m5_TLV_version 1d: tl-x.org
\m5

\SV
    m5_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $reset = *reset;
   $clk_nik = *clk;
   // $op[1:0] = *cnt[1:0];
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = $rand2[3:0];
   
   $add[31:0] =  $val1[31:0] +  $val2[31:0];
   $min[31:0] =  $val1[31:0] -  $val2[31:0];
   $mul[31:0] =  $val1[31:0] *  $val2[31:0];
   $div[31:0] =  $val1[31:0] /  $val2[31:0];
   
   $out[31:0] = $sel[1] ? ($sel[0] ? $div[31:0] : $mul[31:0]) : ($sel[0] ? $min[31:0] : $add[31:0]);
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule
```

![Comb  Calc](https://github.com/user-attachments/assets/7a0d7fcc-0a7b-47d7-bf2d-e507036c714f)

# Sequential Circuit Implementations:

## 1.Fibonacci Seq:
The Fibonacci sequence is a series of numbers where each number (after the first two) is the sum of the two preceding ones. The sequence typically starts with 0 and 1, and then each subsequent number is the sum of the previous two.

![Fibonacci](https://github.com/user-attachments/assets/a7019b56-45b7-4a0a-bf20-fbe269bfd6dd)

## 2.Sequential Calculator:
A sequential calculator is a type of calculator or computational process that performs operations in a step-by-step manner, where each operation is dependent on the previous one. This means that the result of one calculation becomes the input for the next. 

Sequential Calculator can be implemented using a 4*1 MUX , a flip flop to store the current $out[31:0] data. A reset signal is added such that the calculator gives an output of 32'b0 whenever the reset is set to high.

TL Verilog code & waveform:
```
\m5_TLV_version 1d: tl-x.org
\m5

\SV
    m5_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $reset = *reset;
   $clk_nik = *clk;
   // $op[1:0] = *cnt[1:0];
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = $rand2[3:0];
   $val1[31:0] = >>1$out[31:0];
   
   $add[31:0] =  $val1[31:0] +  $val2[31:0];
   $min[31:0] =  $val1[31:0] -  $val2[31:0];
   $mul[31:0] =  $val1[31:0] *  $val2[31:0];
   $div[31:0] =  $val1[31:0] /  $val2[31:0];
   
   $out[31:0] = $reset ? 32'b0 : ($sel[1] ? ($sel[0] ? $div[31:0] : $mul[31:0]) : ($sel[0] ? $min[31:0] : $add[31:0]));
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule
```

![image](https://github.com/user-attachments/assets/64f42bf0-6af7-43c7-869a-33c4650d7797)

# Pipelined Logic:
Pipelined logic refers to a design technique used in digital circuits, especially in microprocessors and other hardware components, to improve performance by processing multiple instructions or data simultaneously in different stages.In a pipelined circuit, the process is divided into several stages. Each stage performs a specific part of the overall task.

## Cycle Calculator:

![image](https://github.com/user-attachments/assets/06ad6661-ba79-4fd9-a7bb-37148caa5d74)

TL Verilog code & waveform:
```
 $reset = *reset;
 $clk_kar = *clk;
   
   |calc
      @1
         $val1[31:0] = $rand1[3:0];
         $val2[31:0] = >>1$out;

         $sum[31:0] = $val1 + $val2;
         $diff[31:0] = $val1 - $val2;
         $prod[31:0] = $val1 * $val2;
         $quot[31:0] = $val1 / $val2;

         $cnt[31:0] = $reset ? 0 : >>1$cnt + 1;
      
      @2
         $out[31:0] = $reset ? 0 : ($op[1] ? ($op[0] ? $quot[31:0] : $prod[31:0])
                        : ($op[0] ? $diff[31:0] : $sum[31:0]));
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule
```

![image](https://github.com/user-attachments/assets/df869356-82c0-4f32-af70-123644a37639)

# Validity:
In TL-Verilog, "validity" is a key concept used to manage the flow of data through a pipeline and to handle control logic. TL-Verilog introduces a more intuitive way of dealing with data validity compared to traditional Verilog, particularly in the context of pipeline stages. 
```
(* pipeline *)
always_comb begin
    if (stage_1_valid) begin
        stage_2_data <= stage_1_data + 1;
        stage_2_valid <= 1;
    end else begin
        stage_2_valid <= 0;
    end
end
```
## Cycle Calcultor with validity:
```
|calc
      @0
         $reset = *reset;
         $clk_nik = *clk;
         
      @1
         $val1 [31:0] = >>2$out [31:0];
         $val2 [31:0] = $rand2[3:0];
         
         $valid = $reset ? 1'b0 : >>1$valid + 1'b1 ;
         $valid_or_reset = $valid || $reset;
         
      ?$valid_or_reset
         @1   
            $sum [31:0] = $val1 + $val2;
            $diff[31:0] = $val1 - $val2;
            $prod[31:0] = $val1 * $val2;
            $quot[31:0] = $val1 / $val2;
            
         @2   
            $out [31:0] = $reset ? 32'b0 :
                          ($op[1:0] == 2'b00) ? $sum :
                          ($op[1:0] == 2'b01) ? $diff :
                          ($op[1:0] == 2'b10) ? $prod :
                                                $quot ;
```
 ![image](https://github.com/user-attachments/assets/52f6eb3b-eb1c-4aaa-8e5e-04c6fdf38e6b)
</details>

<details>
<summary>Day 4:Basic RISC-V CPU microarchitecture:</summary>
<br>
  
RISC-V (pronounced "risk-five") is an open-source instruction set architecture (ISA) based on the principles of reduced instruction set computing (RISC). It has gained popularity due to its flexibility, scalability, and openness, allowing anyone to design their own processors using the RISC-V ISA.
A simple RISC-V microarchitecture typically involves a few fundamental components that interact to execute instructions. 

These components include:

1. Instruction Fetch
2. Instruction Decode
3. Execute
4. Memory Access
5. Write Back

## RISC-V Block Diagram:

![image](https://github.com/user-attachments/assets/e4590d24-1757-4e04-9c67-92ca6c2b10f6)

## Here we will perform fetch, decode and execute operations for a program for sum of numbers 1 to 9:

## Instruction Fetch:
Instruction fetch in a RISC-V microarchitecture is the first step in the instruction execution cycle. It involves retrieving the next instruction to be executed from memory, based on the address stored in the Program Counter (PC).

TL Verilog code & makerchip simulation for instruction fetch:
```
|cpu
      @0
         $reset = *reset;
         $clk_nik = *clk;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0];
```
![image](https://github.com/user-attachments/assets/395b3f6f-9f26-4b14-9313-d4ced519bca4)

## Instruction Decode:
Instruction decode in a RISC-V microarchitecture is the stage where the fetched instruction is interpreted to determine what action the processor should take. This involves extracting the operation code (opcode), identifying the operands, and generating the necessary control signals to drive the subsequent execution stages.

TL Verilog code & makerchip simulation for instruction decode:
```
   |cpu
      @0
         $reset = *reset;
         $clk_nik = *clk;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$rs2_valid
            $funct7[6:0] = $instr[31:25];
            
         $dec_bits[10:0] = {$funct[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;
```
![image](https://github.com/user-attachments/assets/374a1abb-176d-4b82-8719-92aba7af1394)

## Register File Read:
The register file read in a RISC-V microarchitecture is a critical step in the instruction decode stage, where the processor retrieves the values of the source registers required for executing an instruction. The register file is a small, fast memory structure that holds the values of the processor's general-purpose registers.

TL Verilog code & makerchip simulation for register file read:
```
$rf_rd_en1 = !$rs1_valid;
         $rd_rd_en2 = !$rs2_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_index2[4:0] = $rs2;
         $rf_rd_data1[31:0] = $src1_value[31:0]; 
         $rf_rd_data2[31:0] = $src2_value[31:0];
```
![image](https://github.com/user-attachments/assets/aea3379f-fbdc-4cb5-87b4-2f12cb315930)

## Register File Write:
The register file write in a RISC-V microarchitecture is the final step of the instruction execution cycle where the result of an operation is stored back into one of the general-purpose registers. This process typically occurs during the Write Back (WB) stage of the pipeline.

TL Verilog code & makerchip simulation for register file write:
```
$result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx;
         
         $rf_wr_en = ($rd_valid || $rd !== 5'b0);  
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;
```
![image](https://github.com/user-attachments/assets/2723c059-1316-49fc-be83-82bd05451319)

</details>

<details>
<summary>Day 5:Complete Pipelined RISC-V CPU microarchitecture:</summary>
<br>

A complete pipelined RISC-V CPU microarchitecture is designed to improve instruction throughput by overlapping the execution of multiple instructions. The pipeline is divided into stages, with each stage handling a different part of the instruction execution process.

Overview of the Five-Stage Pipeline:
1. Instruction Fetch (IF)
Purpose: The CPU fetches the next instruction from memory based on the Program Counter (PC).

2. Instruction Decode (ID)
Purpose: The fetched instruction is decoded to determine the operation, source operands are read, and control signals are generated.

3. Execute (EX)
Purpose: The actual computation is performed here, such as arithmetic operations, logical operations, and address calculations for memory operations.

4. Memory Access (MEM)
Purpose: This stage handles memory operations such as loads and stores.

5. Write Back (WB)
Purpose: The final result of the instruction is written back to the register file.

## Code:

```
\m4_TLV_version 1d: tl-x.org
\SV
   // Template code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   m4_asm(SW, r0, r10, 10000)           // Store r10 result in dmem
   m4_asm(LW, r17, r0, 10000)           // Load contents of dmem to r17
   m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $clk_nik = *clk;
         
         //PC fetch - branch, jumps and loads introduce 2 cycle bubbles in this pipeline
         $pc[31:0] = >>1$reset ? '0 : (>>3$valid_taken_br ? >>3$br_tgt_pc :
                                       >>3$valid_load     ? >>3$inc_pc[31:0] :
                                       >>3$jal_valid      ? >>3$br_tgt_pc :
                                       >>3$jalr_valid     ? >>3$jalr_tgt_pc :
                                                     (>>1$inc_pc[31:0]));
         // Access instruction memory using PC
         $imem_rd_en = ~ $reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         
         
      @1
         //Getting instruction from IMem
         $instr[31:0] = $imem_rd_data[31:0];
         
         //Increment PC
         $inc_pc[31:0] = $pc[31:0] + 32'h4;
         
         //Decoding I,R,S,U,B,J type of instructions based on opcode [6:0]
         //Only [6:2] is used here because this implementation is for RV64I which does not use [1:0]
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] == 5'b11001;
         
         $is_r_instr = $instr[6:2] == 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] == 5'b10100;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_b_instr = $instr[6:2] == 5'b11000;
         
         $is_j_instr = $instr[6:2] == 5'b11011;
         
         //Immediate value decode
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}} , $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}} , $instr[30:25] , $instr[11:8] , $instr[7]} :
                      $is_b_instr ? { {20{$instr[31]}} , $instr[7] , $instr[30:25] , $instr[11:8] , 1'b0} :
                      $is_u_instr ? { $instr[31] , $instr[30:12] , { 12{1'b0}} } :
                      $is_j_instr ? { {12{$instr[31]}} , $instr[19:12] , $instr[20] , $instr[30:21] , 1'b0} :
                      >>1$imm[31:0];
         
         //Generate valid signals for each instruction fields
         $rs1_or_funct3_valid    = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         $rs2_valid              = $is_r_instr || $is_s_instr || $is_b_instr;
         $rd_valid               = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         $funct7_valid           = $is_r_instr;
         
         //Decode other fields of instruction - source and destination registers, funct, opcode
         ?$rs1_or_funct3_valid
            $rs1[4:0]    = $instr[19:15];
            $funct3[2:0] = $instr[14:12];
         
         ?$rs2_valid
            $rs2[4:0]    = $instr[24:20];
         
         ?$rd_valid
            $rd[4:0]     = $instr[11:7];
         
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
         
         $opcode[6:0] = $instr[6:0];
         
         //Decode instruction in subset of base instruction set based on RISC-V 32I
         $dec_bits[10:0] = {$funct7[5],$funct3,$opcode};
         
         //Branch instructions
         $is_beq   = $dec_bits ==? 11'bx_000_1100011;
         $is_bne   = $dec_bits ==? 11'bx_001_1100011;
         $is_blt   = $dec_bits ==? 11'bx_100_1100011;
         $is_bge   = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu  = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu  = $dec_bits ==? 11'bx_111_1100011;
         
         //Jump instructions
         $is_auipc = $dec_bits ==? 11'bx_xxx_0010111;
         $is_jal   = $dec_bits ==? 11'bx_xxx_1101111;
         $is_jalr  = $dec_bits ==? 11'bx_000_1100111;
         
         //Arithmetic instructions
         $is_addi  = $dec_bits ==? 11'bx_000_0010011;
         $is_add   = $dec_bits ==  11'b0_000_0110011;
         $is_lui   = $dec_bits ==? 11'bx_xxx_0110111;
         $is_slti  = $dec_bits ==? 11'bx_010_0010011;
         $is_sltiu = $dec_bits ==? 11'bx_011_0010011;
         $is_xori  = $dec_bits ==? 11'bx_100_0010011;
         $is_ori   = $dec_bits ==? 11'bx_110_0010011;
         $is_andi  = $dec_bits ==? 11'bx_111_0010011;
         $is_slli  = $dec_bits ==? 11'b0_001_0010011;
         $is_srli  = $dec_bits ==? 11'b0_101_0010011;
         $is_srai  = $dec_bits ==? 11'b1_101_0010011;
         $is_sub   = $dec_bits ==? 11'b1_000_0110011;
         $is_sll   = $dec_bits ==? 11'b0_001_0110011;
         $is_slt   = $dec_bits ==? 11'b0_010_0110011;
         $is_sltu  = $dec_bits ==? 11'b0_011_0110011;
         $is_xor   = $dec_bits ==? 11'b0_100_0110011;
         $is_srl   = $dec_bits ==? 11'b0_101_0110011;
         $is_sra   = $dec_bits ==? 11'b1_101_0110011;
         $is_or    = $dec_bits ==? 11'b0_110_0110011;
         $is_and   = $dec_bits ==? 11'b0_111_0110011;
         
         //Store instructions
         $is_sb    = $dec_bits ==? 11'bx_000_0100011;
         $is_sh    = $dec_bits ==? 11'bx_001_0100011;
         $is_sw    = $dec_bits ==? 11'bx_010_0100011;
         
         //Load instructions - support only 4 byte load
         $is_load  = $dec_bits ==? 11'bx_xxx_0000011;
         
         $is_jump = $is_jal || $is_jalr;
         
      @2
         //Get Source register values from reg file
         $rf_rd_en1 = $rs1_or_funct3_valid;
         $rf_rd_en2 = $rs2_valid;
         
         $rf_rd_index1[4:0] = $rs1[4:0];
         $rf_rd_index2[4:0] = $rs2[4:0];
         
         //Register file bypass logic - data forwarding from ALU to resolve RAW dependence
         $src1_value[31:0] = $rs1_bypass ? >>1$result[31:0] : $rf_rd_data1[31:0];
         $src2_value[31:0] = $rs2_bypass ? >>1$result[31:0] : $rf_rd_data2[31:0];
         
         //Branch target PC computation for branches and JAL
         $br_tgt_pc[31:0] = $imm[31:0] + $pc[31:0];
         
         //RAW dependence check for ALU data forwarding
         //If previous instruction was writing to reg file, and current instruction is reading from same register
         $rs1_bypass = >>1$rf_wr_en && (>>1$rd == $rs1);
         $rs2_bypass = >>1$rf_wr_en && (>>1$rd == $rs2);
         
      @3
         //ALU
         $result[31:0] = $is_addi  ? $src1_value +  $imm :
                         $is_add   ? $src1_value +  $src2_value :
                         $is_andi  ? $src1_value &  $imm :
                         $is_ori   ? $src1_value |  $imm :
                         $is_xori  ? $src1_value ^  $imm :
                         $is_slli  ? $src1_value << $imm[5:0]:
                         $is_srli  ? $src1_value >> $imm[5:0]:
                         $is_and   ? $src1_value &  $src2_value:
                         $is_or    ? $src1_value |  $src2_value:
                         $is_xor   ? $src1_value ^  $src2_value:
                         $is_sub   ? $src1_value -  $src2_value:
                         $is_sll   ? $src1_value << $src2_value:
                         $is_srl   ? $src1_value >> $src2_value:
                         $is_sltu  ? $sltu_rslt[31:0]:
                         $is_sltiu ? $sltiu_rslt[31:0]:
                         $is_lui   ? {$imm[31:12], 12'b0}:
                         $is_auipc ? $pc + $imm:
                         $is_jal   ? $pc + 4:
                         $is_jalr  ? $pc + 4:
                         $is_srai  ? ({ {32{$src1_value[31]}} , $src1_value} >> $imm[4:0]) :
                         $is_slt   ? (($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0, $src1_value[31]}):
                         $is_slti  ? (($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0, $src1_value[31]}) :
                         $is_sra   ? ({ {32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0]) :
                         $is_load  ? $src1_value +  $imm :
                         $is_s_instr ? $src1_value + $imm :
                                    32'bx;
         
         $sltu_rslt[31:0]  = $src1_value <  $src2_value;
         $sltiu_rslt[31:0] = $src1_value <  $imm;
         
         //Jump instruction target PC computation
         $jalr_tgt_pc[31:0] = $imm[31:0] + $src1_value[31:0]; 
         
         //Branch resolution
         $taken_br = $is_beq ? ($src1_value == $src2_value) :
                     $is_bne ? ($src1_value != $src2_value) :
                     $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])) :
                     $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])) :
                     $is_bltu ? ($src1_value < $src2_value) :
                     $is_bgeu ? ($src1_value >= $src2_value) :
                     1'b0;
         
         //Current instruction is valid if one of the previous 2 instructions were not (taken_branch or load or jump)
         $valid = ~(>>1$valid_taken_br || >>2$valid_taken_br || >>1$is_load || >>2$is_load || >>2$jump_valid || >>1$jump_valid);
         
         //Current instruction is valid & is a taken branch
         $valid_taken_br = $valid && $taken_br;
         
         //Current instruction is valid & is a load
         $valid_load = $valid && $is_load;
         
         //Current instruction is valid & is jump
         $jump_valid = $valid && $is_jump;
         $jal_valid  = $valid && $is_jal;
         $jalr_valid = $valid && $is_jalr;
         
         //Destination register update - ALU result or load result depending on instruction
         $rf_wr_en = (($rd != '0) && $rd_valid && $valid) || >>2$valid_load;
         $rf_wr_index[4:0] = $valid ? $rd[4:0] : >>2$rd[4:0];
         $rf_wr_data[31:0] = $valid ? $result[31:0] : >>2$ld_data[31:0];
         
      @4
         //Data memory access for load, store
         $dmem_addr[3:0]     =  $result[5:2];
         $dmem_wr_en         =  $valid && $is_s_instr;
         $dmem_wr_data[31:0] =  $src2_value[31:0];
         $dmem_rd_en         =  $valid_load;
         
      
         //Write back data read from load instruction to register
         $ld_data[31:0]      =  $dmem_rd_data[31:0];
         
      
      

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   //Checks if sum of numbers from 1 to 9 is obtained in reg[17] and runs 10 cycles extra after this is met
   *passed = |cpu/xreg[17]>>10$value == (1+2+3+4+5+6+7+8+9);
   //Run for 200 cycles without any checks
   //*passed = *cyc_cnt > 200;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@2, @3)  // Args: (read stage, write stage) - if equal, no register bypass is required
      m4+dmem(@4)    // Args: (read/write stage)
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```

## Waveforms:

![image](https://github.com/user-attachments/assets/b184c770-955d-430b-b71f-e11002dc8688)

Xreg[14] output waveform for sum of numbers 1 to 9:

![image](https://github.com/user-attachments/assets/ac34e25d-46fb-43fd-9525-c5a1dd6b1aa5)

## Diagram:
![image](https://github.com/user-attachments/assets/adfa82db-7013-4f3e-9b1e-fa3e425f36ba)

## Viz:
![image](https://github.com/user-attachments/assets/bbb1e686-f2a7-4933-ad0b-d35d3e89e40a)

## Summary:

This code configures a simulation for a RISC-V processor to execute a program that computes the sum of integers from 1 to 9. The assembly code initializes the necessary registers, executes a loop to perform the addition, and stores the final result. The simulation models the entire process, including instruction fetching, decoding, execution, memory operations, and result validation, providing a detailed emulation of how the processor would handle this task in a real-world scenario.

</details>
</details>

<details>
<summary>Lab 6 (22/08/24)</summary>
<br>

# Task: Converting TLV code to Verilog using Sandpiper. Use iverilog to simulate and gtkwave to view the output waveforms.

The purpose of converting TLV (Transaction-Level Verilog) code to Verilog using the SandPiper compiler is to bridge the gap between high-level design and lower-level hardware description.The SandPiper compiler translates TLV code into standard Verilog, a widely-used hardware description language (HDL) that can be synthesized into actual hardware.

**Step-by-Step Simulation Process:**

**Step 1:** Install the following packages:
```
sudo apt install make python python3 python3-pip git iverilog gtkwave

cd ~

sudo apt-get install python3-venv

python3 -m venv .venv

source ~/.venv/bin/activate

pip3 install pyyaml click sandpiper-saas
```

**Step 2:** Clone the Repository
First, clone the VSDBabySoC repository into your home directory:
```
cd ~
git clone https://github.com/manili/VSDBabySoC.git
```

**Step 3:** Replace the .tlv File
Replace the existing .tlv file in the VSDBabySoC/src/module folder with your RISC-V .tlv file that you want to convert to Verilog:
```
cp /path/to/your/riscv_file.tlv ~/VSDBabySoC/src/module/
```

**Step 4:** Navigate to the Project Directory
Change the working directory to VSDBabySoC:
```
cd VSDBabySoC
```

**Step 5:** Convert TLV to Verilog
Use the SandPiper compiler to convert the .tlv file into a Verilog (.v) file:
```
sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
```

**Step 6:** Create Pre-Synthesis Simulation File
Generate the pre_synth_sim.vcd file by running:
```
make pre_synth_sim
```

**Step 7:** Compile and Simulate the RISC-V Design
Compile and simulate the RISC-V design using the following command:
```
iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module
```

**Step 8:** Run the Simulation
Navigate to the output directory and run the simulation:
```
cd output
./pre_synth_sim.out
```

**Step 9:** View Simulation Results with GTKWave
Finally, open the simulation results (pre_synth_sim.vcd) using GTKWave:
```
gtkwave pre_synth_sim.vcd
```

**By following these steps, we will successfully convert a RISC-V .tlv file into Verilog and simulate the design using Icarus Verilog and GTKWave.**

## Comparison of Output waveforms:
**Makerchip Waveform:**
![image](https://github.com/user-attachments/assets/ac34e25d-46fb-43fd-9525-c5a1dd6b1aa5)

**GTKWave Waveform:**
![image](https://github.com/user-attachments/assets/a0ee380b-896b-42e0-b9b8-4120d61feeeb)

**Conclusion:**
The output result displaying the sum of integers from 1 to 9 is clearly visible as 02D for waveforms in both Makerchip and GTKWave simulations.

</details>

<details>
<summary>Lab 7 (29/08/24)</summary>
<br>

# Task: Integration of Peripherals for Digital-to-Analog Conversion Using DAC and PLL: 

## 1) Installation of iverilog, gtkwave, yosys and OpenSta:

**(1) Commands for installing iverilog:**

  ```
    sudo apt-get update
    sudo apt-get install iverilog
  ```

**(2) Commands for installing gtkwave:**

```
 sudo apt-get update
 sudo apt install gtkwave
```

**(3) Commands for installing Yosys:**
```
sudo apt-get update
git clone https://github.com/YosysHQ/yosys.git
cd yosys
sudo apt install make (If make is not installed please install it) 
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
make config-gcc
make 
sudo make install
```
***Screenshot of Yosys in terminal window:***

![image](https://github.com/user-attachments/assets/6db2acdb-8457-4157-b9c6-5a39e52a8da2)

**(4) Commands for installing OpenSTA:**
```
git clone https://github.com/The-OpenROAD-Project/OpenSTA.git
cd OpenSTA
mkdir build
cd build
cmake ..
make
sudo make install
```

***Screenshot of OpenSTA in terminal window:***

![image](https://github.com/user-attachments/assets/076595e8-2ee2-4eff-8dc1-cd35ac1dc771)


## 2) BabySoc Simulation :

The VSDBabySoC is a compact yet robust RISCV-based System-on-Chip (SoC) designed to integrate and test three open-source IP cores simultaneously. Its primary objective is to ensure seamless interaction among these cores and to fine-tune the analog components. The VSDBabySoC features an RVMYTH microprocessor, an 8x Phase-Locked Loop (PLL) for stable clock generation, and a 10-bit Digital-to-Analog Converter (DAC) for interfacing with other analog devices.

**Phase-Locked Loop (PLL):**

  • Purpose: Synchronizes an output signal with a reference signal in terms of frequency and phase.
  
  • Function: Continuously adjusts the output frequency to match the phase of the input signal.

  • Applications: Used in clock generation, frequency synthesis, and communication systems for stable and precise timing.

**Digital-to-Analog Converter (DAC):**

  • Purpose: Converts digital signals into corresponding analog signals.
  
  • Function: Translates binary data into a continuous voltage or current output.
  
  • Applications: Used in audio systems, signal processing, and interfacing with analog devices.

**Commands to Run the rvmyth.v File:**

```
 cd VSDBabySoc
```
 
```
iverilog -o ./pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module/
```

```
./pre_synth_sim.out
```

```
gtkwave pre_synth_sim.vcd
```

***Below is a screenshot of the simulated output waveform representing the sum of numbers from 1 to 9:***

![image](https://github.com/user-attachments/assets/a6d376cb-4ad2-43be-bf4b-48fa83a2cae0)

![image](https://github.com/user-attachments/assets/ef689c1e-9bcc-4eea-bfbc-6637ea87062c)


</details>

<details>
<summary>Lab 8 (15/10/24)</summary>
<br>
  
# Task : RTL design using Verilog with SKY130 Technology
<details>
<summary>Day-1</summary>
<br>
  
## iVerilog based Simulation flow:
 
 ![image](https://github.com/user-attachments/assets/0e2f8052-f0f8-4cfa-bab0-fc83a490afb9)

## LAB-1:
**Aim: Cloning the required files from github repository:**

**Commands:**
```
sudo -i
sudo apt-get install git
ls
cd /home
mkdir VLSI
cd VLSI
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
cd sky130RTLDesignAndSynthesisWorkshop/verilog_files
ls
```

**Screenshot of the terminal window:**

![image](https://github.com/user-attachments/assets/5ab593f9-447f-44eb-ac36-8b8a4d8a3b2b)

## LAB-2:
**Aim: Introduction to iVerilog gtkwave:**

In this lab we will implement a 2:1 multiplexer.

**Command to view Verilog code & testbench file:**
```
gvim tb_good_mux.v -o good_mux.v
```
![image](https://github.com/user-attachments/assets/d43bd7e1-60c0-4dfd-8242-647a83636344)

**Steps for implementing the waveform on gtkwave:**
```
iverilog good_mux.v tb_good_mux.v
ls
./a.out
gtkwave tb_good_mux.vcd
```

**Screenshots of terminal window & gtkwave waveform:**

![image](https://github.com/user-attachments/assets/6759c7c8-41b9-4e3f-bcbc-c76a4e26c40f)

![image](https://github.com/user-attachments/assets/6e8118d7-0b71-4d48-8608-727388c04fef)

## LAB-3:
**Aim: Synthesis of 2:1 Multiplexer using Yosys and Logic Synthesis:**

## YOSYS:
A synthesizer is essential in digital design, converting RTL (Register Transfer Level) code into a gate-level netlist. This netlist gives a detailed representation of the circuit, including the logic gates and their connections, forming the groundwork for subsequent steps like placement and routing. In this particular design process, Yosys, an open-source synthesis tool for Verilog HDL, is being used. Yosys employs various optimization strategies to produce an efficient gate-level design from the RTL code.

The primary inputs and outputs are the same in both the RTL design and the synthesized netlist, allowing the same test bench to be used for both.

**Block Diagram of Yosys setup :**
![image](https://github.com/user-attachments/assets/adf3de9f-78c3-4ea8-b07d-01788b398b76)



**Block Diagram of Systhesis Verification :**
![image](https://github.com/user-attachments/assets/72e54532-7abc-43ac-b32e-6a5bde0a9014)

## Logic Synthesis:

**RTL Design:** The design is modeled using a behavioral description in Hardware Description Language (HDL) according to the given specifications.

**Synthesis:** The RTL code is transformed into a gate-level representation, where the design is mapped into logic gates and connections, producing a file called the netlist. In Verilog, a netlist is a representation of a circuit that describes how various components (such as logic gates, flip-flops, or modules) are interconnected. 

## Command steps for Yosys:

**This will invoke/start the yosys:**
```
yosys
```


**Load the sky130 standard library:**
```
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib      
```


**Read the design files:**
```
read_verilog good_mux.v
```
![image](https://github.com/user-attachments/assets/5717cbc9-0303-46b2-bcbe-41748325c4ad)


**Synthesize the top level module:**
```
synth -top good_mux
```
![image](https://github.com/user-attachments/assets/14018083-104b-4037-8327-819e73043671)


**Map to the standard library:**
```
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

![image](https://github.com/user-attachments/assets/c2d5e2d3-25e2-4df9-a8dd-0b8c2796282a)
![image](https://github.com/user-attachments/assets/f26e5b13-e93f-465c-9567-6f3dd301782c)



**To view the graphical representation of the generated logic, simply enter:**
```
show
```
![image](https://github.com/user-attachments/assets/f59ce8e8-79b0-4f26-8f85-04f6c65fd07a)


**To save the netlist, use the write_verilog command. This will generate the netlist file in the current directory:**
```
write_verilog -noattr good_mux_netlist.v
!gvim good_mux_netlist.v
```

![image](https://github.com/user-attachments/assets/ba686931-ea3d-4256-85d4-2c3aba6cd24c)
</details>

<details>
<summary>Day-2</summary>
<br>

# Timing libs, hierarchical vs flat synthesis and efficient flop coding styles:

## LAB-4:
**Introduction and Walkthrough to ' dot lib ':**
ChatGPT

The .lib file serves as a collection of standard cells, including slow cells, fast cells, and other essential components. To view the contents of a .lib file, use the following command:
```
sudo -i
cd /home/nikhil-bhusari/VLSI/sky130RTLDesignAndSynthesisWorkshop/lib
gvim sky130_fd_sc_hd__tt_025C_1v80.lib
```
![image](https://github.com/user-attachments/assets/9c4e2544-45ba-475f-bf77-3bc3572283d9)


The .lib file provides critical information about the type of process used (such as 130nm technology in this case) and the process conditions like temperature, voltage, etc. It also defines various constraints, including units for variables and the type of technology used. For example:

* technology("cmos"): Specifies the technology as CMOS.
* delay_model : "table_lookup": Defines the delay model.
* bus_naming_style : "%s[%d]": Defines the naming convention for buses.
* time_unit : "1ns": Sets the unit of time.
* voltage_unit : "1V": Sets the unit of voltage.
* leakage_power_unit : "1nW": Defines the unit for leakage power.
* current_unit : "1mA": Sets the unit of current.
* pulling_resistance_unit : "1kohm": Specifies the unit for pulling resistance.
* capacitive_load_unit(1.0000000000, "pf"): Defines the unit for capacitive load.

Additionally, the .lib file provides details about the characteristics of various cells, such as leakage power, power consumption, area, input capacitance, and delay for different input combinations.


**Considering a two input **AND** gate:**

![image](https://github.com/user-attachments/assets/e868dcd4-4a26-47d0-9b22-c4d30d62f3a3)


## LAB-5:
**Hierarchical vs flat synthesis & Various Flop Coding Styles and optimization:**

## Hierarchical Synthesis:
**Instructions:**

```
cd ~
cd /home/nikhil-bhusari/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_modules.v
```
![image](https://github.com/user-attachments/assets/8cdd238c-e0b0-406f-898e-4936be8c609e)

**To Synthesize the Design:**
```
synth -top multiple_modules
```

When we run the command synth -top multiple_modules in Yosys, hierarchical synthesis is performed. This means that the relationships between the modules are preserved, maintaining the module hierarchy throughout the synthesis process.

![image](https://github.com/user-attachments/assets/477ffdbb-53bd-4f59-88d7-8b950106a00b)

**Multiple Modules: - 2 SubModules**

Commands to generate the netlist & Create a Graphical Representation of Logic for Multiple Modules: 

```
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show multiple_modules
```
![image](https://github.com/user-attachments/assets/0c65deee-ff56-4111-a733-f5ef462ce97a)

**Commands to write the netlist and view it:**

```
write_verilog -noattr multiple_modules_hier.v
!vim multiple_modules_hier.v
```

![image](https://github.com/user-attachments/assets/33e9e7ca-cb6e-4765-9802-206a75fc31a0)

**Flattening:** To  merge all hierarchical modules in the design into a single module and generate a flat netlist, simply type the following command:
```
flatten
```
**Commands to write the netlist and view it:**

```
write_verilog -noattr multiple_modules_hier.v
!vim multiple_modules_hier.v
```

![image](https://github.com/user-attachments/assets/db7eefe9-5b81-4872-a68a-6cb3090f3760)

![image](https://github.com/user-attachments/assets/9d1ebe79-fb02-423e-9815-a45d16d1bb47)


**Graphical Representation of Logic for Multiple Modules:**
```
show 
```
![image](https://github.com/user-attachments/assets/b323f6ca-8df0-4cf1-a340-abdaeb119e86)


## D Flip-Flop Design and Simulation Using Icarus Verilog, GTKWave, and Yosys:

This project demonstrates various coding styles for D Flip-Flops, followed by simulation using Icarus Verilog and GTKWave. It also covers the synthesis of these designs with Yosys. The simulations focus on three types of D Flip-Flops:

  *  D Flip-Flop with Asynchronous Reset
  *  D Flip-Flop with Asynchronous Set
  *  D Flip-Flop with Synchronous Reset

## 1. D Flip-Flop with Asynchronous Reset:

Verilog code for the D Flip-Flop with an asynchronous reset:
```
module dff_asyncres(input clk, input async_reset, input d, output reg q);
	always@(posedge clk, posedge async_reset)
	begin
		if(async_reset)
			q <= 1'b0;
		else
			q <= d;
	end
endmodule
```

Testbench for Asynchronous Reset D Flip-Flop:
```
module tb_dff_asyncres; 
	reg clk, async_reset, d;
	wire q;
	dff_asyncres uut (.clk(clk), .async_reset(async_reset), .d(d), .q(q));

	initial begin
		$dumpfile("tb_dff_asyncres.vcd");
		$dumpvars(0, tb_dff_asyncres);
		clk = 0;
		async_reset = 1;
		d = 0;
		#3000 $finish;
	end
	
	always #10 clk = ~clk;
	always #23 d = ~d;
	always #547 async_reset = ~async_reset; 
endmodule
```

**Steps to Run the Simulation:**

1. Navigate to the directory where the Verilog files are located:
```
cd /home/username/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
```

2. Run the following commands to compile and simulate the design:
```
civerilog dff_asyncres.v tb_dff_asyncres.v
ls
```
The compiled output will be saved as a.out.

3. Execute the compiled output and open the waveform viewer:
```
./a.out
gtkwave tb_dff_asyncres.vcd
```

By following these steps,we can observe the behavior of the D Flip-Flop with an asynchronous reset in the waveform viewer:

![image](https://github.com/user-attachments/assets/d9b2afd3-a16f-4b74-9eff-a01471cfd177)


**Observation:** From the waveform, we can observe that when the asynchronous reset is activated (set high), the Q output immediately resets to zero, regardless of the clock's positive or negative edge. This demonstrates the asynchronous behavior of the reset signal.


## 1. D Flip-Flop with Asynchronous Set:

This section demonstrates the implementation of a D Flip-Flop with an asynchronous set, using Verilog. The design ensures that when the asynchronous set signal is high, the output Q is immediately set to 1, regardless of the clock signal.

Verilog Code for Asynchronous Set D Flip-Flop:
```
module dff_async_set(input clk, input async_set, input d, output reg q);
	always@(posedge clk, posedge async_set)
	begin
		if(async_set)
			q <= 1'b1;
		else
			q <= d;
	end
endmodule
```

Testbench Code:
```
module tb_dff_async_set; 
	reg clk, async_set, d;
	wire q;
	dff_async_set uut (.clk(clk), .async_set(async_set), .d(d), .q(q));

	initial begin
		$dumpfile("tb_dff_async_set.vcd");
		$dumpvars(0, tb_dff_async_set);
		// Initialize Inputs
		clk = 0;
		async_set = 1;
		d = 0;
		#3000 $finish;
	end

	always #10 clk = ~clk;
	always #23 d = ~d;
	always #547 async_set = ~async_set; 
endmodule
```


**Steps to Run the Simulation:**

1. Navigate to the directory containing the Verilog files:
```
cd /home/username/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
```

2. Compile the Verilog code and the testbench using Icarus Verilog:
```
iverilog dff_async_set.v tb_dff_async_set.v
ls
```

The output will be saved as a.out.

3. Run the compiled file and open the waveform in GTKWave:
```
./a.out
gtkwave tb_dff_async_set.vcd
```

**Result:**

After running the simulation, we will observe the behavior of the D Flip-Flop with an asynchronous set in the waveform viewer. Below is a snapshot of the commands and the resulting waveforms.

![image](https://github.com/user-attachments/assets/708c04a7-baac-40c6-8a65-81eb4cb1d236)







</details>


</details>



