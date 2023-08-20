# Software Testing

Software testing is an essential part of any software development process. It involves verifying that a piece of software meets its requirements and functions correctly. There are various methods of software testing, such as unit testing, integration testing, and end-to-end testing.

There are also different design methodologies such as Test Driven Development (TDD), Test After Development (TAD). Each of these methodologies has its own advantages and disadvantages, and can be used to ensure quality in any software product.

## Test Driven Development
Test Driven Development (TDD) is a process where tests are written before the code is written. This approach helps to ensure that the code meets the requirements as the tests act as a roadmap for development. Additionally, TDD encourages efficient coding as developers are only writing code for the tests that have been written.

[Steps to follow TDD ](https://www.hexacta.com/test-driven-development-vs-test-after-testing/)
1. Write a list of user stories that describe what the application should do. These user stories should be non-technical (the type of thing that a customer would write).
2. Pick a user story and express the user story in a unit test.
3. Write just enough code to pass the unit test. In other words, do the simplest thing that could possibly work to pass the unit test.
4. Consider refactoring your code to improve the design of your application. You can fearlessly refactor because your code is covered by unit tests.
5. Repeat steps 2 – 3 until you have completed the application (keeping in mind that the user stories might change over the course of the process of writing the application).

#### TDD Pros:
- Acts as a roadmap for development
- Encourages efficient coding
- Helps to ensure the code meets the requirements

#### TDD Cons:
- Can be time-consuming
- May lead to over-engineering

## Test After Development
Test After Development (TAD) is the opposite of TDD. In this method, tests are written after the code has been written. With TAD, it is easier to make sure the code meets the requirements as developers can make adjustments to the code based on the results of the tests. However, with TAD it is harder to ensure that the code is efficient as developers may be tempted to add code that is not needed.

[Steps to follow TAD ](https://www.hexacta.com/test-driven-development-vs-test-after-testing/)
1. Create a list of user stories.
2. Consider the best design for the application.
3. Write application code that follows the design.
4. Write unit tests for the code.
5. Repeat steps 2 – 4 until the application is completed.

#### TAD Pros:
- Easier to make sure the code meets the requirements
- Faster than TDD

#### TAD Cons:
- Harder to ensure the code is efficient
- May lead to unnecessary code

### Behavioral Driven Development
Behavior Driven Development (BDD) is a software development process that focuses on the behavior of the system rather than the implementation. BDD uses natural language to define and describe behaviors, allowing for a more collaborative and communicative process between developers, testers, and stakeholders.

- BDD encourages tests to be written before the code, helping to ensure the code meets the user's needs.
- BDD encourages unit testing, integration testing, and end-to-end testing to ensure that the code is meeting the user's needs.
- BDD helps to reduce the chances of errors, as the team can quickly identify and fix any issues before they become a problem.
- In a TDD approach, a developer might write a test to check if a certain piece of code is working correctly. In a BDD approach, the same developer might instead use natural language to describe how the user should interact with the system and what the expected outcome should be.


## Functional testing
- Unit testing: testing individual parts of the code to make sure they are functioning correctly.
- Integration testing: testing how different parts of the code interact with each other.
- End-to-end testing: testing the whole application, from start to finish, to make sure it meets the requirements.

## Testing in CI/CD
- Testing is a key component of a CI/CD pipeline, as it helps to ensure the quality of the software.
- Testing helps to identify bugs and other issues early on in the development process, reducing the cost of fixing them in the future.
- Testing should be done at multiple stages of the CI/CD process, from unit testing to integration testing to end-to-end testing.
- Testing can also be automated, allowing for faster feedback and a more efficient development process.

## Testing frameworks
Testing frameworks are essential tools for software testing. They provide a set of tools that allow developers to quickly and easily write and run tests. Testing frameworks also provide features such as asynchronous testing, snapshot testing, and browser testing, which allow developers to ensure the highest quality of software. Testing frameworks are used in all stages of software development, from unit testing to integration testing to end-to-end testing.

[Jest](https://jestjs.io/) is one of the most popular test frameworks for JavaScript and TypeScript. It is well-suited for both unit and integration testing. It is easy to set up and provides features such as mocking, code coverage, and reporting. Additionally, it is highly configurable and allows for customization.

## Further material
- [TDD](https://youtu.be/Jv2uxzhPFl4)
- [Types of tests](https://youtu.be/4-_0aTlkqK0)
- [One take on unit tests](https://youtu.be/ZGKGb109-I4)
- [API testing](https://www.sisense.com/blog/rest-api-testing-strategy-what-exactly-should-you-test/)

---

# Unit testing with [Jest](https://jestjs.io/)
Unit testing in TypeScript involves the process of testing individual units or components of your code to ensure that they behave as expected. In TypeScript, just like in JavaScript, you can use various testing frameworks and libraries to write and run unit tests. One of the most popular testing frameworks is Jest. Here's a general overview of how you can perform unit testing in TypeScript using Jest:

### Step 1: Setting Up Your Project

1. Install Jest and necessary dependencies:
   ```bash
   npm install jest ts-jest @types/jest --save-dev
   ```

2. Configure Jest in your `package.json`:
   ```json
   {
     "scripts": {
       "test": "jest"
     }
   }
   ```

### Step 2: Writing Tests

Create a test file (e.g., `example.test.ts`) for your TypeScript file (e.g., `example.ts`) you want to test.

```ts
// example.ts
function add(a: number, b: number): number {
  return a + b;
}

export { add };
```

```ts
// example.test.ts
import { add } from './example';

test('add function should correctly add two numbers', () => {
  expect(add(2, 3)).toBe(5);
});
```

### Step 3: Running Tests

Run your tests using the following command:

```bash
npm test
```

Jest will execute the tests and display the results in the terminal.

## Additional Considerations:

1. **[Mocking Dependencies](https://jestjs.io/docs/manual-mocks):** In unit testing, you might need to isolate the code under test from its dependencies. Jest provides mocking capabilities to help you control the behavior of dependencies.

2. **[Asynchronous Testing](https://jestjs.io/docs/asynchronous):** If your code involves asynchronous operations (like Promises or callbacks), Jest provides mechanisms to handle async testing.

3. **[Matchers](https://jestjs.io/docs/using-matchers):** Jest comes with a variety of built-in matchers (like `.toBe()`, `.toEqual()`, etc.) that help you write expressive assertions.

4. **Testing Frameworks:** Besides Jest, other popular testing frameworks for TypeScript include Mocha and Jasmine.

5. **Coverage Reporting:** You can also configure Jest to generate code coverage reports, helping you identify areas of your codebase that lack testing coverage.
