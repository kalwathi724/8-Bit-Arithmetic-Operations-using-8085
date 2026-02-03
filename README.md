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
LDA 1000H
MOV B,A
LDA 1001H
ADD B
STA 4300H
JC STORE_CARRY
HLT
STORE_CARRY:MVI A,01H
STA 4301H
HLT
### Output:
<img width="319" height="437" alt="image" src="https://github.com/user-attachments/assets/dccb9a34-e75a-4e3a-aaa5-2eda14338890" />
<img width="315" height="440" alt="image" src="https://github.com/user-attachments/assets/c6302a0c-d105-4361-b0da-a843287ce391" />
<img width="1484" height="795" alt="image" src="https://github.com/user-attachments/assets/091f8955-b6ee-4cb0-885b-c30823525585" />


### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
LDA 1000H
MOV C,A
LDA 1001H
CMP C
JC SWAP
SWAP:
MOV B,A
MOV A,C
SUB B
STA 4300H
HLT

### Output:
<img width="305" height="441" alt="image" src="https://github.com/user-attachments/assets/61f0edb3-55f9-4362-98e8-924f9dd63fd0" />

<img width="308" height="392" alt="image" src="https://github.com/user-attachments/assets/188a5962-f64b-47b2-8384-cdd08da5ab1d" />

<img width="1434" height="635" alt="image" src="https://github.com/user-attachments/assets/5113393b-a646-442f-8a8e-788678f55438" />


### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
LDA 1000H
MOV C,A
LDA 1001H
MOV B,A
MVI A,00H
LOOP:ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
### Output:
<img width="316" height="460" alt="image" src="https://github.com/user-attachments/assets/f69b5bcf-92dc-43e8-8f94-3f383c4479e2" />
<img width="1445" height="590" alt="image" src="https://github.com/user-attachments/assets/9706f499-61bf-4e08-9253-056afb277aad" />
<img width="316" height="388" alt="image" src="https://github.com/user-attachments/assets/e659f91c-4a82-4fc4-bc2f-b11ebf6e4bc6" />

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
LDA 3200H
MOV C,A
LDA 3201H
MOV B,A
MVI A,00H
LOOP:CMP B
JC END
SUB B
INR A
JMP LOOP
END: STA 3300H
MOV A,C
STA 3301H
HLT

### Output:
<img width="314" height="472" alt="image" src="https://github.com/user-attachments/assets/ae0ed239-3918-4696-8850-84eb0a507e04" />
<img width="1441" height="756" alt="image" src="https://github.com/user-attachments/assets/cb5dc58f-9c1a-4afd-87a5-b2b83f960df4" />
<img width="311" height="451" alt="image" src="https://github.com/user-attachments/assets/b64feb15-eda8-4d3e-8901-6d99675bcaa6" />
## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

