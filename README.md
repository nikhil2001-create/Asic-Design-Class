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
## ASIC Lab 3: ##
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

**Observation:** Output matches for both gcc and risc-v compiler.
</details>






















