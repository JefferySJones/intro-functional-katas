## Intro to functional katas
Pure functions: A pure function is a function that always returns the same output for the same input and doesn't modify any external state. Pure functions are easy to test and reason about, and they can be composed to build more complex behavior.
- A pure function is like a vending machine. You put in the same inputs (money and selection) and you always get the same output (snack). The vending machine doesn't change anything outside itself (like your wallet), and you don't have to worry about the vending machine stealing your money or giving you the wrong snack.

Immutability: In functional programming, data is often treated as immutable, which means that once a value is created, it cannot be changed. Instead, new values are created by applying functions to existing values. This makes it easier to reason about the behavior of a program and avoid unexpected side effects.
- Immutability is like a museum exhibit. Once a piece of art is placed in the exhibit, it can't be changed. Visitors can observe the art and appreciate its beauty, but they can't add to it or alter it in any way. Similarly, in functional programming, data is treated as a valuable artifact that should be preserved and protected from accidental changes.

These katas will help you to practice some of the basics of functional programming. It's good to keep "pure functions" and "immutability" in mind through these examples.

---
This project uses Tailwind and Nuxt3
---

## Setup
Make sure to install the dependencies:

```bash
npm install
```

## Development Server

Start the development server on `http://localhost:3000`

```bash
npm run dev
```
