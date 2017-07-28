* Explain how `this` works in JavaScript

In JavaScript `this` is used to reference whatever it was that called the current method that was invoked.  It is a useful concept that is based on the context of each and every function call, which also makes it difficult to define and often difficult to pin-point in cases where the environment or context of a running function is unclear.

The reference is only valid at the time a function/method is invoked and is only stable for the duration of that invokation.  For example, if the method belogs to a class, `this` can often refer to the specific instance of the class which called it, but there may be many instances of the same class, each with their own state.

Some simple guidelines are to find what environment/context/class/instance the function was called in?

- Look for the first enclosing braces of a function definition where this is used then....
- Look for where the function was invoked (next line down in the callstack), then...
- Is it a global reference of `this` or from a free function invocation ==> the global object / window
- Is it a method invocation ==> whatever is to the left of the '.' at time of invocation
- Is it a binding ==> the target of .call, .apply, or .bind
- Is it a constructor with the keyword 'new' ==> a new instance object
