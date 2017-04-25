# What is GIL?  How does it interact with the heap stack and interpreter?

## Global Interpreter Lock


### let's take a step back.

A python script is first **compiled** to bytecode and then it is implemented (executed) by an **interpreter** like CPython\*, Jython or IronPython...

\* CPython is the original Python implementation. It is the implementation you download from Python.org. People call it CPython to distinguish it from other, later, Python implementations, and to distinguish the implementation of the language engine from the Python programming language itself. It is written in C.


#### Python.py --compiler--> bytecode --interpreter--> native machine code that can be understood by CPU

### Now back to GIL



references:
- stackoverflow.com/questions/17130975/python-vs-cpython
- http://stackoverflow.com/questions/6889747/is-python-interpreted-or-compiled-or-both
- 
