

## 🧠 What Classes Are

In JavaScript, **classes** are a *syntax for creating objects and reusable blueprints* (similar to classes in languages like Java or C++). Under the hood, JavaScript still uses **prototypes**, but the class syntax makes it much easier to express object-oriented designs.

---

## 🟦 Class Declaration

You define a class using the `class` keyword:

```js
class Person {
  constructor(name, age) { 
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}
```

* `constructor()` runs when you create a new instance.
* Methods go inside the class body without the `function` keyword.

---

## 🧾 Creating Instances

Use `new` to make objects from a class:

```js
const p = new Person("Alex", 30);
p.greet(); // "Hi, I'm Alex"
```

The `new` keyword:

1. Creates a new plain object
2. Sets up internal prototype linkage
3. Calls `constructor()` on that object
4. Returns the object

---

## 📦 Methods vs Prototype

Class methods are actually stored on the class’s **prototype**, not directly on each instance. This saves memory and supports shared behavior across objects.

---

## 💫 Inheritance

You can make one class inherit from another using `extends`:

```js
class Animal {
  speak() {
    console.log("Animal noise");
  }
}

class Dog extends Animal {
  speak() {
    super.speak(); // call parent method
    console.log("Bark!");
  }
}

const d = new Dog();
d.speak();
```

* `extends` sets up prototype inheritance
* `super` calls the parent class’s methods (e.g., constructor or others)

---

## 🔐 Special Kinds of Methods

### Static Methods

Belong to the class itself, not instances:

```js
class MathHelpers {
  static square(x) {
    return x * x;
  }
}

console.log(MathHelpers.square(4)); // 16
```

Static methods are great for utility functions that don’t rely on instance data.

---

## 🕵️ Getters & Setters

You can define properties that behave like data but run code under the hood:

```js
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  get area() {
    return this.width * this.height;
  }
}

const r = new Rectangle(3,4);
console.log(r.area); // 12
```

Getters let you treat functions like properties.

---

## 🧽 Private Fields

You can define truly private data using `#`:

```js
class Counter {
  #count = 0;

  increment() {
    this.#count++;
  }

  get value() {
    return this.#count;
  }
}

const c = new Counter();
c.increment();
console.log(c.value); // 1
```

Private fields are only accessible within the class body.

---

## 💭 Quick Takeaways

| Feature            | What It Does                          |
| ------------------ | ------------------------------------- |
| **class**          | Defines a blueprint for objects       |
| **constructor**    | Initializes new instances             |
| **extends**        | Inherits from another class           |
| **super**          | Calls the parent’s method             |
| **static**         | Class-level method (not per instance) |
| **get/set**        | Computed properties                   |
| **private fields** | Truly internal data                   |

---

## 🧪 How It Compares to Prototypes

Classes are mostly “syntactic sugar” — they make prototype-based inheritance easier to read and write, but the underlying behavior is still prototypal.
