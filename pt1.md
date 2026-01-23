# javascript-guide
Difference between JavaScript and Java



## 1. **“Share some syntax”**

This just means **they look similar when written**.

```js
// JavaScript
if (x > 5) {
  doSomething();
}
```

```java
// Java
if (x > 5) {
  doSomething();
}
```

Same curly braces, `if`, `for`, etc.
But how they *work* under the hood is very different.

---

## 2. **Dynamically typed (JavaScript)** vs **Statically typed (Java)**

### JavaScript = dynamically typed

You **don’t tell the language what type something is**. It figures it out while the program is running.

```js
let x = 5;        // x is a number
x = "hello";     // now x is a string — totally allowed
```

Pros:

* Faster and easier to write
* More flexible

Cons:

* More errors show up **while running**, not beforehand

---

### Java = statically typed

You **must declare the type**, and it can’t change.

```java
int x = 5;
x = "hello"; // ❌ ERROR — not allowed
```

Pros:

* Errors are caught **before the program runs**
* Safer for large systems

Cons:

* More verbose and strict

---

## 3. **Prototype-based (JavaScript)** vs **Class-based (Java)**

### JavaScript = prototype-based

Objects can **inherit from other objects directly**, and you can **change them on the fly**.

```js
let car = {
  wheels: 4
};

car.color = "red"; // added later — no problem
```

You can add properties or functions to **individual objects at runtime**.

Think of it like:

> “This object is based on that object, and I can tweak it whenever I want.”

---

### Java = class-based

You must define a **class first**, then create objects from it.

```java
class Car {
  int wheels = 4;
}
```

You **cannot** add new properties to an object after it’s created.

Think of it like:

> “All cars must follow this exact blueprint.”

---

## 4. **Flexible (JavaScript)** vs **Rigid (Java)**

### JavaScript is flexible

* You don’t have to declare variables ahead of time
* You can add/remove properties and methods at runtime
* Functions can be passed around like variables

```js
function greet() {
  console.log("Hi");
}

greet.language = "English"; // yes, functions can have properties
```

This is powerful, but can get messy in large projects.

---

### Java is rigid (by design)

* Everything must fit the class structure
* Access rules are strict (public/private)
* Memory and types are tightly controlled

This makes Java:

* Safer
* More predictable
* Better for large, long-lived systems

---

## 5. **Type safety & structured object hierarchies (Java)**

### Type safety

Java **prevents you from doing unsafe things**, like treating one type as another.

```java
Object x = "hello";
Integer y = (Integer) x; // ❌ runtime error
```

Java actively tries to stop bugs like this.

---

### Structured object hierarchies

Java programs are organized like **family trees of classes**:

```java
Animal
 └── Dog
     └── Labrador
```

Everything fits neatly into a hierarchy, which helps large teams work together.

---

## One-sentence intuition

* **JavaScript**: *“Figure it out as you go, change things whenever you want.”*
* **Java**: *“Define everything clearly first, then follow the rules strictly.”*

