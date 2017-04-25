# What is GIL?  How does it interact with the heap stack and interpreter?

## Global Interpreter Lock


### let's take a step back.

A python script is first **compiled** to bytecode and then it is implemented (executed) by an **interpreter** like CPython\*, Jython or IronPython...

**Python.py** --compiler--> **bytecode.pyc** --interpreter--> **native machine code** that can be understood by CPU

\* CPython is the original Python implementation. It is the implementation you download from Python.org. People call it CPython to distinguish it from other, later, Python implementations, and to distinguish the implementation of the language engine from the Python programming language itself. It is written in C.

![Python Compilation and Interpretation](http://austincode.com/cosc1336/images/compilationinterpretation.PNG)


### Now back to GIL
- CPython has a Global Interpreter Lock because python is not thread safe.
- In order to support multi-threaded Python programs, there’s a global lock (GIL)
- When a thread is running is must hold the GIL before it can safely access Python objects (which are stored in a heap stack)
- Python can only run threads serially, never in parallel
* Prevents multiprocessing power
* Runnable threads compete with each other to acquire a GIL
  - present an issue of priority inversion in case of multi threading
  - new convoy effect in python 3.2  with I/O vs CPU threads

![Thread Execution Model](https://callhub.io/wp-content/uploads/2016/06/python-gil-visualization.png)

#### heap stack
- Memory management in Python involves a private heap containing all Python objects and data structures.
- how it relates to GIL?
  - objects can only be referenced by one thread (the one holding the GIL) at a time.

references:
- stackoverflow.com/questions/17130975/python-vs-cpython
- http://stackoverflow.com/questions/6889747/is-python-interpreted-or-compiled-or-both
- https://en.wikipedia.org/wiki/CPython
- https://docs.python.org/3.5/c-api/init.html
- https://callhub.io/understanding-python-gil/
