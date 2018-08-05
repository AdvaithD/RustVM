### Follows a series of posts detailing how to build a language VM

- When you type `python script.py` the python VM / language interpreter reads teh source code, translates it to bytecode that the VM can understand, and then executes it.
- Transforming the code into something that the CPU can understand and act upon: `binary`
- This process is called compilation
- Languages that run on a VM execute more slowly than ones compiled to run on specific hardware

* **Registers** - A register is a special area to store data on a CPU.\
  - A quickly accessible location available to a computer's CPU.
  - When the CPU executes code to set a variable to 5, it is loaded into a register somewhere.

### Summary

- Going to write an application that pretends to be a CPU and executes programs we write for it.
- This means we'll have to invent a language(wowow)
