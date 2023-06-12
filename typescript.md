![Mr. TypeScript](images/typescript.jpg)

---

## Type Safety
Type safety is an important feature of full stack development. It helps us write better code by ensuring that the data types of variables and functions are correctly specified and used throughout the code. This helps to catch errors early in the development process and makes debugging easier. Type safety also helps to maintain the quality of the code and avoid unexpected issues further down the line.

- Type safety ensures that the code we are writing is correct and error-free.
- It ensures that the data types of variables and functions are correctly specified and that they are correctly used throughout the code.
- Type safety helps catch errors early in the development process and makes debugging easier.
- Type safety also helps to maintain the overall quality of the code and helps to avoid unexpected issues further down the line.

Example without type safety:
```javascript
// Define a variable without specifying its type
let age = 25;

// Assigning a value of the wrong type will not produce an error
age = "30"; // No error is thrown

// Define a function without specifying parameter types or a return type
function addNumbers(a, b) {
  return a + b;
}

// Invoking the function with arguments of the wrong type will not produce an error
const result = addNumbers(10, "20"); // No error is thrown

// Without type safety, the code allows assigning values of different types to variables
// and invoking functions with arguments of any type, which may lead to unexpected behavior or errors during runtime.

```

Example with type safety:
```typescript
// Define a variable with a specific type
let age: number = 25;

// Attempting to assign a value of the wrong type will result in a compilation error
age = "30"; // This line will produce a compilation error

// Define a function with specific parameter types and a return type
function addNumbers(a: number, b: number): number {
  return a + b;
}

// Invoking the function with arguments of the wrong type will result in a compilation error
const result = addNumbers(10, "20"); // This line will produce a compilation error

// TypeScript's type safety ensures that variables and functions are used correctly,
// helping to catch errors during development and improve code quality.

```

---

# TypeScript
- is a superset of JavaScript that adds optional static typing.
- comes in three parts: programming language, language server, and compiler.
- can catch errors such as incomplete refactoring, missing values, and internal contracts within the code base.
- can increase productivity and help developers catch errors early on.
- provides support for popular JavaScript libraries and frameworks such as React and Node.js.
- can be used to write code that runs both on the client and server sides.
- was created by Microsoft in 2012 as an open-source language.

#### Some terminology
- **[Static Typing](https://www.typescriptlang.org/docs/handbook/typescript-from-scratch.html#typescript-a-static-type-checker)**: TypeScript adds optional static typing to JavaScript, which enables developers to write code that is more maintainable and easier to debug.
- **[Compiler](https://www.typescriptlang.org/download)**: TypeScript uses a compiler to compile the TypeScript code into JavaScript code.
- **[TypeScript Declaration Files](https://www.typescriptlang.org/docs/handbook/2/type-declarations.html)**: TypeScript Declaration Files provide type information for external JavaScript libraries and can be used to enable type safety for these libraries.

## Getting Started
- [TypeScript handbook](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html#defining-types)
- [TypeScript website](https://www.typescriptlang.org/)
- [Documentation](https://www.typescriptlang.org/docs/)
- [Beginner's TypeScript](https://www.totaltypescript.com/tutorials/beginners-typescript)

---
