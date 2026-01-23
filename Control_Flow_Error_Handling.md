## JavaScript Control Flow & Error Handling — Summary

**Statements & blocks**

* JavaScript uses **statements** to control program flow.
* A **block statement** groups statements using `{}` and is commonly used with `if`, `while`, etc.
* Variables declared with `var` are **not block-scoped** (they leak outside blocks); `let` and `const` *are* block-scoped and preferred.

---

## Conditional Statements

### `if...else`

* Runs code when a condition is true; runs `else` when false.
* Conditions are expressions that evaluate to `true` or `false`.
* `else if` allows multiple conditions to be checked in order.
* Best practice: always use `{}` even for single statements.

**Falsy values** (evaluate to false):

* `false`, `undefined`, `null`, `0`, `NaN`, `""`
* Everything else (including objects) is truthy.

⚠️ Don’t confuse primitive booleans (`true`, `false`) with `Boolean` objects.

---

### `switch`

* Compares a value against multiple cases.
* Executes the matching case.
* `break` stops execution; without it, execution “falls through” to the next case.
* `default` runs if no case matches.

---

## Exception Handling (Errors)

### `throw`

* Used to manually raise an error.
* You can throw **any value**, but using `Error` objects is best practice.

---

### `try...catch...finally`

* `try`: code that might fail
* `catch`: runs if an error occurs
* `finally`: always runs (error or not), often used for cleanup

Key behaviors:

* If an error is thrown in `try`, execution jumps to `catch`.
* `finally` runs **even if**:

  * an error occurs
  * a return happens
* A `return` or `throw` in `finally` **overrides** earlier returns or throws.

---

## Nested & Advanced Error Handling

* `try...catch` blocks can be nested.
* Errors bubble outward until a matching `catch` is found.
* Use `Error` objects to get meaningful `name` and `message` properties.
* Prefer `console.error()` over `console.log()` for error logging.

---

## Big Picture

JavaScript control flow relies on **blocks, conditionals, and switches** to make decisions, and **try/catch/finally** to handle errors safely. Understanding scope, falsy values, and how errors propagate is key to writing predictable, bug-resistant code.

