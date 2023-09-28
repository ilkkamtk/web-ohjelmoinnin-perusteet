# Software Testing

Software testing is an essential part of any software development process. It involves verifying that a piece of
software meets its requirements and functions correctly. There are various methods of software testing, such as unit
testing, integration testing, and end-to-end testing.

There are also different design methodologies such as Test Driven Development (TDD), Test After Development (TAD). Each
of these methodologies has its own advantages and disadvantages, and can be used to ensure quality in any software
product.

## Test Driven Development

Test Driven Development (TDD) is a process where tests are written before the code is written. This approach helps to
ensure that the code meets the requirements as the tests act as a roadmap for development. Additionally, TDD encourages
efficient coding as developers are only writing code for the tests that have been written.

[Steps to follow TDD ](https://www.hexacta.com/test-driven-development-vs-test-after-testing/)

1. Write a list of user stories that describe what the application should do. These user stories should be
   non-technical (the type of thing that a customer would write).
2. Pick a user story and express the user story in a unit test.
3. Write just enough code to pass the unit test. In other words, do the simplest thing that could possibly work to pass
   the unit test.
4. Consider refactoring your code to improve the design of your application. You can fearlessly refactor because your
   code is covered by unit tests.
5. Repeat steps 2 – 3 until you have completed the application (keeping in mind that the user stories might change over
   the course of the process of writing the application).

#### TDD Pros:

- Acts as a roadmap for development
- Encourages efficient coding
- Helps to ensure the code meets the requirements

#### TDD Cons:

- Can be time-consuming
- May lead to over-engineering

## Test After Development

Test After Development (TAD) is the opposite of TDD. In this method, tests are written after the code has been written.
With TAD, it is easier to make sure the code meets the requirements as developers can make adjustments to the code based
on the results of the tests. However, with TAD it is harder to ensure that the code is efficient as developers may be
tempted to add code that is not needed.

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

Behavior Driven Development (BDD) is a software development process that focuses on the behavior of the system rather
than the implementation. BDD uses natural language to define and describe behaviors, allowing for a more collaborative
and communicative process between developers, testers, and stakeholders.

- BDD encourages tests to be written before the code, helping to ensure the code meets the user's needs.
- BDD encourages unit testing, integration testing, and end-to-end testing to ensure that the code is meeting the user's
  needs.
- BDD helps to reduce the chances of errors, as the team can quickly identify and fix any issues before they become a
  problem.
- In a TDD approach, a developer might write a test to check if a certain piece of code is working correctly. In a BDD
  approach, the same developer might instead use natural language to describe how the user should interact with the
  system and what the expected outcome should be.

## Functional testing

- Unit testing: testing individual parts of the code to make sure they are functioning correctly.
- Integration testing: testing how different parts of the code interact with each other.
- End-to-end testing: testing the whole application, from start to finish, to make sure it meets the requirements.

## Testing in CI/CD

- Testing is a key component of a CI/CD pipeline, as it helps to ensure the quality of the software.
- Testing helps to identify bugs and other issues early on in the development process, reducing the cost of fixing them
  in the future.
- Testing should be done at multiple stages of the CI/CD process, from unit testing to integration testing to end-to-end
  testing.
- Testing can also be automated, allowing for faster feedback and a more efficient development process.

## Testing frameworks

Testing frameworks are essential tools for software testing. They provide a set of tools that allow developers to
quickly and easily write and run tests. Testing frameworks also provide features such as asynchronous testing, snapshot
testing, and browser testing, which allow developers to ensure the highest quality of software. Testing frameworks are
used in all stages of software development, from unit testing to integration testing to end-to-end testing.

[Jest](https://jestjs.io/) is one of the most popular test frameworks for JavaScript and TypeScript. It is well-suited
for both unit and integration testing. It is easy to set up and provides features such as mocking, code coverage, and
reporting. Additionally, it is highly configurable and allows for customization.

## Further material

- [TDD](https://youtu.be/Jv2uxzhPFl4)
- [Types of tests](https://youtu.be/4-_0aTlkqK0)
- [One take on unit tests](https://youtu.be/ZGKGb109-I4)
- [API testing](https://www.sisense.com/blog/rest-api-testing-strategy-what-exactly-should-you-test/)

---

# Unit testing with [Vitest](https://vitest.dev/)

### Step 1: Setting Up Your Project

1. Install Vitest:
   ```bash
   npm i -D vitest
   ```

2. Configure Vitest in your `package.json`:
   ```json
   {
     "scripts": {
       "test": "vitest"
     }
   }
   ```

### Step 2: Writing Tests

Create a new Vite project and then add a test file (e.g., `test/example.test.ts`) for your TypeScript file (
e.g., `src/example.ts`) you want to test.

```ts
// example.ts
function add(a: number, b: number): number {
    return a + b;
}

export {add};
```

```ts
// example.test.ts
import {add} from './example';

test('add function should correctly add two numbers', () => {
    expect(add(2, 3)).toBe(5);
});
```

### Step 3: Running Tests

Run your tests using the following command:

```bash
npm test
```

Vitest will execute the tests and display the results in the terminal.

## test(), it() and describe()

In testing frameworks like Vitest `test`, `describe`, and `it` are used to structure and organize your test suites and
individual test cases. Here's when and how to use each of these:

1. **`test()`**:

    - **Usage**: `test(description, testFunction)`

    - **When to Use**:
        - `test` is used to define an individual test case, also known as a test assertion or test spec.
        - You use `test` to describe a single piece of functionality you want to test within your code.

    - **Example**:
      ```javascript
      test('Adds two numbers correctly', () => {
        expect(add(1, 2)).toBe(3);
      });
      ```

2. **`it()`**:
    - `it` is an alias for `test`. You can use either `it` or `test` based on your preference.
    - Some developers prefer `it` because it can make test descriptions read more like plain English sentences.

3. **`describe()`**:

    - **Usage**: `describe(description, testSuiteFunction)`

    - **When to Use**:
        - `describe` is used to group multiple related test cases or tests that pertain to a specific component,
          function, or feature.
        - You use `describe` to provide a context or categorization for a set of tests.

    - **Example**:
      ```javascript
      describe('Math Operations', () => {
        it('Adds two numbers correctly', () => {
          expect(add(1, 2)).toBe(3);
        });
 
        it('Subtracts two numbers correctly', () => {
          expect(subtract(5, 3)).toBe(2);
        });
      });
      ```


- Use `it` (or `teset`) for individual test cases or assertions.
- Use `describe` to group related tests and provide context.
- Use descriptive names for `describe`, `test`, and `it` to make your test suite more readable and maintainable.

## Additional Considerations:

1. [Mocking](https://vitest.dev/guide/mocking.html)

2. [Matchers](https://vitest.dev/api/expect.html): Vitest comes with a variety of built-in matchers (
   like `.toBe()`, `.toEqual()`, etc.) that help you write expressive assertions.

3. Testing Frameworks: Besides Vitest, other popular testing frameworks for TypeScript include Jest, Mocha and Jasmine.

4. Coverage Reporting: You can also configure Vitest to generate code coverage reports, helping you identify areas of
   your codebase that lack testing coverage by adding `vitest --coverage` flag to `package.json`.

---

## Exercises

### String Manipulation - Reverse

**Function to be Tested:**

```typescript
function reverseString(input: string): string {
    return input.split('').reverse().join('');
}
```

**Input Values and Expected Output:**

1. Test reversing a short string (e.g., "hello").
    - Input: `"hello"`
    - Expected Output: `"olleh"`

2. Test reversing a longer string with spaces and special characters (e.g., "Hello, World!").
    - Input: `"Hello, World!"`
    - Expected Output: `"!dlroW ,olleH"`

3. Test reversing an empty string.
    - Input: `""`
    - Expected Output: `""` (The input and output are both empty strings).

4. Test reversing a string with a single character.
    - Input: `"a"`
    - Expected Output: `"a"` (The input and output are both the character "a").

---

### Email Validation

**Function to be Tested:**

```typescript
function isValidEmail(email: string): boolean {
    // Regular expression for a basic email validation
    const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return emailPattern.test(email);
}
```

**Input Values and Expected Output:**

1. Test a valid email address with a typical format (e.g., "user@example.com").
    - Input: `"user@example.com"`
    - Expected Output: `true`

2. Test a valid email address with a subdomain (e.g., "user@sub.example.com").
    - Input: `"user@sub.example.com"`
    - Expected Output: `true`

3. Test an invalid email address with missing "@" (e.g., "userexample.com").
    - Input: `"userexample.com"`
    - Expected Output: `false`

4. Test an invalid email address with special characters (e.g., "user@exa!mple.com").
    - Input: `"user@exa!mple.com"`
    - Expected Output: `false`

5. Test an invalid email address with a missing top-level domain (e.g., "user@example").
    - Input: `"user@example"`
    - Expected Output: `false`

---

### Fibonacci Sequence

**Function to be Tested:**

```typescript
function fibonacci(n: number): number {
    if (n <= 0) return 0;
    if (n === 1) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}
```

**Input Values and Expected Output:**

1. Test the Fibonacci of 0.
    - Input: `fibonacci(0)`
    - Expected Output: `0`

2. Test the Fibonacci of 1.
    - Input: `fibonacci(1)`
    - Expected Output: `1`

3. Test the Fibonacci of 5.
    - Input: `fibonacci(5)`
    - Expected Output: `5`

4. Test the Fibonacci of a negative number (e.g., -1).
    - Input: `fibonacci(-1)`
    - Expected Output: `0`

___

### Matrix Multiplication

**Function to be Tested:**

```typescript
function multiplyMatrix(matrix1: number[][], matrix2: number[][]): number[][] {
    if (matrix1[0].length !== matrix2.length) {
        throw new Error('Invalid matrix dimensions for multiplication');
    }

    const result: number[][] = [];
    const rows1 = matrix1.length;
    const cols1 = matrix1[0].length;
    const cols2 = matrix2[0].length;

    for (let i = 0; i < rows1; i++) {
        result[i] = [];
        for (let j = 0; j < cols2; j++) {
            result[i][j] = 0;
            for (let k = 0; k < cols1; k++) {
                result[i][j] += matrix1[i][k] * matrix2[k][j];
            }
        }
    }

    return result;
}
```

**Input Values and Expected Output:**

1. Test matrix multiplication with a 2x2 matrix and a 2x2 matrix.
    - Matrix 1:
      ```
      [[1, 2],
       [3, 4]]
      ```
    - Matrix 2:
      ```
      [[5, 6],
       [7, 8]]
      ```
    - Expected Output:
      ```
      [[19, 22],
       [43, 50]]
      ```

2. Test matrix multiplication with a 2x3 matrix and a 3x2 matrix.
    - Matrix 1:
      ```
      [[1, 2, 3],
       [4, 5, 6]]
      ```
    - Matrix 2:
      ```
      [[7, 8],
       [9, 10],
       [11, 12]]
      ```
    - Expected Output:
      ```
      [[58, 64],
       [139, 154]]
      ```

3. Test matrix multiplication with a 1x1 matrix and a 1x1 matrix.
    - Matrix 1:
      ```
      [[3]]
      ```
    - Matrix 2:
      ```
      [[2]]
      ```
    - Expected Output:
      ```
      [[6]]
      ```

4. Test matrix multiplication with an invalid input (e.g., incompatible dimensions).
    - Matrix 1:
      ```
      [[1, 2],
       [3, 4]]
      ```
    - Matrix 2:
      ```
      [[5, 6, 7],
       [8, 9, 10]]
      ```
    - Expected Output: An error should be thrown with the message 'Invalid matrix dimensions for multiplication'.
