# The NULL Macro

In Linux, `NULL` is a macro which is defined as:
```c

#define NULL (void *)0

```
And that is why it is said to initialize every pointer to `NULL`, so that you
can get seg-fault :) [by accessing virtual address 0] in case of blind access.

# Linked List Beauty

1. The way generic Linked List is created with the help of `container_of` macro.
The code for this macro is used to calculate the base address of any custom-made
Linked List (Smartest `1-line code` encountered so far).

2. There could be many reasons (some simpler and some software engineering related)
to create a generic Linked List kernel data structure. Out of all this reasons,
one reason, which I have recently encountered (Thanks to `CRIU`), could be: <br/>
The functions like **list\_add**, **list\_del** and others do not perform
any memory allocation or deallocation (opposed to what we learn in our data
structure classes). It just perform pointer manipulations. You could say
_"Yeah I know. Whats big deal in that?"_. It become crucial when you are
maintaining (feature addition, refactoring, reusebility) applications/ drivers.

# OS: The Born Manager

Its ever evolving isolation mechanism:
* From process to threads, to virtual machines (hypervisors), to containers
(cgroups and namespaces).
