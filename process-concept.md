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

### 



