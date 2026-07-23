# vfastqueue.
(ideally) fast lockless FIFO queue written in C.\
no dependencies other than the standard C library.\

## usage.
include vfastqueue.h into your project. much like stb libraries, define the macro `VFASTQUEUE_IMPLEMENTATION` in the file you want the actual implementation to reside; otherwise you're just including the headers.\

## innovations.
this library's very interesting from a technical point of view, as it implements ABA-free CAS without using a double-width cmpxchg & it allows multiple readers & writers concurrently without locking at all.\
the queue is unbounded in size as it is implemented as a linked list with a head & a tail. adding & removing are both O(1) operations.
