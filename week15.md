# What are JavaScript Promises?

a Promise object represents an operation which has produced or will eventually produce a value. Promises provide a robust way to wrap the (possibly pending) result of asynchronous work, mitigating the problem of deeply nested callbacks (known as "callback hell").

Instead of immediately returning the final value, the asynchronous method returns a Promise to supply the value at some point in the future.

Promise constructor takes a function, that takes two parameters, resolve, and reject.

scotch.io tutrials code:
https://jsbin.com/sisifofake/edit?js,console

https://jsbin.com/rodelanawu/1/edit?js,console


will be in one of 3 possible states:
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
 

https://jsfiddle.net/api/mdn/

https://jsfiddle.net/yz27rvay/

 
Referneces:
- https://developers.google.com/web/fundamentals/getting-started/primers/promises
- https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then
- https://scotch.io/tutorials/javascript-promises-for-dummies
- http://stackoverflow.com/documentation/javascript/231/promises#t=201704301901386431347
