![Mr. TypeScript](images/typescript.jpg)

---

## Type Safety
Type safety is an important feature of full stack development. It helps us write better code by ensuring that the data types of variables and functions are correctly specified and used throughout the code. This helps to catch errors early in the development process and makes debugging easier. Type safety also helps to maintain the quality of the code and avoid unexpected issues further down the line.

- Type safety in full stack development ensures that the code we are writing is correct and error-free.
- It ensures that the data types of variables and functions are correctly specified and that they are correctly used throughout the code.
- Type safety helps catch errors early in the development process and makes debugging easier.
- Type safety also helps to maintain the overall quality of the code and helps to avoid unexpected issues further down the line.

For example, a REST API may accept a string on the client side but reject it on the server side due to type safety issues. If the server expects a number but the client side sends a string, the API will reject the request. This could cause unexpected errors and unexpected behavior. To avoid this, proper type safety needs to be implemented on both the client and server sides.

- On the client side, ensure that requests are sent using the appropriate data type. For example, send data as JSON.
- On the server side, validate the data types of incoming requests and ensure that the data is in the correct format.
    - for example in a query string everything is a string
- On the server side, send a response with the appropriate data type. Again: JSON

One of the better alternatives to REST APIs when considering type safety is [GraphQL](https://graphql.org/). GraphQL is strongly typed and can provide more precise control over data types. It can also be used to validate data types on both the client and server sides, while in REST APIs, data validation must be handled on the server side. Additionally, GraphQL can provide the exact data required with no issues of overfetching or underfetching.

[tRPC](https://trpc.io/) is another alternative to REST APIs when considering type safety. tRPC is a type-safe RPC framework that allows services to communicate with each other over HTTP. It allows for the precise definition of data types, which helps to ensure that data is properly validated and that the correct data is exchanged between services. Additionally, tRPC supports multiple protocols, making it a flexible and powerful option for type-safe communication.

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
