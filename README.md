# presentations
## zip() function
## Explain what the function does, provide at least one example of the use of the function and be prepared to present this topic on Monday.

In python 3 you nearly always get a generator^ object from operations such as zip or range.

In Python 3 zip returns an iterator^, use list or dict to see its content.

^Every generator is an iterator, but not vice versa. (An iterator is an iterable.) This produces less memory overhead, as no big iterable is created, holding all the needed values.

An iterator is an object that implements *next*. next is expected to return the next element of the iterable object that returned it, and raise a StopIteration exception when no more elements are available.

If you want to get the list, call list() on the generator.

```python
l = list(zip([1, 2, 3], [4, 5, 6]))
# However, this will give you a list of tuples:

l
[(1, 4), (2, 5), (3, 6)] 
#If you want to get a list of lists, use a *list comprehension:*

l = [list(t) for t in zip([1, 2, 3], [4, 5, 6])] 
```

With zip we can act upon two lists at once. Zip() is a built-in function. We pass it sequences, like lists, and it enumerates them together- like the teeth in a Zipper.

You can use zip with * to get transpose of a matrix:
```
>>> A = [[ 1, 2, 3],[ 4, 5, 6]]
>>> zip(*A)
[(1, 4), (2, 5), (3, 6)]
>>> lis  = [[1,2,3], 
... [4,5,6],
... [7,8,9]]
>>> zip(*lis)
[(1, 4, 7), (2, 5, 8), (3, 6, 9)]
If you want the returned list to be a list of lists:

>>> [list(x) for x in zip(*lis)]
[[1, 4, 7], [2, 5, 8], [3, 6, 9]]
#or
>>> map(list, zip(*lis))
[[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```

Referenced:
* https://wiki.python.org/moin/Iterator
* http://stackoverflow.com/questions/17037566/transpose-a-matrix-in-python
* https://www.dotnetperls.com/zip-python
* http://stackoverflow.com/questions/2776829/difference-between-pythons-generators-and-iterators


## What is a function? What is a method? What is the difference (if any) between a function and a method?

This hits at the heart of what Object Oriented Programming is. In an OOP language, programs are largely based around Classes and Objects, rather than Functions.

A Class, such as "cell phone", can have many Objects, such as Apple iPhone7, Galaxy Note 7, Blackberry Curve and Google Pixel. A Class is like a template for an Object instance. The Class "cell phone" can have Attributes attached to an Object which store data, usually variables, such as keyboard type, mobile OS, camera pixels, and spontaneous flamability. The Class "cell phone" can also have Functions (procedures) attached to an Object which allow the Object to perform actions, such as create new contact, call mom, send txt, and take photo.

A Method is a Function that is  stored/defined in a Class. This makes the relationship between Class and Method explicit. When OOP languages call a Method, it binds the first argument of the call to the appropriate Object reference within the Method's Class. All Methods are therefore Functions, but not all Functions are Methods. (Method = square, Function = rectangle)

Ex:
```python
class Dog:
    def bark(self):
        print 'Woof woof!'

rufus = Dog()
rufus.bark()

# rufus is an Object and bark is a Method, both within the Class "Dog". Such a method would not work on a "Cat" Class.
```


#### The syntax for invoking a Method is different from the syntax for calling a Function.

> A Method uses dot notation.
> Ex: my_string.upper() where upper is a Method within the Class string, and only works on string objects such as my_string.


> A function is a globally defined procedure that can call on anything.
> Ex: len(my_string) or len(my_list) where len is a function that returns the number of items in the given arguement and can work on different Classes (strings, lists, tupels, etc).


Bonus: Parameters appear in definitions; arguments appear in calls.


##### The syntax for a Function call: print(my_string), suggests that the Function is the active agent. It says something like, "Hey print! Here's an object for you to print."


##### In OOP, the Objects are the active agents. ~~An invocation like console.log() says "Hey console! Please log yourself!"~~ An invocation like: my_string.upper(), says "Hey my_string! Please uppercase yourself!"


##### This change in perspective might be more polite, but it is not obvious that it is useful. In the examples we have seen so far, it may not be. But sometimes shifting responsibility from the functions onto the objects makes it possible to write more versatile functions, and makes it easier to maintain and reuse code*.

*Write DRY code: Don't Repeat Yourself. A principle of software development aimed at reducing repetition of information of all kinds.



Referenced:

* https://en.wikibooks.org/wiki/A-level_Computing_2009/AQA/Problem_Solving,_Programming,_Operating_Systems,_Databases_and_Networking/Programming_Concepts/Object-oriented_programming_(OOP)#Methods

* http://www.greenteapress.com/thinkpython/thinkCSpy/html/chap14.html

* https://www.quora.com/Whats-the-difference-between-a-method-and-function-in-Python

* http://stackoverflow.com/questions/28703834/why-do-some-methods-use-dot-notation-and-others-dont

* https://docs.python.org/3.6


