# TypeScript: Primitive Types and Type System Refinement

## Primitive Types

TypeScript is a statically typed superset of JavaScript that provides enhanced type checking and compilation-time error
detection.

Primitive types in TypeScript represent the basic building blocks for variables and data.

1. **Number:**
    - Represents both integer and floating-point numbers.
    - Supports mathematical operations like addition, subtraction, multiplication, and division.
   ```typescript
   let age: number = 25;
   
   let price: number = 9.99;
   
   const total = age * price;
   console.log('Total cost: $' + total.toFixed(2));
   ```

2. **String:**
    - Represents a sequence of characters enclosed in single ('') or double ("") quotes.
    - Supports various string manipulation methods and template literals for easy string interpolation.
   ```typescript
   let greeting: string = 'Hello, TypeScript!';
   let name: string = 'Alice';
   
   console.log(greeting + ' My name is ' + name);
   ```

3. **Boolean:**
    - Represents a logical value that can be either `true` or `false`.
    - Used for making decisions and controlling program flow through conditional statements.
   ```typescript
   let isStudent: boolean = true;
   let hasJob: boolean = false;
   
   if (isStudent && !hasJob) {
    console.log('You are a student without a job.');
   } else {
    console.log('You are either not a student or have a job.');
   }
   ```

4. **Null and Undefined:**
    - `null` represents the intentional absence of any value.
    - `undefined` is the default value of uninitialized variables.
   ```typescript
   let nullableValue: string | null = null;
   let undefinedValue: undefined = undefined;
   
   console.log(nullableValue);    // Outputs: null
   console.log(undefinedValue);   // Outputs: undefined
   ```
5. **Symbol:**
    - Represents a unique and immutable value, often used as object property keys.
    - Useful for preventing unintended name collisions in objects.
   ```typescript
   const idSymbol = Symbol('id');
   const user = {
       name: 'John',
       [idSymbol]: 123
   };
   
   console.log(user[idSymbol]);   // Outputs: 123
   ```

6. **BigInt:**
    - Represents arbitrary precision integers that can be larger than the `Number` type can handle.
    - Useful for scenarios requiring large integer calculations, like cryptography or high-precision arithmetic.
   ```typescript
   const bigValue: bigint = 123456789012345678901234567890123456n;
   
   console.log(bigValue * 2n);    // Outputs: 246913578024691357802469135780246912n
   ```

## Type Aliases and Interfaces

- **Custom Type Aliases:**
    - Type Aliases allow defining types with a custom name (an Alias).
    - They enhance code readability by providing descriptive names for data structures.

    ```typescript
    // Custom Type Alias for User
    type User = {
        id: number;
        username: string;
        email: string;
        isAdmin: boolean;
    };
    
    // Using the Custom Type Alias
    const currentUser: User = {
        id: 1,
        username: 'john_doe',
        email: 'john@example.com',
        isAdmin: false,
    };
    ```

- **Interfaces for Object Shapes:**
    - Interfaces are used to define the structure and shape of objects in TypeScript.
    - They establish contracts and ensure that objects adhere to a specific structure.

    ```typescript
    // Interface for Object Shape
    interface UserProfile {
        id: number;
        username: string;
        email: string;
    }
    
    // Using the Interface
    const user: UserProfile = {
        id: 1,
        username: 'alice',
        email: 'alice@example.com',
    };
    ```

- **Extending Interfaces:**
    - Interfaces can extend other interfaces, inheriting their properties and methods.
    - This promotes code reusability and supports a modular approach to defining types.

    ```typescript
    // Extending Interfaces
    interface Person {
        name: string;
    }
    
    interface Employee extends Person {
        employeeId: number;
    }
    
    const employee: Employee = {
        name: 'Bob',
        employeeId: 123,
    };
    ```

- **Using Type Aliases and Interfaces Together:**
    - Type aliases and interfaces can be used in conjunction to create powerful and descriptive types.

    ```typescript
    // Using Type Aliases and Interfaces Together
    type Status = 'active' | 'inactive' | 'pending';
    
    interface Task {
        id: number;
        title: string;
        status: Status;
    }
    
    const task: Task = {
        id: 1,
        title: 'Finish TypeScript Guide',
        status: 'pending',
    };
    ```

