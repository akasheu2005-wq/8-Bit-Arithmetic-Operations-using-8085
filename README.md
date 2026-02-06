# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
```
CMC
LDA 4200H
MOV B, A
LDA 4201H
ADD B
STA 4300H
HLT
```

### Output:
<img width="1900" height="781" alt="image" src="https://github.com/user-attachments/assets/11b3e63d-6b63-427c-b921-30b50db91eb3" />
<img width="1879" height="747" alt="image" src="https://github.com/user-attachments/assets/c03465bf-029c-4c98-ade4-baffab2b40a2" />

ADDITION EXPLANTION:

![photo_2026-02-06_10-08-20](https://github.com/user-attachments/assets/d0236f68-f927-406b-801c-15283673cfb5)


### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
CMP C
MOV B, A
MOV A, C
SWAP:
SUB B
STA 4300H
HLT
```
### Output:
<img width="1808" height="733" alt="image" src="https://github.com/user-attachments/assets/508206c9-e89c-4ab8-95c2-cfef984f0943" />
<img width="1810" height="729" alt="image" src="https://github.com/user-attachments/assets/cd46ad0e-b63c-4b6e-8027-fd021edadec0" />

SUBTRACTION EXPLANTION:

![photo_2026-02-06_10-10-15](https://github.com/user-attachments/assets/54da02ed-101c-4563-a5c0-bf6b7747d793)


### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
MOV B, A
MVI A, 00H
LOOP: ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```

### Output:
<img width="1812" height="724" alt="image" src="https://github.com/user-attachments/assets/04243d11-ff7a-4458-8e05-8589d04a001a" />
<img width="1815" height="734" alt="image" src="https://github.com/user-attachments/assets/3a6be00d-d8d2-4f4b-b9fc-ab139fb82b6b" />

MULTIPLICTION EXPLANATION:

![photo_2026-02-06_10-12-15](https://github.com/user-attachments/assets/3d5bd00a-50ed-4ded-af2e-d1ffc62f915b)



### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
MOV B,A
MVI A,00H
LOOP: MOV A,C
CMP B
JC END
SUB B
MOV C,A
INR D
JMP LOOP
END: MOV A,D
STA 4300H
MOV A,C
STA 4301H
HLT
```

### Output:
<img width="1810" height="739" alt="image" src="https://github.com/user-attachments/assets/6b0ffe9d-8506-453f-911e-6311bd929734" />
<img width="1806" height="737" alt="image" src="https://github.com/user-attachments/assets/3c4db363-027b-412a-b84e-80dbbecad15d" />

DIVISION EXPLANATION:

![photo_2026-02-06_10-13-11](https://github.com/user-attachments/assets/7f3f74f7-20aa-4783-aaf2-82eb898d4d99)




## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

