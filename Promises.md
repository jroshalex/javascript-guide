

## 📌 What a **Promise** Is

A **Promise** is a built-in JavaScript object that represents the **future result** of an asynchronous operation — something that *will finish later*, either **successfully** or **with an error**. Unlike old callback patterns, you attach handlers to the promise itself rather than passing callbacks into functions. ([MDN Web Docs][1])

---

## 🔗 Promise **Chaining**

Instead of nested callbacks (“callback hell”), promises let you chain operations:

```js
doSomething()
  .then(result => doSomethingElse(result))
  .then(newResult => doThirdThing(newResult))
  .then(final => console.log(final))
  .catch(error => console.error(error));
```

Each `.then()` returns a new promise, so you can link multiple asynchronous steps in a flat, readable chain. ([MDN Web Docs][1])

---

## 📍 Attaching Handlers

* `.then(onFulfilled, onRejected)` — run when the promise settles
* `.catch(onRejected)` — same as `.then(null, onRejected)`
* `.then()` always returns a new promise, allowing chaining ([MDN Web Docs][1])

If a `.then()` callback returns a promise, the next step waits for that promise to finish before moving on. ([MDN Web Docs][1])

---

## 🛑 Error Handling

Putting `.catch()` at the end of a chain catches **any error** thrown anywhere in the chain, similar to a `try/catch` block in synchronous code. ([MDN Web Docs][1])

This makes asynchronous error handling much simpler than in old callback styles.

---

## 🧩 Composition Tools

JavaScript includes helper methods to handle **multiple promises at once**:

* `Promise.all([...])` → waits for all to resolve (rejects if any rejects).
* `Promise.allSettled([...])` → waits for all, regardless of success/failure.
* `Promise.any([...])` → resolves when any promise succeeds.
* `Promise.race([...])` → settles as soon as the first promise settles. ([MDN Web Docs][1])

---

## 🧱 Wrapping Old Callback APIs

You can create a promise yourself with the `Promise` constructor to wrap older callback APIs:

```js
function wait(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}
```

Then use it like:

```js
wait(1000).then(() => console.log("Done!"));
```

This converts callbacks into modern promise usage. ([MDN Web Docs][1])

---

## 🧠 Async/Await Works on Promises

The newer `async/await` syntax is just “syntax sugar” over promises: it lets you write promise-based code that looks synchronous, but it still uses promises under the hood. ([MDN Web Docs][1])

---

## 🔎 Handling Unhandled Rejections

If no `.catch()` handles a rejected promise, the browser or Node.js will emit a **rejection event** so you can log or respond to it (useful for debugging). ([MDN Web Docs][1])

---

## 🧠 Core Takeaways

✔ Promises represent future results (success or failure). ([MDN Web Docs][1])
✔ `.then()` chains operations and returns new promises. ([MDN Web Docs][1])
✔ `.catch()` handles errors for the whole chain. ([MDN Web Docs][1])
✔ You can run many promises together or in sequence. ([MDN Web Docs][1])
✔ Async/await builds on promises for cleaner syntax. ([MDN Web Docs][1])


