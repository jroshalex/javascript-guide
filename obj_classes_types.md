
1. **JS types (what values exist)**
2. **Objects (what they really are)**
3. **Classes (what they actually do in JS)**
4. **How all three fit together**
5. **Common mistakes + “aha” moments**


---

# 1️⃣ JavaScript Types (start here)

A **type** answers: *“What kind of value is this?”*

## 🔹 Primitive types (simple, atomic values)

These are **not objects**.

| Type        | Example            | Notes                       |
| ----------- | ------------------ | --------------------------- |
| `number`    | `5`, `3.14`, `NaN` | No separate int/float       |
| `string`    | `"hi"`             | Immutable                   |
| `boolean`   | `true`, `false`    |                             |
| `undefined` | `let x;`           | Variable declared, no value |
| `null`      | `null`             | Intentional “nothing”       |
| `symbol`    | `Symbol("id")`     | Unique identifiers          |
| `bigint`    | `123n`             | Very large integers         |

```js
let a = 10;
let b = a;
b = 20;

console.log(a); // 10
```

➡️ **Primitives are copied by value**


**JS is dynamically typed.**
But here are the *practical* ways to indicate or enforce types:

### 1️⃣ By assignment (implicit)

```js
let x = 5;        // number
let name = "Sam"; // string
```

### 2️⃣ Runtime checks

```js
if (typeof x === "number") { ... }
```

### 3️⃣ Instance checks (objects/classes)

```js
if (user instanceof Person) { ... }
```

### 4️⃣ JSDoc (type hints, no enforcement)

```js
/** @type {number} */
let count;
```

### 5️⃣ TypeScript (actual types)

```ts
let age: number = 21;
```

👉 **Plain JS doesn’t enforce types; TypeScript does.**


---

## 🔹 Objects (reference types)

Everything else is an **object**:

* Objects
* Arrays
* Functions
* Dates
* Classes (yes)

```js
let obj1 = { x: 10 };
let obj2 = obj1;

obj2.x = 20;
console.log(obj1.x); // 20
```

➡️ **Objects are copied by reference**

**This single rule explains 50% of JS confusion.**

---

## 🔎 `typeof` weirdness (important)

```js
typeof 42           // "number"
typeof "hi"         // "string"
typeof null         // "object" ❌ (JS bug from 1995)
typeof []           // "object"
typeof function(){} // "function"
```

👉 Arrays and functions are **special kinds of objects**.

---

# 2️⃣ Objects (the heart of JS)

An **object** is:

> A collection of **key → value pairs**

```js
const user = {
  name: "Sam",
  age: 21,
  greet() {
    return "Hello";
  }
};
```

Keys are strings (or symbols), even if they don’t look like it.

```js
user["name"] === user.name; // true
```

---

## 🔹 Objects have identity

```js
{} === {} // false
```

Even if they look the same, they are **different objects in memory**.

---

## 🔹 Methods & `this`

```js
const dog = {
  name: "Rex",
  bark() {
    console.log(this.name);
  }
};

dog.bark(); // Rex
```

**`this` = the object that calls the function**

🚨 NOT where the function is defined — where it’s called.

```js
const bark = dog.bark;
bark(); // undefined (or error)
```

---

## 🔹 Adding & removing properties

```js
dog.age = 3;
delete dog.age;
```

Objects are **dynamic** — structure can change at runtime.

---

# 3️⃣ Prototypes (the secret engine)

Every object has a **prototype** → another object it can inherit from.

```js
const animal = {
  eat() {
    console.log("eating");
  }
};

const cat = Object.create(animal);
cat.meow = () => console.log("meow");

cat.eat(); // works!
```

JS looks up properties like this:

1. On the object
2. On its prototype
3. On prototype’s prototype
4. Until `null`

This is the **prototype chain**.

---

# 4️⃣ Classes (not what you think)

⚠️ **JS classes are NOT like Java/C++ classes**

They are:

> **Syntax sugar over prototypes**

---

## 🔹 Class basics

```js
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    return `Hi, I'm ${this.name}`;
  }
}

const p = new Person("Alex");
console.log(p.greet());
```

What actually happens:

* `p` is an object
* `greet()` lives on `Person.prototype`
* `p.__proto__ === Person.prototype`

---

## 🔹 `new` keyword (very important)

```js
new Person("Alex")
```

Does 4 things:

1. Creates a new empty object
2. Sets its prototype
3. Binds `this`
4. Returns the object

---

## 🔹 Class vs object literal

```js
// Object literal (one-off)
const user = { name: "A" };

// Class (many similar objects)
const u1 = new User("A");
const u2 = new User("B");
```

Use classes when you want **many instances**.

---

## 🔹 Inheritance with classes

```js
class Animal {
  speak() {
    console.log("sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("bark");
  }
}

const d = new Dog();
d.speak(); // bark
```

Under the hood: **prototype chaining again**.

---

# 5️⃣ Functions are objects too (mind-blowing but true)

```js
function hello() {}
hello.x = 5;

console.log(hello.x); // 5
```

Functions can:

* Be called
* Have properties
* Be passed around

This is why JS is powerful (and confusing).

---

# 6️⃣ How types, objects, and classes connect

### 🔁 Mental model (IMPORTANT)

```
Value
 ├─ Primitive (number, string, etc.)
 └─ Object
     ├─ Plain object
     ├─ Array
     ├─ Function
     └─ Instance of a class
```

**Classes don’t create types.**
They create **patterns for objects**.

```js
typeof p; // "object"
```

Even if `p` came from a class.

---

# 7️⃣ Common confusion (and fixes)

### ❌ “Classes define types”

✅ **No — classes define object shapes**

---

### ❌ “Arrays are not objects”

✅ Arrays ARE objects with extra behavior

---

### ❌ “`this` refers to the class”

✅ `this` refers to the **caller**

---

### ❌ “Objects copy like primitives”

✅ Objects copy **by reference**

---

# 8️⃣ When to use what

### Use primitives when:

* You need simple data
* You want immutability

### Use objects when:

* Data has structure
* You need behavior + data

### Use classes when:

* You create many similar objects
* You want shared methods
* You want readable architecture

---

# 🧠 One-sentence summary (bookmark this)

> **JavaScript has primitive values and objects; objects inherit behavior through prototypes, and classes are just a cleaner way to create and link objects.**

---
