# Process Concept

## Process

A program in execution

Includes:

* Text section
* Program counter
* Stack
* Data section
* Heap

## Process State

* New
* Running
* Waiting
* Ready
* Terminated

## Process Control Block \(PCB\)

#### Contains:

* Process state
* Program counter
* CPU registers
* CPU scheduling information
* Memory-management information
* Accounting information
* I/O state information

## Process VS Program

Program is a static object while process is running.

Process has running states and lifecycles.

## Process Scheduling

### Job queue

The set of all processes in the system

### Ready queue

The set of processes waiting to be executed

### Device queue

The set of processes waiting for I/O device

### Long-term scheduler

Select which processes to be in ready queue

Determine degree of multiprogramming

#### I/O bound process

Processes spending more time doing I/O

#### CPU bound process

Processes spending more time doing computation

#### Process mix

Long-term scheduler strive good mix of I/O and CPU bound processes in the ready queue

### Short-term scheduler

Select which process to be run by CPU next

### Context Switch

Happens when CPU switches from one process to another.

The system save the state of the old process and load the state of new process into CPU

## Operation on Processes

### Process Creation

Parent process create child process, forming a process tree.

Process identified by PID

What to do to create a process?

* Construct new PCB
* Set up new page table for address space
* Copy data from parent if fork\(\)
* Copy I/O state if fork\(\)

#### Create new process by copying parent process

fork\(\)

Copy the entire address space of parent to child process

Except PID, accounting info, running state

fork\(\) returns 0 to parent process, returns child's PID to parent

#### Create new process by loading in new program

Windows CreateProcess\(\)

Load a specified program into address space of child process

### Process Termination

Process execute last statement and request to be deleted by calling exit\(\)

Parent can wait\(\) for child's termination

Parent cannot exit with running children, it must wait\(\) for all children before exit\(\)

Zombie is a child which exited but its parent has not wait\(\) for it yet

Orphan is a child which's parent exit\(\) without calling wait\(\). Init will be its new parent and will periodically call wait\(\) to reclaim orphan's resources.

## Interprocess Communication \(IPC\)

### Share Memory

* Will suffer from cache coherency problem in multicore system

#### Producer-Consumer Model

Producer produces information consumed by consumer.

Can use bounded-buffer or unbounded-buffer

### Message Passing

#### Direct Communication

Message sent directly to another process

Link automatically generated and destoryed

Link associate with one pair of processes

send\(P,msg\) will send msg to process P

receive\(Q,msg\) will receive msg from process Q

Indirect Communication

Processes exchange messages via mailbox

There can be more than 2 processes sharing a mailbox

Link generated and destroyed by the process using the mailbox

Can set rules on who receive the message

#### Synchronization

Blocking Send: Sender blocks until some process receive the message

Blocking Receive: Receiver blocks until there is message available

Non-blocking Send: Sender leaves the message and continue with other operation

Non-blocking Receive: Receiver either get the message or get null

Rendezvous: Both sending and receiving are blocking

### Client-Server Communication

#### Socket

Socket is a endpoint of communication

Socket has IP and port, IP determines the host and port determines the process

Ports below 1024 are well-known

IP address 127.0.0.1 loopbacks to localhost

### Pipe

Unix's first IPC mechanism

#### Ordinary Pipe

Only allows producer-consumer model

Producer write on the write-end while consumer read on the read-end

Unidirectional

Require parent-child relationship

Also called anonymous pipe

#### Named Pipe

Bidirectional

No parent-child relationship required

Several processes can use one named pipe

In Unix mkfifo\(\) create a named pipe

Exist after involving processes exit