- **Benefits of Abstraction:**
    - Both type aliases and interfaces promote abstraction and encapsulation, enhancing code organization and
      maintainability.
    - Abstraction allows you to focus on the high-level structure of your code without getting bogged down in
      implementation details.

- **Choosing the Right Approach:**
    - [Types vs Interfaces](https://www.typescriptlang.org/play#example/types-vs-interfaces)
    - Consider your specific use case and design goals when deciding between type aliases and interfaces.
    - Strive for consistency in your codebase, using the approach that best fits the context and contributes to code
      quality.

## Function Type Annotations

1. **Explaining the Syntax for Specifying Parameter Types and Return Type Using Type Annotations:**
    - TypeScript allows you to annotate function parameters and return types using the colon `:` followed by the desired type.
    - The syntax for function type annotations is: `(parameter: type, parameter: type): return_type`.
    - You can use primitive types like `number`, `string`, `boolean`, custom types, or even union types in annotations.

2. **Benefits of Using Type Annotations for Functions:**
    - **Type Safety:** Type annotations catch type-related errors during development, helping you avoid unexpected runtime errors.
    - **Readability:** Annotations make code more readable by clearly indicating what types of values a function expects and returns.
    - **Documentation:** Annotations serve as documentation, providing a clear understanding of the function's contract.
    - **Intellisense:** Integrated development environments can provide better code suggestions and autocompletion based on type annotations.

3. **Examples of Functions with Type Annotations:**
   ```typescript
   // Function with type annotations
   function addNumbers(a: number, b: number): number {
     return a + b;
   }
   
   // Function with complex parameter types and return type
   function formatUser(name: string, age: number): { name: string; age: number } {
     return { name, age };
   }
   
   // Function with optional and default parameters
   function greetUser(name: string, greeting: string = "Hello"): string {
     return `${greeting}, ${name}!`;
   }
   ```

## Advanced Type System Features

1. **Type Inference:**
    - TypeScript employs type inference to automatically determine the type of variable based on its assigned value.
    - Reduces the need for explicit type annotations, making code more concise and readable.
   ```typescript
   let inferenceExample = 42; // TypeScript infers type number
   inferenceExample = 'oops'; // Error: Type 'string' is not assignable to type 'number'
   ```
2. **Type Annotations:**
    - Developers can explicitly define types using type annotations (e.g., `let age: number = 30;`).
    - Provides better documentation and helps catch type-related errors early.
   ```typescript
   let itemCount: number;
   itemCount = 10;
   
   console.log('Number of items: ' + itemCount);
   ```

3. **Type Compatibility:**
    - TypeScript performs type compatibility checks to ensure that variables assigned to different types are compatible
      based on their structure.
   ```typescript
   let value: number | string;
   value = 42;
   
   console.log('Value is: ' + value.toFixed(2)); // Works, value is treated as number
   
   value = 'hello';
   
   console.log('Value is: ' + value.toFixed(2)); // Error, value is treated as string
   ```

4. **Type Narrowing:**
    - TypeScript narrows down the type of variable within conditional statements using type guards (
      e.g., `typeof`, `instanceof`, custom user-defined guards).
   ```typescript
   // Get img element from the HTML
   const myImage = document.querySelector('img') as HTMLImageElement | null;
   
   // check that image element exists e.g. myImage is truthy hence not null
   if (myImage) {
      mySelect.addEventListener('click', () => {
         // do something
      });
   }
   ```
    - This prevents the use of the non-null assertion operator `(!)` when dealing with potentially nullable or undefined
      values in TypeScript.
   ```typescript
   // Get img element from the HTML
   const myImage = document.querySelector('img') as HTMLImageElement | null;
   
   // Warning: Ensure that myImage is not null before using the non-null assertion operator (!)
   mySelect!.addEventListener('click', () => {
      // do something
   });
   ```
    - Exercise caution when employing the non-null assertion operator, ensuring the variable is guaranteed to be
      non-null at the point of usage to prevent potential runtime errors.

5. **Type Literals:**
    - Type literals in TypeScript allow you to define exact values with specific types. They are particularly useful
      when you want to create a union type of literal values. One common use case is to create a set of allowed values
      for a particular property or parameter.
    - Here's an example of using a type literal to define a `Direction` type with specific literal values:
   ```typescript
   type Direction = 'north' | 'south' | 'east' | 'west';
   let heading: Direction = 'north';
   
   console.log('Heading: ' + heading);
   ```
6. **Generics**

    - Generics in TypeScript allow you to create flexible and reusable components that work with various data types while preserving type safety.
    - You can create functions that operate on different types by using type parameters.
    ```typescript
    function identity<T>(value: T): T {
        return value;
    }
    
    const result = identity(42); // Inferred type: number
    const message = identity("Hello"); // Inferred type: string
    ```
    
# Assignments

### Assignment 1: Calculating Total Cost

Write a TypeScript program that calculates the total cost of a shopping cart. The cart contains items with their prices.
Use the `number` primitive type for prices and quantities. Start by creating the interface first.

```TypeScript
// TODO: Write interface Item
// TODO: Define the properties 'name', 'price', and 'quantity' within the interface

// Create an empty array named 'cart' to store the items
const cart: Item[] = [];

// TODO: Implement a loop to prompt the user for item details
// Use 'while' loop to keep prompting until an empty item name is entered
while (true) {
  // TODO: Prompt user for item name, price, and quantity
  const itemName = /* TODO: Get user input */;
  
  // Break the loop if an empty item name is entered
  if (itemName === "") {
    break;
  }
  
  const itemPrice = /* TODO: Get user input */;
  const itemQuantity = /* TODO: Get user input */;
  
  // Create an item object and add it to the 'cart' array
  const newItem: Item = { name: itemName, price: itemPrice, quantity: itemQuantity };
  cart.push(newItem);
}

// Calculate the total cost using the 'map' and 'reduce' functions
const totalCost = cart.map(item => item.price * item.quantity).reduce((sum, cost) => sum + cost, 0);

// Display the total cost to the user
console.log(`Total cost of the shopping cart: $${totalCost.toFixed(2)}`);

```

### Assignment 2: Managing Null and Undefined

Develop a function that takes a number and returns the square root. Handle cases where the input is negative or
undefined. Use the `number`, `null`, and `undefined` primitive types.

```TypeScript
// TODO: Implement the squareRoot function
// parameter num should be a number or null or undefined and the function shoud return a number or a string
function squareRoot(num) {
  // TODO: Check if the input is undefined or null. If fail, return 'Input is undefined or null.'
    
  // TODO: Check if the input is a valid number. If fail, return 'Invalid input. Please enter a valid number.'
    
  // TODO: Handle cases where the input is negative. If fail, return 'Cannot calculate square root of a negative number.'
 
  // Calculate the square root and return the result
  const sqrt = Math.sqrt(num);
  return sqrt;
}

// Prompt the user to enter a number
const userInput = /* TODO: Get user input */;

// Convert user input to a number or keep it undefined if empty
// TODO: replce x and y with proper types
const numberInput: x | y = userInput ? parseFloat(userInput) : undefined;

// Call the squareRoot function and display the result
const result = squareRoot(numberInput);
console.log(result);
```

### Assignment 3: Defining Custom Types

Create a type alias for a book with properties like title, author, and publication year. Define an object using this
type alias and print its details.

1. Define a type alias named `Book` with properties `title`, `author`, and `publicationYear`, each having appropriate
   primitive types.
2. Prompt the user to enter details for a book (title, author, publication year) and create an object of type `Book`
   with the entered values.
3. Display the details of the book object to the user.

```typescript
export {}; // hack to ignore Book from task 4  
// TODO: Define a type alias named 'Book' with appropriate properties


// TODO: Implement the promptForBook function
function promptForBook() {
  // TODO: Prompt user for book details (title, author, publication year)
  const bookTitle = /* TODO: Get user input for title */;
  const bookAuthor = /* TODO: Get user input for author */;
  const bookPublicationYear = /* TODO: Get user input for publication year */;

  // TODO: Create an object of type 'Book' with the entered values
  const book: Book = /* TODO: Create the Book object */;
  return book;
}

// TODO: Call the promptForBook function to get the book details
const bookDetails = promptForBook();

// TODO: Display the details of the book object to the user
console.log("Book Details:");
console.log(`Title: ${bookDetails.title}`);
console.log(`Author: ${bookDetails.author}`);
console.log(`Publication Year: ${bookDetails.publicationYear}`);

```

### Assignment 4: Combinations of Types

Define a type alias for a product that can be either an electronic device with brand and model or a book with title and
author. Create instances of this type alias for different products.

1. Define a type alias named `Product` that can represent either an `ElectronicDevice` or a `Book`.
2. Implement instances of the `Product` type for a sample electronic device and a book, prompting the user for details.
3. Display the details of each product, including the properties specific to the chosen type.

```TypeScript
export {}; // hack to ignore Book from task 3
// TODO Define the 'ElectronicDevice' interface (or type)

// Define the 'Book' interface (or type)

// Define the 'Product' type alias that can represent either 'ElectronicDevice' or 'Book'


// Implement instances of the 'Product' type
function createElectronicDevice(): ElectronicDevice {
  // TODO: Prompt user for electronic device details (brand and model)
  const brand = /* TODO: Get user input for brand */;
  const model = /* TODO: Get user input for model */;
  // TODO: return object containing brand and model
}

function createBook(): Book {
  // TODO: Prompt user for book details (title and author)
  const title = /* TODO: Get user input for title */;
  const author = /* TODO: Get user input for author */;
  // TODO: return object containing title and author
}

// Create instances of 'Product'
const electronicProduct = createElectronicDevice();
const bookProduct = createBook();

// Display the details of each product
function displayProductDetails(product: Product) {
  console.log(`Product Type: ${product.type}`);
  if (product.type === 'electronic') {
    console.log(`Brand: ${product.brand}`);
    console.log(`Model: ${product.model}`);
  } else {
    console.log(`Title: ${product.title}`);
    console.log(`Author: ${product.author}`);
  }
}

console.log('Electronic Device Details:');
displayProductDetails(electronicProduct);

console.log();

console.log('Book Details:');
displayProductDetails(bookProduct);
```

### Assignment 5: Union Types + Type Guard

Write a function that takes a string or number and returns its length if it's a string or the square of the number if
it's a number. Use union types to handle both cases.

1. Prompt the user to enter a value as either a string or a number.
2. Define a TypeScript function that takes a parameter of type `string | number`.
3. Use a type guard to check the actual type of the parameter.
4. If the parameter is a string, display its length. If it's a number, display its square.

```typescript
// TODO: Implement the lengthOrSquare function
// define the type(s) for 'value'
function lengthOrSquare(value) {
    // TODO: Use a type guard to check the actual type of 'value'
    // if type is string, retrurn the length of the string
    // if type is number return the square of the number
}

// Prompt the user to enter a value as either a string or a number
const userInput = /* TODO: Get user input */;
const parsedValue = /* TODO: If userInput is numeric, convert it to number else keep it as string */;

// Call the lengthOrSquare function
const result = lengthOrSquare(parsedValue);
console.log(typeof result);
console.log(result);

```

### Assignment 6: Generics

Write a generic function that reverses the elements of an array. Test the function with arrays of numbers, strings, and
other types.

1. Create a TypeScript function named `reverseArray` that takes an array as a parameter with a generic type
   parameter `T`.
2. Inside the function, reverse the elements of the array using a loop or the `reverse` method.
3. Return the reversed array.
4. Call the `reverseArray` function for each array type and display the reversed arrays.

```typescript

// Test the function with arrays of different types
const numberArray: number[] = [1, 2, 3, 4, 5];
const stringArray: string[] = ["apple", "banana", "cherry", "date"];
const mixedArray: (string | number | boolean)[] = [true, 42, "hello", false];

// Use console log to print the result. Desired result:
// Reversed Array of Numbers: [ 5, 4, 3, 2, 1 ]
// Reversed Array of Strings: [ 'date', 'cherry', 'banana', 'apple' ]
// Reversed Mixed Array: [ false, 'hello', 42, true ]

```
