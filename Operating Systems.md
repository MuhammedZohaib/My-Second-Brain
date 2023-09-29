- OS is a software that act as an intermediary between applications and hardware resources.
- Kernel is the a computer program that is at the core of a computer's operating system and generally controls everything on the system.
	- `Kernel Internals`: Data Structures and Algorithms that defines how to manage and use hardware.
	- `Kernel API`: It offers set of functions to ask for system services.
- All the system calls are handled by the kernel.

## Steps of an Operating System:

1. `Boot`: When system is turned on the kernel program is loaded into the memory. Interrupts are generated. It also starts the system access mechanism such as login or shell. The kernel code is the minimum boot code required for startup. It can be loaded from a disk, a network or can be loaded from a boot loader program such as grub (Grand Unified Boot loader which shows available boot options. Once the system to boot is selected it is fully copied in the memory and hardware configurations are initialized and then the kernel gets the full access of the hardware.
2. `Usage`: We develop new applications and execute applications.
3. `Shutdown`: When system is turned off saves persistent information, stop devices etc.


## Processes:
A process is the OS representation of a program during its execution. When a program is executed in a multi-programmed multi-user environment the OS needs to assign it some attributes. 
- Which region of the physical memory is being used?
- Which files are being accessed?
- Which user is executing it?
- What time it is started?
- How much CPU time it has consumed?

When a process is executed kernel assigns hardware resources to it. and kernel reserves and initializes a new process data structure which has a limited number of total process.
Each OS uses a name for that data structure and in general we call it PCB (Process Control Book). Each new process has a unique identifier in Linux it is known as PID (Process Identifier).


### Process States
When a process is executed we can find it waiting  for data from some device or sometimes from some other process. To utilize the maximum hardware we have multi programmed systems, The OS only allocates CPU to those process which are using it.

#### States:
- `run`: The process is assigned CPU and is running.
- `ready`: The process is ready to run but is waiting for CPU to be allocated. 
- `blocked`: The process does not have CPU, it is blocked waiting for I/O to finish.
- `zombie`: The process has finished executing but has not been removed from the PCB data structure. 

Each process has a specific amount of time allocated by a CPU this is often referred as quantum or time slice. each process must leave the running phase after the quantum expires.


### Process Creation:
System calls allow to users to ask for:
- creating new processes
- changing executable files associated with a process
- ending it's execution
- waiting until a process ends
- sending events from one process to another

```c
//Linux System calls for process management
fork //process creation
exec("executable file") //changing executable file
exit // end process
wait waitpid // wait for a child process (can block) 
getpid // process id for calling process
getppid // Father's process ID for calling process
```


```c
/* Understanding the fork call:
Fork call is used to create a prcoess in the unix system, suppose we call it in a program at the point where it will be called it will create and exact duplicate of the program and execute it and all the other lines below the fork call will be now the child process of our fork call */

#include <stdlib.h>
#include <unistd.h>
#include <stdio.h>
#include <string.h>

void main(int argc,char *argv[]){

    char buffer[80];
//The for creates a new process
    fork(); 
/*The lines below the fork process will be considered as the child process
of the fork process*/
//In c language the sprint is used to store a message in the buffer
    sprintf(buffer, "I'm the process: %d\n", getpid());
//The one in the above write function is standard output in unix which is shell
    write(1,buffer,strlen(buffer));
}
```

- When the child process is created it contains zero signals initially
- The child does not inherit timers from its parents
The fork call returns a signed int which is either -1, 0 or 0<
if val == 0 --> child process
if val == -1 --> error
if val >= 0  --> parent (the val is usually the pid of the child)

### Executing other programs:


```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <string.h>

void main(){
        char buffer [80];
        sprintf(buffer, "\nI am the process in Program 2: %d\n\n", getpid());
        write(1,buffer,strlen(buffer));


        execlp("./program1","proram1", (char *) 0);
        //anything below the execlp call will not be executed
}
```





