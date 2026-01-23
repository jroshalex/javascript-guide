## JavaScript Functions — Big Picture

A **function** is reusable code that:

* Takes **inputs** (parameters)
* Does some work
* **Returns an output**

You must **define** a function before you can **call** it, and it must be in scope.

---

## Defining Functions

### Function Declarations

The classic way:

```js
function square(x) {
  return x * x;
}
```

* Has a name
* Can be called **before** it appears in the code (hoisting)
* Common and readable

---

### Function Expressions

Functions stored in variables:

```js
const square = function (x) {
  return x * x;
};
```

* Can be anonymous or named
* Not hoisted
* Useful for passing functions as values (callbacks)

Functions can be:

* Passed into other functions
* Returned from functions
* Stored in variables
  ➡️ This is a core JavaScript idea.

---

## Calling Functions

Calling a function runs its code:

```js
square(5); // 25
```

* Arguments can be numbers, strings, objects, arrays, etc.
* Functions can **call themselves** (recursion)

---

## Parameters & Arguments

### Pass-by-value vs objects

* Primitives (numbers, strings): changes don’t affect the outside
* Objects & arrays: changing properties/elements **does affect** the original

---

### `arguments` object

* Inside every non-arrow function
* Holds all passed arguments
* Array-like, but not a real array

Useful when you don’t know how many arguments you’ll get.

---

### Default parameters

Set fallback values:

```js
function multiply(a, b = 1) {
  return a * b;
}
```

---

### Rest parameters

Collect extra arguments into an array:

```js
function multiply(multiplier, ...nums) {
  return nums.map(n => multiplier * n);
}
```

---

## Arrow Functions

Shorter syntax:

```js
x => x * x
```

Key differences:

* Short and clean
* **No own `this`**
* No `arguments`
* Cannot be used as constructors

Great for callbacks and small functions.

---

## Scope & Closures

### Scope

* Variables inside a function are **not accessible outside**
* Inner functions can access outer variables
* Outer functions **cannot** access inner variables

---

### Closures

A **closure** is when a function “remembers” variables from where it was created, even after that outer function finishes running.

This allows:

* Private variables
* Encapsulation
* Persistent state

Very powerful, very common in JS.

---

## Recursion

A function calling itself:

* Similar to loops
* Needs a base case to stop
* Uses the call stack

Used for:

* Tree structures (like the DOM)
* Problems that naturally break into smaller versions of themselves

---

## IIFE (Immediately Invoked Function Expression)

A function that runs immediately:

```js
(function () {
  // runs right away
})();
```

Used to:

* Create private scope
* Avoid polluting global variables

Less common now, but still good to recognize.

---

## Hoisting (Important!)

* **Function declarations are hoisted**
* **Function expressions are NOT**

✅ This works:

```js
square(5);
function square(n) { return n * n; }
```

❌ This doesn’t:

```js
square(5);
const square = function(n) { return n * n; };
```

---

## TL;DR (What to Remember)

* Functions are reusable blocks of code
* JS functions are values (can be passed around)
* Objects/arrays can be modified through parameters
* Closures let functions remember variables
* Arrow functions are shorter and don’t bind `this`
* Function declarations are hoisted, expressions aren’t
