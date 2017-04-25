# What is GIL?  How does it interact with the heap stack and interpreter?

## Global Interpreter Lock


### let's take a step back.

A python script is first **compiled** to bytecode and then it is implemented (executed) by an **interpreter** like CPython\*, Jython or IronPython...

\* CPython is the original Python implementation. It is the implementation you download from Python.org. People call it CPython to distinguish it from other, later, Python implementations, and to distinguish the implementation of the language engine from the Python programming language itself. It is written in C.


**Python.py** --compiler--> **bytecode.pyc** --interpreter--> native machine code that can be understood by CPU

### Now back to GIL
"The Python interpreter is not fully thread-safe. In order to support multi-threaded Python programs, there’s a global lock, called the global interpreter lock or GIL, that must be held by the current thread before it can safely access Python objects." - python documentation

TLDR: Python can only run things serially. never in parallel. because of the GIL.

![Alt Text](https://www.google.com/url?sa=i&rct=j&q=&esrc=s&source=images&cd=&ved=0ahUKEwjCrZLM4r7TAhUEbSYKHaNlBMAQjRwIBw&url=https%3A%2F%2Fwww.slideshare.net%2Femayssat%2Fpythonunderstanding-gil&psig=AFQjCNEENLUboYsoKRknxtnf-FuxWy7vtg&ust=1493180929522996)

references:
- stackoverflow.com/questions/17130975/python-vs-cpython
- http://stackoverflow.com/questions/6889747/is-python-interpreted-or-compiled-or-both
- https://en.wikipedia.org/wiki/CPython
- https://docs.python.org/3.5/c-api/init.html
- 
