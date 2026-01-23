

## 🧠 What Objects Are

In JavaScript, an **object** is a collection of **properties** where each property has a **key** (name) and a **value**. If the value is a function, that property is called a **method**. Objects are fundamental to JavaScript and are used everywhere. ([MDN Web Docs][1])

---

## 🧱 Creating Objects

### **Object literals**

The simplest way to make an object:

```js
const myCar = {
  make: "Ford",
  model: "Mustang",
  year: 1969
};
```

This creates a “plain object” with named properties. ([MDN Web Docs][1])

---

### **Constructor Functions**

You can define a “type” using a function and make instances with `new`:

```js
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}

const car1 = new Car("Honda", "Civic", 2020);
```

This creates separate objects with the same structure. ([MDN Web Docs][1])

---

### **Object.create()**

Create a new object that inherits from a prototype object:

```js
const proto = { greet() { console.log("Hi"); } };
const obj = Object.create(proto);
obj.greet(); // Hi
```

Useful when you want to choose an object’s prototype without a constructor. ([MDN Web Docs][1])

---

## 🔑 Accessing & Modifying Properties

Two ways to get/set properties:

* **Dot notation:** `obj.key`
* **Bracket notation:** `obj["key"]`

Bracket form lets you use dynamic keys (e.g., variables). ([MDN Web Docs][2])

```js
const key = "color";
myCar[key] = "red"; // same as myCar.color = "red"
```

---

## 🚶‍♂️ Enumerating Properties

You can list keys:

* `for...in` loops through all enumerable properties (including prototype chain)
* `Object.keys(obj)` returns an array of own property names
* `Object.getOwnPropertyNames(obj)` gets own names including non-enumerable ones ([MDN Web Docs][2])

---

## 🗑 Deleting Properties

Remove a property with `delete`:

```js
delete myCar.year;
```

After this, `"year" in myCar` becomes `false`. ([MDN Web Docs][2])

---

## 📍 Inheritance & Prototypes

Objects inherit from a “prototype” object.
Properties from the prototype aren’t own properties but still accessible via the prototype chain. ([MDN Web Docs][2])

### **Prototype properties**

You can add shared properties or methods that all instances of a type will use:

```js
Car.prototype.getInfo = function () {
  return `${this.make} ${this.model}`;
};
```

Now every `Car` object gets `getInfo()` without duplicating the function. ([MDN Web Docs][2])

---

## 💡 Methods & `this`

A method is just a function stored in an object:

```js
const person = {
  name: "Sam",
  sayHi() {
    console.log(`Hi, I’m ${this.name}`);
  }
};
```

Inside a method, `this` refers to the object the method belongs to. ([MDN Web Docs][2])

---

## ⚙ Getters & Setters

You can define **getter** and **setter** properties that run functions when a property is read or assigned:

```js
const obj = {
  a: 7,
  get b() { return this.a + 1; },
  set c(x) { this.a = x / 2; }
};

console.log(obj.b); // 8
obj.c = 50;
console.log(obj.a); // 25
```

This lets you control how properties behave. ([MDN Web Docs][2])

---

## 🧠 Comparing Objects

Objects are **reference types**. Even if two objects have the same content, they are *not equal* unless they reference the same instance:

```js
{} === {} // false
let x = {};
let y = x;
x === y // true
```

The first two objects are separate, the second example references the same object. ([MDN Web Docs][2])

---

## 🧾 Key Takeaways

| Concept            | What It Means                                   |
| ------------------ | ----------------------------------------------- |
| Object             | Collection of key-value pairs                   |
| Literal            | Easiest way to make an object                   |
| Constructor        | Template for many similar objects               |
| Prototype          | Shared behavior across instances                |
| Method             | A function inside an object                     |
| Getter/Setter      | Control property access                         |
| Reference equality | Objects only equal if they’re the *same* object |

