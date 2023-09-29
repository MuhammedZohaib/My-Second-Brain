- OS is a software that act as an intermediary between applications and hardware resources.
- Kernel is the a computer program that is at the core of a computer's operating system and generally controls everyting on the system.
	- `Kernel Internals`: Data Structures and Algorithms that defines how to manage and use hardware.
	- `Kernel API`: It offers set of functions to ask for system services.
- All the system calls are handled by the kernal.

## Steps of an Operating System:

1. `Boot`: When system is turned on the kernal program is loaded into the memory. Interrupts are generated. It also starts the system access mechanism such as login or shell. The kernal code is the minimum boot code required for startup. It can be loaded from a disk, a network or can be loaded from a bootloader program such as grub (Grand Unified Bootloader) which shows available boot options. Once the system to boot is selected it is fully copied in the memory and harware configurations are initialized and then the kernal gets the full access of the hardware.
2. `Usage`: We develop new applications and execute applications.
3. `Shutdown`: When system is turned off saves persistent information, stop devices etc.


## Processes:
A process is the OS representation of a program during its execution. When a program is executed in a multi-programmed multi-user enviornment the OS needs to assign it some attributes. 
- Which region of the physical memory is being used?
- Which files are being accessed?
- Which user is executing it?
- What time it is started?
- How much CPU time it has consumed?

When a process is executed kernal assigns hardware resources to it. and kernal reserves and initializes a new process data structure which has a limited number of total process.
Each OS uses a name for that data structure and in general we call it PCB (Process Control Book). Each new process has a unique identifier in Linux it is known as PID (Process Identifier).


### Process States
When a process is executed we can find it wating  for data from some device or sometimes from some other process. To utilize the maximum hardware we have multiprogrammed systems, The OS only allocates CPU to those process which are using it.

#### States:
- `run`: The process is assigned CPU and is running.
- `ready`: The process is ready to run but is waiting for CPU to be allocated. 
- `blocked`: The process does not have CPU, it is blocked waiting for I/O to finish.
- `zombie`: The process has finished executing but has not been removed from the PCB data structure. 

Each process has a specific amount of time allocated by a CPU this is often reffered as quantum or time slice. each process must leave the running phase after the quantum expires

