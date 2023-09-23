# Javascript

- Only has primitive types and objects. Everything besides primitive types are objects.
- Primitive types are boolean, null, undefined, bigint, number, string, and symbol.
- JavaScript is a dynamically typed language: we don't specify what types certain variables are.
- Coercion is converting from one type into another. Values can automatically be converted into another type without you knowing, which is called implicit type coercion.
- If you want a method to be available to all object instances, you have to add it to the prototype property. Therefore, the method gets added only to the constructor function object itself.
- When using "new" keyword, "this" refers to the new empty object created. However, if you don't add "new" keyword, "this" refers to the global object.
- During the addition of a numeric type and a string type, the number is treated as a string.
- When testing equality, primitives are compared by their value, while objects are compared by their reference (location in memory).
- With "use strict", you can make sure that you don't accidentally declare global variables;
- When we stringify an object, it becomes "[object Object]";
- "typeof" can return the following list of values: undefined, boolean, number, bigint, string, symbol, function and object. Note that "typeof null" returns "object".
- There are 8 falsy values: undefined, null, NaN, false, '' (empty string), 0, -0, 0n (BigInt(0))
- Function constructors, like new Number and new Boolean are truthy.

# What is node

- JavaScript runtime environment.
- Platform built on Chrome's JavaScript runtime.
- It is a single threaded, non-blocking and event driven.
- Used for Back-End development and general scripting.
- NPM is the default package manager for Node.
- "package.json" is the file used to describe and configure your JavaScript project.

# Classes

- Sintax suggar over JS existing prototype based inheritance
- It is not a object oriented inheritance model

# Synchronous and Asynchronous

- Synchronous is when tasks are executed sequentially, one after the other, in a predictable order.
- Asynchronous is when tasks are executed concurrently, and the order of execution is not guaranteed.

# Promise

- Object that represents a value that may not be available yet but will be resolved in the future.
- Object that wait for an asynchronous operation to complete.
- Resolve (1st handler): function to call with the future value when it is ready.
- Reject (2nd handler): function to call to reject the promise if it can't resolve the future value.

# Async/Await

- Async/await is a way to write asynchronous code that looks like synchronous code.
- It allows developers to write code that waits for a promise to resolve before executing the next line of code.

# Event Loop

- handles the asynchronous task and multiple requests at a time in parallel.
- allows Node.js to perform non-blocking I/O operations by offloading operations to the system kernel whenever possible.
- Responsible for executing the code, collecting and processing events and executing queued sub-tasks.
- execute the async task as per priority
- It continuously monitors the call stack and the message queue, and when the call stack is empty, it takes the first message from the queue and adds it to the call stack.

# Call Stack

- FIFO queue of callbacks to execute
- three phases of event propagation: Capturing \> Target \> Bubbling. During the "capturing" phase, the event goes through the ancestor elements down to the target element. It then reaches the "target" element, and "bubbling" begins.

# Let / Const / Var

- "let" and "const" are scoped to the nearest enclosing block.
- "const" has to be defined with its declaration.
- "const" cannot be re-assigned, but "let" can.
- "let" and "const" are hoisted, but cannot be accessed before their declaration (don't get initialized). They are not accessible before the line we declare them and this is called the "temporal dead zone". When we try to access the variables before they are declared, JavaScript throws a "ReferenceError".
- variables with "var" keyword are hoisted and initialized with "undefined".

# This

- Each function in JavaScript defines its own "this" context.
- arrow functions capture the "this" value of the nearest enclosing context.
- arrow functions don't have their own bindings to "this".
- With arrow functions, the "this" keyword refers to its current surrounding scope, unlike regular functions.

# Hoisting

- memory space is set up during the creation phase of element
- behavior in JavaScript where variable and function declarations are moved to the top of their respective scopes.
- variable or function can be used before it has been declared, although it will still be "undefined" until it is assigned a value.
- Using "bind", "call", or "apply" will override the value inside a function, and you can hardcode its value for "this".

# Null coalescing

- The OR Operator (||) Will Return the First Truthy Value.
- The Nullish Coalescing Operator (??) Is Smarter. It will return the first defined value (not null/undefined), So if the first value is an empty string, 0, or false, it will return that value.

## What Data Types Does Nullish Coalescing Work With?

- Nullish coalescing works with any data type in JavaScript, including:
- Numbers: 0 ?? 1 // Returns 1
- Strings: '' ?? 'Hello' // Returns 'Hello'
- Booleans: false ?? true // Returns true
- Objects: {} ?? {name: 'John'} // Returns {name: 'John'}
- Arrays: [] ?? [1, 2, 3] // Returns [1, 2, 3]

## What's the Difference Between || (OR) and ?? (Nullish Coalescing) Operators?

- The || (OR) operator will return the right operand if the left operand is falsy (false, 0, empty string, null, undefined, NaN).
- The ?? (Nullish Coalescing) operator will only return the right operand if the left operand is null or undefined.
- So the key difference is that ?? considers 0 and empty strings to be valid values, whereas || does not.

## When Should I Use ?? Over ||

- Use ?? when you want to provide a default value for null or undefined, but consider 0 and empty strings to be valid values.
- Use || when you want to provide a fallback for any "falsy" value.
