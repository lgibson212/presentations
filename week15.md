# What are JavaScript Promises?

javascript is single threaded: two bits of script cannot run at the same time; they have to run one after another

A Promise is an object which can be returned synchronously from an asynchronous function.

Lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.

A better way/abstraction for writing callbacks and avoiding "callback hell" (nested callbacks in nested callbacks) in JS.

Promise constructor takes a function, that takes two parameters, resolve, and reject.

https://jsbin.com/rodelanawu/1/edit?js,console


It will be in one of 3 possible states:
![states](https://raw.githubusercontent.com/basarat/typescript-book/master/images/promise%20states%20and%20fates.png)
A promise is settled if it’s not pending (it has been resolved or rejected). Sometimes people use resolved and settled to mean the same thing: not pending.

Once settled, a promise cannot be resettled. Calling resolve() or reject() again will have no effect. The immutability of a settled promise is an important feature.

If a promise has succeeded or failed and you later add a success/failure callback, the correct callback will be called, even though the event took place earlier.

This is extremely useful for async success/failure, because you're less interested in the exact time something became available, and more interested in reacting to the outcome.

Common when dealing with APIs: Multiple data fetches, then do something when it's all done.
You don't want your entire process to be blocked while waiting for results.

Promises define a .then() method which you use to pass handlers which can take the resolved or rejected value.

Anything that needs to wait for promise to proceed, you put that in .then.

Because .then() always returns a new Promise, it’s possible to chain promises with precise control over how and where errors are handled. Promises allow you to mimic normal synchronous code’s try/catch behavior.

![timeline](https://cdn.tutsplus.com/net/uploads/2013/04/promise-validation-promise.png)
 

 
https://jsfiddle.net/yz27rvay/

 
Referneces:
- https://developers.google.com/web/fundamentals/getting-started/primers/promises
- https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then
- https://scotch.io/tutorials/javascript-promises-for-dummies
- 
