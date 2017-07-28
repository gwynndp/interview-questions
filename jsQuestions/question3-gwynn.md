* Explain how prototypal inheritance works

 JavaScript does a good job of emulating object oriented programming even thought it isn't designed to work that way from scratch.  The root of this emulation is being able to make a new instance of an object with it's referenced values and methods without having to copy all of them and use up more space.

 Everything in JavaScript is an object, but it can also be said that everything is a function.  All JS functions have a default property called Prototype which stores stuff.  There are default methods available to all JS objects, and there are also more unique methods, particularly for special classes that are already defined in JavaScript. We can also store our own custom methods on Prototype when we want to define our own custom class.

 The advantage is that whenever we create an instance of a class we will have access to those methods, without duplication, because the JS processor will find the methods on our parent class.