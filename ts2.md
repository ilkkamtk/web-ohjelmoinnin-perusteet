# TypeScript advanced typing

## Optional Properties

Sometimes, not all properties of an object are required. TypeScript allows you to define optional properties in your interfaces. This is especially useful when creating objects with varying sets of properties.

Consider the following examples:

**Example 1: Optional Property**
```typescript
interface Person {
  name: string;
  age?: number; // Optional property
}

const alice: Person = { name: "Alice" };
const bob: Person = { name: "Bob", age: 25 };
```

In this example, the `age` property is optional. You can create a `Person` object with or without the `age` property.

**Example 2: Function Parameters with Optional Properties**
```typescript
interface Config {
  host: string;
  port?: number; // Optional property
}

function initializeApp(config: Config) {
  // Initialize app using config
}

initializeApp({ host: "example.com" });               // No port provided
initializeApp({ host: "localhost", port: 3000 });     // Port provided
```

Here, the `port` property is optional in the `Config` interface. When calling the `initializeApp` function, you can provide a configuration object with or without the `port` property.

**Benefits of Optional Properties:**
- Allows you to create objects with varying properties.
- Improves code flexibility when not all properties are needed.
- Enables cleaner interfaces for scenarios where some properties are optional.

--- 

## Readonly Properties

In TypeScript, you can use readonly properties to ensure that certain properties of an object cannot be modified after they are initially set. This is useful when you want to prevent accidental modifications to important data.

Consider the following examples:

**Example 1: Readonly Property**
```typescript
interface Point {
  readonly x: number;
  readonly y: number;
}

const origin: Point = { x: 0, y: 0 };
origin.x = 10; // Error: Cannot assign to 'x' because it is a read-only property
```

In this example, the `x` and `y` properties of the `Point` interface are marked as readonly. Once these properties are set, you cannot change their values.

**Example 2: Readonly Arrays**
```typescript
const numbers: ReadonlyArray<number> = [1, 2, 3];
numbers.push(4); // Error: Property 'push' does not exist on type 'readonly number[]'
```

Arrays can also be marked as readonly. This prevents methods like `push` from modifying the array.

**Benefits of Readonly Properties:**
- Prevents accidental modifications to critical data.
- Enhances code reliability and prevents bugs related to unintended changes.
- Useful for scenarios where data should remain constant once initialized.

---

## Array Types

**Defining Array Types:**
Arrays in TypeScript can hold multiple values of the same type. Array types are written as `type[]` or using the generic syntax `Array<type>`.

**Example 1: Basic Array Type**
```typescript
let numbers: number[] = [1, 2, 3, 4, 5];
let fruits: string[] = ["apple", "banana", "orange"];
```

**Example 2: Using Array\<T\> Generic Syntax**
```typescript
let colors: Array<string> = ["red", "green", "blue"];
```

**Using Array Types in Interfaces:**
You can use array types within interfaces to define properties that are expected to be arrays.

**Example 3: Interface with Array Property**
```typescript
interface ShoppingCart {
  items: string[];
  totalPrice: number;
}

const cart: ShoppingCart = {
  items: ["item1", "item2"],
  totalPrice: 100
};
```

---

## Tuple Types

In TypeScript, tuple types offer a way to represent an array with a fixed number of elements, each with a specific type. Tuples allow you to maintain strict ordering of elements while specifying their data types. Let's dive into the concept of tuple types with some examples.

**Defining Tuple Types:**
Tuple types are defined using square brackets and specifying the types for each element in the order they appear.

**Example 1: Basic Tuple Type**
```typescript
let person: [string, number] = ["Alice", 30];
let coordinates: [number, number] = [10, 20];
```

**Using Tuple Types in Interfaces:**
Tuples can be used within interfaces to define structured data models.

**Example 2: Interface with Tuple Property**
```typescript
interface Employee {
  id: number;
  info: [string, string, number]; // [firstName, lastName, age]
}

const employee: Employee = {
  id: 1,
  info: ["John", "Doe", 25]
};
```

**Accessing Elements in Tuples:**
Elements in tuples can be accessed using index positions.

**Example 3: Accessing Tuple Elements**
```typescript
let point: [number, number] = [5, 10];
let xCoord: number = point[0]; // 5
let yCoord: number = point[1]; // 10
```

**Mutability of Tuple Elements:**
Tuples are mutable, meaning you can modify their individual elements.

**Example 4: Modifying Tuple Elements**
```typescript
let data: [string, number] = ["Alice", 30];
data[0] = "Bob"; // Modify the first element
data[1]++;       // Increment the second element
```

**Tuple vs. Array:**
While arrays can hold any number of elements of the same type, tuples have a fixed length and allow specifying types for each element.

---

## Exercises

**Exercise 1: Optional Properties**

Create an interface for representing a user profile. The user profile should have a username, email, and an optional bio. Write a function that displays the user's information, including the bio if provided.

```typescript
// TODO: Define the interface User with username, email, and optional bio

// TODO: Create a user object using the defined interface. Add all properties
// TODO: Create another user object using the defined interface. Don't add bio

// Function to display user information
function displayUserInfo(user: User): void {
  // TODO: console log all properties of a user separately. Example: console.log(user.email)
}

// Display user information
displayUserInfo(user);
```

**Exercise 2: Array Types**

Construct an interface for a blog post. Each post should have a title, content, and an array of tags. Write a function that displays the tags of a blog post.

```typescript
// TODO: Define the interface BlogPost with title, content, and tags array

const blogPost: BlogPost = {
  title: "Getting Started with TypeScript",
  content: "Learn the basics of TypeScript and its powerful features.",
  tags: ["TypeScript", "Programming", "Web Development"]
};

// Function to display tags of a blog post
function displayTags(post: BlogPost): void {
  console.log(`Tags: ${post.tags.join(", ")}`);
}

// Display tags of the blog post
displayTags(blogPost);
```

**Exercise 3: Tuple Types**

Develop an interface for a student's exam result. Each result should include the student's name, an array of subject scores as a tuple (subject name and score), and the total score. Write a function that calculates and displays the average score.

```typescript
// TODO: Define the interface ExamResult with name, subject scores tuple, and total score

const examResult: ExamResult = {
  name: "Alice",
  scores: [["Math", 85], ["Science", 92], ["History", 78]],
  totalScore: 255
};

// Function to calculate and display average score
function displayAverageScore(result: ExamResult): void {
  const totalSubjects = result.scores.length;
  const totalScore = result.totalScore;
  const averageScore = totalScore / totalSubjects;
  console.log(`Average Score for ${result.name}: ${averageScore.toFixed(2)}`);
}

// Display average score
displayAverageScore(examResult);
```
