#
## notes
- Under the hood, JavaScript always and only has prototypal inheritance. What makes things more complicated is how constructor functions are used to set up chains of prototypes. In ECMAScript 5, they are the mainstream way of doing inheritance, though. And in ECMAScript 6, you get classes as syntactic sugar for constructors that hides the complications well enough that you should never have problems in practice.
- Interestingly, prototypal inheritance and (truly) class-based inheritance are not drastically different, conceptually. In prototypal inheritance prototypes roughly correspond to classes [1]. The main differences are:
Class-based inheritance: There are two entities (classes and objects) and two kinds of relationships between entities (the instance-of relationship between an object and a class and the subclass-of relationship between classes).
Prototypal inheritance: There is only one kind of entity (the object) and one relationship between entities (the prototype-of relationship between objects). However, the conceptual difference between subclassing and instantiating still exists. One advantage of prototypal inheritance is that you can start with objects and introduce abstractions later. In class-based languages you normally need a class to produce an object, even if it is just a single one (hence the singleton pattern, as a work-around).
[1] http://bibliography.selflanguage.org/organizing-programs.html


