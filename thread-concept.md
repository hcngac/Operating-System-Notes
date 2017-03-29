# Thread Concept

## Motivation

Modern applications need multiple thread of execution to update display, fetch data, do network request and so on at the same time.

But creating new process is costly.

Extra thread of execution can share process information with existing thread of execution.

Example is a server creating different threads, one for each client.

## Benefits

Allow more responsive user interface, letting the extra thread to do the timely work while Ui thread updates UI

Easier for sharing resources among threads than among processes

Thread creation is cheaper than process creation

Take advantage of multicore architecture

## Multicore Programming

### Parallelism

Performing more than one task at the same instance of time

#### Data Parallelism

Same operation on different subset of data

#### Task Parallelism

Different operation on different threads

### Concurrency

Multiple processes having progress over a period of time

### Amdahl's Law

S = Serial portion of the operation

N = Number of processing cores

speedup &lt;= 1 / \( S + \( 1 - S \) / N \)

## Thread State

Saved in Thread Control Block \(TCB\)

* Execution state
* Scheduling information
* Accounting information
* Pointer to process
* Others

Threads under same process share:

* Global variables
* Heap
* I/O state

States not shared:

* TCB
* Registers
* Stack

## Thread Lifecycle

Similar to process lifecycle:

* New
* Ready
* Running
* Waiting
* Terminated

## Thread Support

### User Thread

Lives in user space, managed by libraries

A.K.A logical thread

### Kernel Thread

Supported by kernel

### User Thread - Kernel Thread Relationship

#### Many-to-one

Many user threads mapped to one kernel thread

One thread blocking would block all threads

Threads may not run in parallel

#### One-to-one

Each user thread has it's corresponding kernel thread

More concurrency

High overhead, may restrict number of threads

#### Many-to-many

A pool of user threads mapped to a pool of kernel threads

#### Two-level Model

Allow many-to-many and one-to-one to exist at the same time

### Thread Library

Provide API to utilize threads

* POSIX Pthread
* JAVA threads
* Windows API threads

## Threading Issues

### fork\(\) and exec\(\)

fork\(\) copies all the threads unless exec\(\) is called immediately. In that case only current thread would be copied.

### Signal handling

#### Synchronous Signal

Caused by errors in operation of current thread

#### Asynchronous Signal

Caused by external events

#### Signal handling

Handled by kernel-defined default signal handler if not overrided by user-defined signal handler

Signal can be delivered to:

* All threads
* Threads that the signal applies
* Certain threads
* One specific thread handle all signals
* Synchronous signal delivered to the problematic thread
* Terminating signal delivered to all threads

### Thread Cancellation

To terminate a thread before it completes

#### Asynchronous cancellation

The target thread is cancelled immediately

#### Deferred Cancellation

Target thread periodically checks if it should be cancelled, avoiding being terminated without cleaning up

### Thread-Local Storage \(TLS\)

Global variable visible to the thread alone

## Thread Example

### Windows

One-to-one mapping

### Linux

clone\(\) creates new process, but can be told by parameter to share some address space with parent process.



