# Assembly Language Overview

## Why Assembly Language?

- Hardware Manipulation
- Access to specialized processor instructions
- Address critical performance issues
- Device Drivers
- Low-level embedded systems
- Real-time systems

## Important Points

- Structure defines how components relate to each other.
- ALU performs data processing functions.
- Always consider using hexadecimal (`NUMh`) or decimal.
- Unsigned numbers are always positive; signed numbers can be positive or negative.
- Data types: word (2 bytes), byte (8 bits).
- Assembler converts Assembly language to machine language; compiler converts HLL to LLL.
- Yellow line in emu8086 indicates the line to run on emulation.
- General-purpose registers: Ax, Bx, Cx, Dx (16-bit).
- Register parts: Ax -> AH, AL; Bx -> BH, BL.
- All numbers are converted to hexadecimal when reaching CPU.
- Keywords are blue, registers are red in emu8086 syntax.
- Source and destination size must be the same within an instruction.
- Semicolon at start indicates a comment.
- Hexadecimal number must start with digit, end with 'h'.
- Data > 16-bit may require ES.
- Registers are used when working with two variables; no memory-to-memory operations.
- Interrupts (ISR = Interrupt Service Routine) handle user inputs.

## Instructions

- ADD
- SUB
- MPY
- DIV
- LOAD
- STOR

## Registers

- Ax -> Accumulation Register
- Bx -> Base Register
- Cx -> Counter Register
- Dx -> Destination/Data Register
- IP -> Instruction Pointer
- SP -> Stack Pointer
- BS -> Base Pointer
- SI -> Source Index
- DI -> Destination Index

## Extended Registers

- EAX is a 32-bit extended register, normally 16-bit.
- CS -> Code Segment
- SS -> Stack Segment
- DS -> Data Segment
- ES -> Extended Segment

## Declarations

- DB -> Declare byte
- DW -> Declare word

## Memory and Addressing

- Physical memory divided into segments.
- Each segment has a number and memory is specified by offset.
- Logical address = Segment : Offset
- Physical address = Segment * 10 + Offset

## Flags

- ZF -> Zero Flag
- CF -> Carry Flag
- PF -> Parity Flag
- AF -> Auxiliary Flag
- SF -> Sign Flag
- OF -> Overflow Flag
- TF -> Trap Flag
- IF -> Interrupt Flag
- DF -> Direction Flag

### Flag Definitions

- Carry Flag: Set on carry/borrow from MSB on add/subtract.
- Parity Flag: Set if low byte has even/odd one bits.
- Auxiliary Flag: Set on carry/borrow from bit 3.
- Zero Flag: Set when result is zero.
- Sign Flag: Set when MSB is 1.
- Overflow Flag: Set on signed overflow.

## Data Types

1. `DB` -> 1 Byte
2. `DW` -> 2 Bytes
3. `DD` -> 4 Bytes
4. `DQ` -> 8 Bytes
5. `DT` -> 10 Bytes

## Conversions

1. Hex to Decimal: Multiply digits by 16 and add.
2. Binary to Decimal: Multiply digits by 2 and add.
3. Binary to Octal: Divide into groups of three, convert to octal.
4. Octal to Binary: Convert each digit to binary, combine.
5. Binary to Hex: Divide into groups of four, convert to hex.
6. Hex to Binary: Convert each hex digit to 4-bit binary, combine.

## Signed and Unsigned

- Unsigned: Always positive.
- Signed: Can be positive/negative, MSB reserved for sign.
- 1 as MSB: Negative; 0 as MSB: Positive.
- 1's Complement: Replace 0 with 1, vice versa.
- Negative Integers: Stored in 2's complement.
- Adding 1 to 1's complement gives 2's complement.
- For MSB = 1, take 2's complement, then convert to decimal.
- In Hexadecimal: 0-7 = positive, 8-F = negative.

## Endianness

- Big Endian: Read MSB first.
- Little Endian: Read LSB first.

## Loops

- For loop: Set iterations in CX, use LOOP on a label.

---
Note: These notes are formatted using Markdown for better readability.
