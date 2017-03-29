# Operating System Structure

## Operating System Serivces

* User Interface
* Program Execution
* I/O Operation
* File-system manipulation
* Communication
* Error Detection and Correction
* Resource Allocation
* Accounting
* Protection and Security

## User Interface

Command Line Interface

Graphical User Interface

Touchscreen Interface

## System Call

### System Call API

### System Call Parameter Passing

* Pass in register
* Pass by pointer
* Pass in stack

### System Call Types

* Process Control
* File Management
* Device Management
* Information Maintainance
* Communication
  * Inter-process communication
  * Network communication
* Protection

## System Program

Provide a convenient environment for program development and execution, or simply user interface.

## Operating System Design

Affected by choice of hardware, type of system.

User Goal: Convenient to use, easy to learn, reliable, safe, fast.

System Goal: Easy to design, implement and maintain, flexible, reliable, error-free, efficient.

Policy: What to do? What need to be done?

Mechanism: How to do?

## Operating System Implementation

Language: Assembly, C, C++, or even Python and shell script.

Language choice affects portability.

## Operating System Structure

### Simple Structure

Do not have well-defined structure, usually started as small, simple and limited system.

Ex. MS-DOS

### Traditional Unix

Somehow layered, but not strictly structured. Has kernel and system parts.

Layered Approach: Each layer built on top of lower layer.

Information Hiding: Upper layer only knows what lower layer do, but not how.

Simple for construction and debugging.

Difficult to define layers and their functionality.

### Microkernel Approach

Only include necessary functions in kernel. Implement others as system or user programs.

Communication by message passing.

Easier to extend, easier to port, more reliable.

Performance suffer due to increased system-function overhead

### Modular Approach

Loadable kernel modules

Most used modern OS approach

Resemble layered approach, but more flexible

Resemble microkernel approach, but more efficient

### Hybrid System

Adopt more than one OS design approach

## Mac OS X

Aqua GUI

Cocoa Objective-C API

BSD/Mach kernel plus kernel extensions

## iOS

Cocoa Touch API

Media Service layer

Core Services

Core OS kernel of OSX

## Android

Dalvik Runtime

Java API

Mobile-optimized libraries

Linux kernel

## Virtual** **Machine

OS running on another OS

### Emulation

Stimulate different CPU architecture

### Nachos

A learning OS

