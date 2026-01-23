

## 🧠 **1. What is an Iterator?**

An **iterator** is a JavaScript object that **knows how to step through a sequence of values one at a time**.

An iterator object has a method called `next()`, and each time you call `next()` it returns an object like:

```js
{ value: ..., done: false }
```

* `value` is the next item in the sequence
* `done` becomes `true` when the sequence is finished ([MDN Web Docs][2])

### Example of a simple manual iterator

```js
function makeIterator(arr) {
  let index = 0;
  return {
    next() {
      if (index < arr.length) {
        return { value: arr[index++], done: false };
      }
      return { value: undefined, done: true };
    }
  };
}

const iter = makeIterator([10, 20, 30]);
console.log(iter.next()); // { value: 10, done: false }
console.log(iter.next()); // { value: 20, done: false }
console.log(iter.next()); // { value: 30, done: false }
console.log(iter.next()); // { value: undefined, done: true }
```

👉 This pattern lets you *control iteration manually*. ([MDN Web Docs][2])

---

## 🕶️ **2. What is an Iterable?**

An **iterable** is any object that you can loop over with a `for...of` loop or spread syntax (`[...]`).

For an object to be iterable, it **must have a special method named `[Symbol.iterator]()`** that returns an **iterator**. ([MDN Web Docs][1])

✔ Built-in iterables: `Array`, `String`, `Map`, `Set`, `TypedArray`
❌ Normal `{}` objects are *not* iterable by default. ([MDN Web Docs][1])

---

## 🚀 **3. Generator Functions — the Easy Iterator**

JavaScript has a special feature called **generator functions** that make writing iterators easy.

A generator function uses the `function*` syntax and `yield` expressions:

```js
function* genNumbers() {
  yield 1;
  yield 2;
  yield 3;
}
```

Calling this function doesn’t run it — it returns a **Generator object**, which is an iterator:

```js
const sequence = genNumbers();
console.log(sequence.next()); // { value: 1, done: false }
console.log(sequence.next()); // { value: 2, done: false }
console.log(sequence.next()); // { value: 3, done: false }
console.log(sequence.next()); // { value: undefined, done: true }
```

Each `yield` pauses the function and returns a value. The next `next()` call resumes where it left off. ([MDN Web Docs][1])

---

## ➿ **4. Iterating with `for...of`**

Generator objects and any iterable can be used in a `for...of` loop:

```js
for (const num of genNumbers()) {
  console.log(num);
}
// 1
// 2
// 3
```

This works because `for...of` automatically calls the iterator’s `.next()` repeatedly until `done` is true. ([MDN Web Docs][1])

---

## 🧩 **5. Custom Iterables**

You can make *any object* iterable by defining `[Symbol.iterator]()` — either directly or using a generator inside the object:

```js
const myIterable = {
  *[Symbol.iterator]() {
    yield "a";
    yield "b";
    yield "c";
  }
};

console.log([...myIterable]); // ["a", "b", "c"]
```

👉 This allows `for...of`, spread (`[...]`), destructuring, etc. ([MDN Web Docs][1])

---

## ⚙ **6. Advanced Generator Features**

### 🔁 Infinite or lazy sequences

Generators compute values *on demand*, not all at once — making them great for big/infinite sequences:

```js
function* countUp() {
  let i = 1;
  while (true) {
    yield i++;
  }
}
```

You can stop whenever you want and the generator keeps its state. ([MDN Web Docs][1])

---

### 🔄 Passing values into a generator

You can pass values *into* a generator when you call `next()`:

```js
function* ask() {
  const answer = yield "Question?";
  console.log(answer); // gets the value passed in
}

const q = ask();
console.log(q.next().value);       // "Question?"
q.next("42!");                     // logs "42!"
```

👉 The first value passed in is ignored, but subsequent ones are received by `yield`. ([MDN Web Docs][1])

---

### 🔥 Throwing & returning from a generator

Generators also expose:

* `.throw(error)` — makes the generator behave like a `throw` happened at the last `yield`
* `.return(value)` — immediately end the generator and set the return value

These let you control generator execution like an exception or early return. ([MDN Web Docs][3])

---

## 🧠 Quick Concept Map

| Term                   | What it Means                                            |
| ---------------------- | -------------------------------------------------------- |
| **Iterable**           | Something you can loop over (`for...of`, spread)         |
| **Iterator**           | Object with `.next()` returning `{value, done}`          |
| **Generator function** | Easy way to make iterators using `yield`                 |
| **Generator object**   | The iterator returned when you call a generator function |

---

## 🧾 Why This Matters

Iterators and generators:

* Let you walk through sequences lazily, one value at a time
* Are used by many built-in features (`for...of`, spread, destructuring)
* Can model infinite sequences or streams of data
* Make custom iteration logic easier to write ([MDN Web Docs][1])


