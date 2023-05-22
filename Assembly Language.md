Why Assembly Langugae?
- Hardware Manipulation
- Access to specialized processor instructions
- To address critical performance issues
- Device Drivers
- Low-level embedded systems
- Real time systems

# Imp Points
- Structure is way in which components relate to each other
- ALU performs the computer's data processing functions
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

- ADD
- SUB
- MPY
- DIV
- LOAD
- STOR

- Ax -> Accumulation Register
- Bx -> Base Register 
- Cx -> Counter Register
- Dx ->  Destination/ Data Register
* IP  -> Instruction Pointer
* SP -> Stack Pointer
* BS -> Base Pointer
* SI -> Source Index
* DI -> Destination Index

* There is possiblity that there will be garbage value in registers.
* EAX is known as extended register as it is 32 bit but normally its size is 16 bit.
  
* CS -> code
* SS -> Stack
* DS -> Data
* ES -> Extended

  
* DB -> Declare byte
* DW -> Declare word

* Sometimes we need to remeber the physible intial address.
* Segment Address and Logic address should be same.
* All the arrays we declare in our assembly code will be visible in the var portion of the emulate window.

### Flags
6 status flags 3 control flags
* ZF -> Zero Flag `Either Equal or Not`
* CF -> Carry Flag 
* PF -> Parity Flag
* AX -> Auxiliary Flag
* SF -> Sign Flag
* OF -> Overflow Flag
* TF -> Trap Flag
* IF -> Interupt Flag
* DF -> Direction Flag

## Carry Flag:
The Carry Flag is set to 1 when there is a carry out from MSB on addition or there is a borrow into the MSB on subtraction. Also affected by shift and rotate instructions.

## Parity Flag:
If low byte of a result has even number of one bits then parity flag is 1 in case of odd number of one bits parity flag is 0.

## Auxiliary Flag:
The Auxiliary Carry Flag is set to 1 if there is a carry out from bit 3 on addition, or a borrow into bit 3 on subtraction.

## Zero Flag:
Zero Flag is set when the result is zero.

## Sign Flag:
Sign Flag is one when MSB is 1. It means the result is one.

## Overflow Flag:
Overflow Flag is one if signed overflow occur, otherwise it is 0.



### DataTypes:

1. `DB` -> 1B
2. `DW` -> 2B
3. `DD` -> 4B
4. `DQ` -> 8B
5. `DT` -> 10B



* CARRY
* ZERO
* SIGN
* OVERFLOW

Signed overflow -> overflow flag
Unsigned overflow -> carry flag 


If machine read most significant bit first then this is known as big endian and if it read the least significant bit first then it is known as little endian.
When little endian reads the data from memory and stores it in register it puts the least significant bit in suppose AH and most significant bit in AL.

For loop in assembly works by moving the number of iterations in CX and LOOP keyword will be used to iterate number of times on a Label. The number of iterations is from the CX register.

# Conversions:
1. Hexa To Decimal: Multiply each digit from right with 16 and corresponding power and add
2. Binary To Decimal: Multiply each digit from right with 2 and corresponding power and add
3. Binary To Octal: Divide Binary number into pairs of three digits and multiply by 2 and corresponding power of 2.
4. Octal To Binary: Convert every digit of octal into its binary form and then combine all binaries
5. Binary To Hexa: Divide Binary Into Group of 4 and multiply by 2 and corresponding power of 2
6. Hexa To Binary: Convert each hexa digit to a 4 digit binary number and cominer all binaries

# Signed And Unsigned:
- Unsigned Represent magnitude so always positive while signed values are appropriate to represent negative values also.
- A signed Integer can be positive or negative. The most significant bit is reserverd for sign.
- 1 as MSB means negative and 0 and MSB means positive.
- 1's Complement is obtained by replacing 0 by 1 and vice versa.
- Negative Integers in Computer are stored by 2's complement.
- Adding 1 to 1's complement gives us 2's Complement.
- If MSB is one first take 2's complement and then convert to decimal.
- In HexaDecimal 0-7 represent positive while 8-F represent negative. (subtract 65536 from answer if MSB is 8-F)

# Memory and Address:
- A memory segment is a block of 2^16 or 64k consecutive memory address.
- Number of bit in an address depends on the processor.
- Number of bits in an address represents memory that a processor can access.
- Size of Data bus is equal to width of memory
- Each segement has a number and memory is specified by an offset.
- Physical memory is divided into several block and one block is known as segment
- 8000:0000 8000 is the segment while 0000 is offset.
- Logical address = Segment : offset
- Physical address = Segment * 10 + offset

# Type and Variable Declaration:
