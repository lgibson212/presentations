# What are JavaScript Promises?

javascript is single threaded: two bits of script cannot run at the same time; they have to run one after another

A promise is an object which can be returned synchronously from an asynchronous function. It will be in one of 3 possible states:
Fulfilled: onFulfilled() will be called (e.g., resolve() was called)
Rejected: onRejected() will be called (e.g., reject() was called)
Pending: not yet fulfilled or rejected
A promise is settled if it’s not pending (it has been resolved or rejected). Sometimes people use resolved and settled to mean the same thing: not pending.
Once settled, a promise can not be resettled. Calling resolve() or reject() again will have no effect. The immutability of a settled promise is an important feature.

If a promise has succeeded or failed and you later add a success/failure callback, the correct callback will be called, even though the event took place earlier.

This is extremely useful for async success/failure, because you're less interested in the exact time something became available, and more interested in reacting to the outcome.

pattern is pretty common when dealing with APIs: Multiple data fetches, then do something when it's all done





 promise constructor takes a function. That function takes two parameters, resolve(), and reject()
 
 
 promises define a .then() method which you use to pass handlers which can take the resolved or rejected value.
 
 Because .then() always returns a new promise, it’s possible to chain promises with precise control over how and where errors are handled. Promises allow you to mimic normal synchronous code’s try/catch behavior.
 
 
 
 
Referneces:
- https://developers.google.com/web/fundamentals/getting-started/primers/promises
- https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261
- 
