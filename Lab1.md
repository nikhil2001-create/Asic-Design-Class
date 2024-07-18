## TASK 1: Compile a C program of sum from 1 to n natural numbers using gcc compiler. ##

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
