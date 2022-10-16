## Linux Process

- Process: A running program.
- Process ID: A unique number that identifies a process.
- Parent Process: The process that started another process.
- Child Process: A process that was started by another process.
- Parent Process ID: The process ID of the parent process.
- Child Process ID: The process ID of the child process.
- Process Tree: A tree of processes where each process is a node in the tree.
- Process Group: A group of processes that are related to each other.
- Process Group ID: A unique number that identifies a process group.
- Session: A group of processes that are related to each other.
- Session ID: A unique number that identifies a session.
- Foreground Process: A process that is currently running in the foreground.
- Background Process: A process that is currently running in the background.
- Foreground Process Group: A process group that is currently running in the foreground.
- Background Process Group: A process group that is currently running in the background.
- Zombie Process: A process that has finished executing, but has not been cleaned up yet.
- Orphan Process: A process that has no parent process.
- Daemon Process: A process that runs in the background and does not have a controlling terminal.
- Kernel Thread: A thread that is managed by the kernel.
- User Thread: A thread that is managed by a user process.
- Thread: A lightweight process that shares resources with other threads.
- Thread ID: A unique number that identifies a thread.
- TSTP: A signal that stops a foreground process.

## Process Commands

### Inspect Processes

- **ps**: List processes.
  - **output anatomy**: The ps command print a table of process.
    - **PID**: The process ID.
    - **TTY**: The terminal that the process is running in.
    - **STAT**: The state of the process.
    - **TIME**: The amount of time that the process has been running.
    - **COMMAND**: The command that started the process.
  - **options**:
    - **pstree**: List processes as a tree.
    - **-A**: List all processes.
    - **-a**: List all processes except session leaders.
    - **-e**: List all processes.
    - **-f**: List processes in full format.
    - **x**: Show all ours process.
    - **ax**: Show all process in the system.
    - **aux**: Show all process in the system with full format.
    - **-u**: Show process of a specific user.
    - **u**: include more detailed information on the process.
    - **-p**: Show process of a specific process ID.
    - **-o**: Show specific columns.

### Terminate Processes

- **kill pid**: Terminate a process with the pid.
  - **options**:
    - **-l**: List all signals.
    - **-s**: Send a specific signal.
    - **-9**: Send a SIGKILL signal.
    - **-15**: Send a SIGTERM signal.
    - **-STOP**: Freeze a process.
    - **-CONT**: Unfreeze a process.

NOTE: Do not kill unknown processes, you may shoot yourself in the foot.

### Job Control

- **jobs**: List all jobs.
- **fg**: Bring a job to the foreground.
- **bg**: Send a job to the background.
- **disown**: Remove a job from the job list.

