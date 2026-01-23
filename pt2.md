## JavaScript Basics — Summary

**Syntax & structure**

* JavaScript’s syntax is similar to Java, C, and C++, but it’s influenced by scripting languages like Python and Perl.
* It is **case-sensitive** (`Früh` and `früh` are different).
* Code is written as **statements**, usually ended with semicolons (`;`). Semicolons are optional but recommended.
* JavaScript code is read left-to-right; whitespace and comments are ignored during execution.

**Comments**

* Single-line: `// comment`
* Multi-line: `/* comment */`
* Block comments cannot be nested.
* Special “hashbang” comments (`#!`) may appear at the top of some files.

---

## Variables & Declarations

* Three ways to declare variables:

  * `var` – function-scoped (older, less safe)
  * `let` – block-scoped (preferred)
  * `const` – block-scoped and cannot be reassigned
* Variables must be declared before use.
* `const` variables must be initialized and cannot be reassigned, but **objects and arrays declared with `const` can still be modified**.

**Scope**

* Variables can be global, module-scoped, function-scoped, or block-scoped.
* `let` and `const` respect block scope (`{}`).
* `var` ignores block scope and only respects function/global scope.

**Hoisting**

* `var` declarations are “hoisted” (moved to the top of their scope) and default to `undefined`.
* `let` and `const` are not usable before declaration (temporal dead zone).
* Function declarations are fully hoisted.

---

## Data Types

JavaScript has **8 data types**:

* **Primitives**: `Boolean`, `null`, `undefined`, `Number`, `BigInt`, `String`, `Symbol`
* **Object**

JavaScript is **dynamically typed**, so variables can change types during execution.

---

## Type Conversion

* The `+` operator concatenates strings if either operand is a string.
* Other operators (`-`, `*`, `/`) convert strings to numbers.
* Strings can be converted to numbers using:

  * `Number()`
  * `parseInt()` (use radix!)
  * `parseFloat()`
  * Unary `+`

---

## Literals (fixed values in code)

* **Array literals**: `[]`
* **Object literals**: `{}`
* **Boolean literals**: `true`, `false`
* **Numeric literals**: decimal, binary, octal, hex, BigInt
* **String literals**: `'text'`, `"text"`, or template literals `` `text` ``
* **RegExp literals**: `/pattern/`

**Arrays**

* Extra commas create empty slots.
* Trailing commas are allowed and help with clean version control diffs.

**Objects**

* Objects are key-value pairs.
* Property names can be strings or numbers.
* Invalid identifier names must be accessed using bracket notation (`obj["!"]`).
* Enhanced object literals support shorthand syntax, methods, and computed property names.

---

## Strings

* Strings can use escape characters (`\n`, `\t`, `\\`, etc.).
* Template literals (`` `...` ``) support:

  * Multi-line strings
  * Variable interpolation (`${value}`)
* Tagged templates allow custom processing of template strings.

---

## Big Picture

JavaScript is a **flexible, dynamically typed language** with simple syntax, powerful object and array handling, and built-in support for strings, numbers, and data structures. Its rules around scope, hoisting, and type conversion are important to understand to avoid bugs.
