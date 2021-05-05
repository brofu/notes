# Virtual Memory

This article will answer some key questions about virtual memory.
  * Why virtual memory
  * Memory layout for user mode process and kernel mode

**Why Virtual Memory**
  * Isolation from process (user mode) perspective

**Memory Layout (User mode process)**

  ![user_layout][layout_1]

  * Text Segment (also known as Code Segment)
 
    * Executable instructions
    * Usually is sharable. So only 1 copy needs to be in memory for frequently executed programs
    * Often read-only.

  * Data Segment
  
    Static constant 

  * BSS Segment
   
    Static variables uninitialized 

  * Heap

    Allocated dynamically

  * Memory Mapping Segment

    so file

  * Stack

    Function call stacks


**Memory Layout (Kernel mode process)**

  ![kernel_layout][layout_2]

  * Similar as user mode. Text, Data and BSS segments
  * Not so **isolated** as viewing from user mode processes.
  * Actually, memory is **shared** among all process.


[layout_1]: ../img/memory_1.jpeg
[layout_2]: ../img/memory_2.jpeg

**Reference:**

https://www.geeksforgeeks.org/memory-layout-of-c-program/
