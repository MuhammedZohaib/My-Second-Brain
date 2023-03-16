*  Always stay considerate wether you use hexadecimal or decimal. If we use hexadecimal remember to use `NUMh` at the end.
* Unsigned means always positive. Signed number means either positive or negative.
* Data types are word(2 bytes) and byte(8 bits).
* Assembler convert Assembly language to machine language while compiler convert HLL to LLL.
* Yellow line indicates the line to be run when we click on emulate.
* Four general purpose registers are `Ax` , `Bx` , `Cx` and `Dx` and each register is 16 bit. we can also use them separate like in two parts (8bits) 
  Ax -> AH , AL
  Bx -> BH, BL
  * No matter what type of number we take it is always converted to hexadecimal when it reacher cpu.
  * In emu8086 Keywords are blue and registers are red in syntax.
  * Within one instruction the size of source and destination should be same.
  * Semicolon at the start means the the code is commented.
  * A hexadecimal number must start with a digit and end with h.
  * If the data is greater than 16 bit either the data is discarded or we need to use ES.
  * We must involve a register while using two variables. Memory to memory operations are not performed.
  * Interupts (ISR = Interupt service routine) are user inputs in other words
  * 

-> Ax Accumulation Register
-> Bx Base Register 
-> Cx Counter Register
-> Dx Destination/ Data Register

* There is possiblity that there will be garbage value in registers.
* EAX is known as extended register as it is 32 bit but normally its size is 16 bit.
  
* CS -> code
* SS -> Stack
* DS -> Data
* ES -> Extended
* IP  -> Instruction Pointer
* SP -> Stack Pointer
* BS -> Base Pointer
* SI -> Source Index
* DI -> Destination Index
  
* DB -> Declare byte
* DW -> Declare word

* Sometimes we need to remeber the physible intial address.
* Segment Address and Logic address should be same.
* All the arrays we declare in our assembly code will be visible in the var portion of the emulate window.

### Flags
* ZF -> Zero Flag `Either Equal or Not`

```assembly
mov  
```

### DataTypes:

1. `DB` -> 1B
2. `DW` -> 2B
3. `DD` -> 4B
4. `DQ` -> 8B
5. `DT` -> 10B

### Assembly Template
```
org 100h
.data

.code

ret
```

```
org 100h ;standard

.data ;data segment

VAR1 DB 0x5A   ;Declaring variable
VAR2 DW 0xE76F ;Declaring variable


.code ;code segment

MOV AL, var1 ;Mov value of var1 into AL
MOV BX, var2 ;Mov value of var2 into BX

ADD AX, BX  ;ADD AX and BX
SUB AX, BX  ;SUB BX from AX
NEG AL      ;negative of AL  
XCHG AX, BX ;Swap values of AX and BX


ret
```

* CARRY
* ZERO
* SIGN
* OVERFLOW

Signed overflow -> overflow flag
Unsigned overflow -> carry flag 

