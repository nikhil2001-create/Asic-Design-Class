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

## ASIC Lab 3: ##
## Task 1: "Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions. 

| Instruction       | Type | Hexadecimal | 32-bit Representation             |
|-------------------|------|-------------|-----------------------------------|
| ADD r6, r7, r8    | R    | 0x00C38333  | 0000000 01000 00111 000 00110 0110011 |
| SUB r8, r6, r7    | R    | 0x40E30333  | 0100000 00111 00110 000 01000 0110011 |
| AND r7, r6, r8    | R    | 0x00C37333  | 0000000 01000 00110 111 00111 0110011 |
| OR r8, r7, r5     | R    | 0x00A3A333  | 0000000 00101 00111 110 01000 0110011 |
| XOR r8, r6, r4    | R    | 0x00A32333  | 0000000 00100 00110 100 01000 0110011 |
| SLT r10, r2, r4   | R    | 0x00A10333  | 0000000 00100 00010 010 01010 0110011 |
| ADDI r12, r3, 5   | I    | 0x00518193  | 000000000101 00011 000 01100 0010011  |
| SW r3, r1, 4      | S    | 0x00418223  | 0000000 00100 00011 010 00001 0100011 |
| SRL r16, r11, r2  | R    | 0x0025B393  | 0000000 00010 01011 101 10000 0110011 |
| BNE r0, r1, 20    | B    | 0x00A0B0E3  | 0000000 01010 00001 001 00000 1100011 |
| BEQ r0, r0, 15    | B    | 0x00F08063  | 0000000 01111 00000 000 00000 1100011 |
| LW r13, r11, 2    | I    | 0x0025A293  | 000000000010 01011 010 01101 0000011  |
| SLL r15, r11, r2  | R    | 0x0025D193  | 0000000 00010 01011 001 01111 0110011 |



