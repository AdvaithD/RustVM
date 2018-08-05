- Building a VM/interpreter for a programming language in Rust.

### Goals

- We want our VM to be reasonably performant compared to modern implementations
  - Benchmark with python
  - Fault tolerant
  - Serves as command and control platform for running applications
  - Clustering of VM's running on different physical servers

### Types of VM's

1.  **Tree Walking**
    1.  Transformes source code into a tree like data structure
    2.  Starts at the root of the tree and visits each node, performing operationnode
    3.  Performs operations as it goes along the nodes
    4.  Pros: Simple, greater flexibility to transform(because it is already a data structure)
    5.  Cons: Slow as compared to other types
2.  **Stack Based**
    1.  Most common. Examples: JVM, Python
    2.  Store operations and results on a stack
    3.  When the VM executes an instruction, most recent value of the stack is popped
    4.  Operation performed, followed by pushing result to the stack
    5.  Pros: Easier to code than regiuster based VM, decent performance
    6.  Cons: Does not map to real hardware, CPU's use registers, Most tasks require more instructions.
3.  **Register Based**
    1.  Least common. Examples: BEAMVM, Lua VM, Dalvik VM(runs Java code on android)
    2.  Pros: Much closer to how actual hardware works, More performant
    3.  Cons: Comples to code, worry about register allocation and de-allocation

### Structure of an Assembly Instruction

- Ability to take 32 bits of data at a time, execute it and then go get another group of 32 bits.

1.  Read next instruction
2.  Execute next instruction
3.  Repeat

### Misc

- A grouping of 32-bits is an instruction.
- The first 8 bits of the 32 will contain Opcode
- Remaining bits dedicated to Operands
  - Opcode can have 0, 1, 2, or 3 Operands
