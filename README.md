# user-level-thread-library
# Thread Library (User-Level Concurrency)

Implementation of a user-level thread library built in C++ that supports
multiprocessor scheduling, mutexes, and condition variables.

> Code omitted due to university academic integrity policy.

## Key Features
- User-level thread creation and scheduling
- Preemptive scheduling via timer interrupts
- Mutex locks with FIFO ordering
- Mesa-style condition variables
- Joinable threads
- Multi-CPU support

## Concepts Implemented
- Context switching using `ucontext`
- Cooperative and preemptive scheduling
- Ready queues and wait queues
- Synchronization primitives
- Interrupt safety

## Technologies
- C++
- ucontext
- Custom scheduler
- RAII resource management

## Design Overview
The system maintains a global ready queue of runnable threads.
Each thread is represented by a Thread Control Block (TCB) containing:

- stack
- context
- thread state
- synchronization metadata

Threads yield or block by switching back to a scheduler context using `swapcontext`.

## Key Challenges
- Ensuring interrupt safety during scheduling
- Correctly implementing Mesa monitor semantics
- Avoiding deadlocks when multiple CPUs schedule threads simultaneously
- Managing thread stacks safely

## What I Learned
- Low-level concurrency primitives
- How operating systems schedule threads
- Designing safe synchronization mechanisms
