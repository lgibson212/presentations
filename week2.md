# What is an expression? What is a statement? What is the difference (if any) between the two?
__Statements__ are anything that make up stand alone line or lines of code.

Loops, ifs, and imports are examples of statements (compound, compound, and simple statements repsectively).

**Statements "Do something"

An __expression__ is a statement that returns at least __one value__; it needs to be evaluated.

**Expressions "Evaluate something"


* http://stackoverflow.com/questions/4728073/what-is-the-difference-between-an-expression-and-a-statement-in-python
* http://interactivepython.org/courselib/static/thinkcspy/SimplePythonData/StatementsandExpressions.html


# What is lambda? What does it do and why do we use it?
lambda (function) = anonymous function, a function defined without a name.

Normal functions are defined using the **def** keyword

Lambdas are meant to be a short or one time use function since you cannot call them again (they have no name to call them by)- they can 
only be called in line or within a higher order function.


Syntax for writing a lambda function:
**lambda arguments:*****expression***

``` python
(lambda x, y: x*y)(3,5)
15
```

Anonymous functions are generally used in **higher order functions**, functions that take in other functions as arguments. Ex: map() and filter().

``` python
my_list = [1, 5, 4, 6, 8, 11, 3, 12]

map_list = list(map(lambda x: x * 2 , my_list))
# Output: [2, 10, 8, 12, 16, 22, 6, 24]

filter_list = list(filter(lambda x: (x%2 == 0) , my_list))
# Output: [4, 6, 8, 12]
```
These functions are passed a lambda function as an argument as well as my_list.

Lambda can also be used as a key:
```python
sorted([1, 2, 3, 4, 5, 6, 7, 8, 9], key=lambda x: abs(5-x))
[5, 4, 6, 3, 7, 2, 8, 1, 9]
```

* https://www.programiz.com/python-programming/anonymous-function
* http://stackoverflow.com/questions/9342574/calling-anonymous-functions-in-python-without-assigning-them-to-a-variable
