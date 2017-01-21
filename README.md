# presentations

##Zip

###Explain what the function does, provide at least one example of the use of the function and be prepared to present this topic on Monday.



###What is a function? What is a method? What is the difference (if any) between a function and a method?

* Short form: methods are associated with object instances or classes; functions aren't. When Python dispatches (calls) a method, then it binds the first parameter of that call to the appropriate object reference. (For most methods that's conventionally called self).

* Methods are defined inside a class definition in order to make the relationship between the class and the method explicit.

* All methods are functions but not all functions are methods.

* The syntax for invoking a method is different from the syntax for calling a function.



defined a class named Time and you wrote a function named printTime, which should have looked something like this:

'''
class Time: 
  pass 

def printTime(time): 
  print str(time.hours) + ":" + \ 
        str(time.minutes) + ":" + \ 
        str(time.seconds) 
'''

To call this function, we passed a Time object as an argument:

>>> currentTime = Time() 
>>> currentTime.hours = 9 
>>> currentTime.minutes = 14 
>>> currentTime.seconds = 30 
>>> printTime(currentTime) 

To make printTime a method, all we have to do is move the function definition inside the class definition. Notice the change in indentation.

'''
class Time: 
  def printTime(time): 
    print str(time.hours) + ":" +  \ 
          str(time.minutes) + ":" +  \ 
          str(time.seconds) 
'''

Now we can invoke printTime using dot notation.

>>> currentTime.printTime() 

As usual, the object on which the method is invoked appears before the dot and the name of the method appears after the dot.

The object on which the method is invoked is assigned to the first parameter, so in this case currentTime is assigned to the parameter time.

By convention, the first parameter of a method is called self. The reason for this is a little convoluted, but it is based on a useful metaphor.

The syntax for a function call, printTime(currentTime), suggests that the function is the active agent. It says something like, "Hey printTime! Here's an object for you to print."

In object-oriented programming, the objects are the active agents. An invocation like currentTime.printTime() says "Hey currentTime! Please print yourself!"

This change in perspective might be more polite, but it is not obvious that it is useful. In the examples we have seen so far, it may not be. But sometimes shifting responsibility from the functions onto the objects makes it possible to write more versatile functions, and makes it easier to maintain and reuse code.

