**Exercise 1:** Exclude the 'email' property from a user interface

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

type BasicUser = //TODO;

// Example usage (valid)
const userWithoutEmail: BasicUser = { id: 1, name: 'John' };

// Example usage (invalid)
const userWithEmail: BasicUser = { id: 2, name: 'Alice', email: 'alice@example.com' };
```

**Exercise 2:** Ensure the type is not nullable for a given type

```typescript
type MaybeName = string | null | undefined;

type NotNullableName = //TODO;

// Example usage (valid)
const validName: NotNullableName = 'Alice';

// Example usage (invalid)
const nullName: NotNullableName = null;
```

**Exercise 3:** Create an interface for a required user profile with 'username,' 'email,' and 'age' properties

```typescript
type UserProfile = //TODO;

// Example usage (valid)
const user: UserProfile = { username: 'alice', email: 'alice@example.com', age: 25 };

// Example usage (invalid)
const incompleteUser: UserProfile = { username: 'bob' };
```

**Exercise 4:** Extract 'name' and 'price' properties from a product interface

```typescript
interface Product {
  id: number;
  name: string;
  price: number;
}

type ProductInfo = //TODO;

// Example usage (valid)
const productInfo: ProductInfo = { name: 'Widget', price: 19.99 };

// Example usage (invalid)
const invalidProductInfo: ProductInfo = { id: 1, name: 'Invalid Product' };
```

**Exercise 5:** Create a dictionary of users using the `Record` type

```typescript
interface User {
  name: string;
  age: number;
}

type UserDictionary = //TODO;

// Example usage of the UserDictionary (valid)
const users: UserDictionary = {
  user1: { name: 'Alice', age: 30 },
  user2: { name: 'Bob', age: 25 },
  user3: { name: 'Charlie', age: 35 },
};

// Access a user by key
const alice: User = users.user1;

// Example usage (invalid)
const invalidUsers: UserDictionary = {
  user4: { name: 'David', age: 'unknown' },
};
```

Certainly! Here are the remaining exercises (6 to 12) with both valid and invalid example usages:

**Exercise 6:** Create a read-only configuration interface for 'apiUrl' and 'apiKey'

```typescript
interface Configuration {
  apiUrl: string;
  apiKey: string;
}

type ReadonlyConfig = //TODO;

// Example usage (valid)
const config: ReadonlyConfig = { apiUrl: 'https://api.example.com', apiKey: 'secret-key' };

// Attempt to modify a read-only property (invalid)
config.apiUrl = 'https://new-api.example.com';
```

**Exercise 7:** Extract 'orange' and 'grape' values from a union type of fruits

```typescript
type Fruit = 'apple' | 'banana' | 'orange' | 'grape';

type CitrusFruits = //TODO;

// Example usage (valid)
const citrusFruits: CitrusFruits = ['orange', 'grape'];

// Example usage (invalid)
const nonCitrusFruits: CitrusFruits = ['apple', 'banana'];
```

**Exercise 8:** Infer the argument types of a Math function that takes 'a' and 'b' as arguments

```typescript
interface MathFunction {
  (a: number, b: number): number;
}

type MathArgs = //TODO;

// Example usage (valid)
const mathArgs: MathArgs = [5, 10];

// Example usage (invalid)
const invalidMathArgs: MathArgs = [5, 'invalid'];
```

**Exercise 9:** Infer the return type of a Greet function that returns a string

```typescript
interface GreetFunction {
  (): string;
}

type GreetResult = //TODO;

// Example usage (valid)
const greeting: GreetResult = 'Hello, World!';

// Example usage (invalid)
const invalidGreeting: GreetResult = 42;
```

**Exercise 10:** Create a partial address interface with optional properties 'street,' 'city,' and 'postalCode'

```typescript
interface Address {
  street?: string;
  city?: string;
  postalCode?: string;
}

type PartialAddress = //TODO;

// Example usage (valid)
const partialAddress: PartialAddress = { street: '123 Main St', city: 'City' };

// Example usage (invalid)
const invalidPartialAddress: PartialAddress = { zipcode: '12345' };
```

**Exercise 11:** Exclude 'green' and 'yellow' values from a union type of colors

```typescript
type Color = 'red' | 'green' | 'blue' | 'yellow';

type PrimaryColors = //TODO;

// Example usage (valid)
const primaryColors: PrimaryColors = ['red', 'blue'];

// Example usage (invalid)
const invalidColors: PrimaryColors = ['green', 'yellow'];
```

**Exercise 12:** Extract required key 'name' and optional key 'price' from a product interface

```typescript
interface Product {
  name: string;
  price?: number;
  description: string;
}

type RequiredKeysOfProduct = //TODO;
type OptionalKeysOfProduct = //TODO;

// Example usage (valid)
const requiredKeys: RequiredKeysOfProduct = 'name';
const optionalKeys: OptionalKeysOfProduct = 'price';

// Example usage (invalid)
const invalidRequiredKeys: RequiredKeysOfProduct = 'description';
const invalidOptionalKeys: OptionalKeysOfProduct = 'nonexistent';
```

I've added both valid and invalid example usages for the remaining exercises as requested.
