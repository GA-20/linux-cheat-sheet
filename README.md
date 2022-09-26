
## Levels and Layers in Linux

### Hardware: Level 1

The hardware is at the base, include the memory to perform computation. (CPU, RAM, disk, network, etc.)

### Kernel: Level 2

It is responsible for managing the hardware and providing an interface for the user to interact with the hardware. (system calls, process management, memory management, device drivers, etc.)

### User Process: Level 3

The running programs managed by the kernel. (graphical user interface, servers, shell, etc.)

## Hardware: Main Memory

The main memory is the place where the data and instructions are stored. An slot in the memory is called a byte. The memory is organized in a way that each byte has a unique address. The address is a number that identifies the byte.

## Kernel: System Calls

- Process: Determine the process allowed to access the memory.
- Memory: Determine the memory allowed to be accessed by the process.
- Driver: The kernel acts as interface between the hardware and the user process.

### Process Management

- Starting a process: The kernel creates a new process and allocates memory for it.
- Pausing a process: The kernel suspends the process and saves its state.
- Resuming a process: The kernel restores the process state and resumes it.
- Scheduling: The kernel decides which process to run next.
- Terminating a process: The kernel terminates the process and frees its memory.

Note: Many processes can be running simultaneously but only one process can be running at a time. 

### Memory Management

- Allocating memory: The kernel allocates memory for a process.
- Freeing memory: The kernel frees memory allocated for a process.
- Swapping: The kernel moves a process from memory to disk and vice versa.

### Device Drivers

Allowing the user process to interact with a hardware device.

### System Calls

Interaction between the user process and the kernel.

- Fork: Create a new process.
- Exec: Start a new program.
- Wait: Wait for a child process to terminate.
- Exit: Terminate a process.
- Kill: Terminate a process.
- Init: Start the init process.

### User Space




