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
    
# Ecercises

## Primitive Types

### Exercise 1: Calculating Total Cost

Write a TypeScript program that calculates the total cost of a shopping cart. The cart contains items with their prices.
Use the `number` primitive type for prices and quantities.

1. Create an empty array named `cart` to store the items.
2. Use a loop to prompt the user for the name, price, and quantity of each item. Store these values as objects in
   the `cart` array.
3. When the user enters an empty value for the item name, proceed to calculate the total cost by iterating through
   the `cart` array and summing up the product of each item's price and quantity.
4. Display the total cost to the user.

### Exercise 2: String Manipulation

Create a function that takes a sentence as a string input and returns the sentence reversed. Use the `string` primitive
type for the input and output.

1. Prompt the user to enter a sentence as a string and store it in a variable.
2. Split the sentence into an array of words using the `split` method.
3. Use a loop to reverse the order of the words in the array.
4. Join the reversed array of words back into a sentence using the `join` method.
5. Display the reversed sentence to the user.

### Exercise 3: Logical Decisions

Write a program that determines if a given student is eligible for a discount based on their age and student status. Use
the `boolean` primitive type to represent eligibility and the `number` primitive type for age.

1. Prompt the user to enter their age as a number and their student status as a boolean.
2. Use conditional statements to check if the age is less than 18 or if the student status is `true`.
3. If either condition is met, display a message to the user indicating that they are eligible for a discount.
   Otherwise, inform them that they are not eligible.

### Exercise 4: Managing Null and Undefined

Develop a function that takes a number and returns the square root. Handle cases where the input is negative or
undefined. Use the `number`, `null`, and `undefined` primitive types.

1. Prompt the user to enter a number and store it in a variable.
2. Check if the entered value is a valid number.
3. If the value is a valid number, calculate the square root using the `Math.sqrt` function and display the result.
4. If the value is not a valid number, display an error message.
5. If the user enters an empty value, display a message indicating that no value was entered.

## Type Aliases and Interfaces

### Exercise 1: Defining Custom Types

Create a type alias for a book with properties like title, author, and publication year. Define an object using this
type alias and print its details.

1. Define a type alias named `Book` with properties `title`, `author`, and `publicationYear`, each having appropriate
   primitive types.
2. Prompt the user to enter details for a book (title, author, publication year) and create an object of type `Book`
   with the entered values.
3. Display the details of the book object to the user.

### Exercise 2: Using Interfaces

Define an interface for a geometric shape with properties like type, dimensions, and area calculation method. Implement
the interface for a rectangle and a circle.

1. Define an interface named `GeometricShape` with properties `type`, `dimensions`, and a method `calculateArea()` that
   returns a number.
2. Implement the `GeometricShape` interface for a `Rectangle` by prompting the user to enter its dimensions and
   calculating the area using the provided formula.
3. Implement the `GeometricShape` interface for a `Circle` by prompting the user to enter its radius and calculating the
   area.

### Exercise 3: Extending Interfaces

Extend the previous geometric shape interface to include a color property. Implement the extended interface for a
colored rectangle and a colored circle.

1. Extend the `GeometricShape` interface to include a property `color` with a suitable primitive type.
2. Implement the extended interface for a `ColoredRectangle` by implementing the `calculateArea` method and prompting
   the user to enter the color.
3. Implement the extended interface for a `ColoredCircle` in a similar manner.

### Exercise 4: Combinations of Types

Define a type alias for a product that can be either an electronic device with brand and model or a book with title and
author. Create instances of this type alias for different products.

1. Define a type alias named `Product` that can represent either an `ElectronicDevice` or a `Book`.
2. Implement instances of the `Product` type for a sample electronic device and a book, prompting the user for details.
3. Display the details of each product, including the properties specific to the chosen type.

## Advanced Type System Features

### Exercise 1: Union Types

Write a function that takes a string or number and returns its length if it's a string or the square of the number if
it's a number. Use union types to handle both cases.

1. Prompt the user to enter a value as either a string or a number.
2. Define a TypeScript function that takes a parameter of type `string | number`.
3. Use a type guard to check the actual type of the parameter.
4. If the parameter is a string, display its length. If it's a number, display its square.

### Exercise 2: Intersection Types

Create interfaces for a `Person` with name and age properties and an `Address` with city and zip code properties. Define
a type that combines both interfaces and represents a person's profile.

1. Define an interface named `Person` with properties `name` and `age`.
2. Define an interface named `Address` with properties `city` and `zipCode`.
3. Create a type named `PersonProfile` by combining the `Person` and `Address` interfaces using an intersection type.
4. Prompt the user to enter details for a person and an address, and create an object of type `PersonProfile`.
5. Display the combined details of the person and address.

### Exercise 3: Type Guards

Develop a function that takes a value and determines whether it's a string or a number. Use type guards to differentiate
between the two types and print a message accordingly.

1. Prompt the user to enter a value as either a string or a number.
2. Define a TypeScript function that takes a parameter of type `string | number`.
3. Use the `typeof` operator to differentiate between string and number.
4. If the parameter is a string, display a message indicating it's a string. If it's a number, display a message
   indicating it's a number.

### Exercise 4: Generics

Write a generic function that reverses the elements of an array. Test the function with arrays of numbers, strings, and
other types.

1. Create a TypeScript function named `reverseArray` that takes an array as a parameter with a generic type
   parameter `T`.
2. Inside the function, reverse the elements of the array using a loop or the `reverse` method.
3. Return the reversed array.
4. Prompt the user to enter an array of numbers, an array of strings, and an array of any other type.
5. Call the `reverseArray` function for each array type and display the reversed arrays.
