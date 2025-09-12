## Utility Types in TypeScript

TypeScript's utility types are built-in type transformations that can be applied to existing types to create new types
or modify existing ones. They enhance code readability, maintainability, and reduce the need for repetitive type
definitions.

1. **`Partial<Type>`:**
    - Creates a type with all properties of the given `Type` set as optional.
    - Useful for creating partial forms or objects with optional properties.

   ```typescript
   type Person = {
     name: string;
     age: number;
   };
   
   type PartialPerson = Partial<Person>;
   // PartialPerson has properties name and age as optional
   ```

2. **`Required<Type>`:**
    - Creates a type with all properties of the given `Type` set as required.
    - Useful when you want to ensure that an object has all its properties defined.

   ```typescript
   type PartialPerson = {
     name?: string;
     age?: number;
   };
   
   type RequiredPerson = Required<PartialPerson>;
   // RequiredPerson has properties name and age as required
   ```

3. **`Readonly<Type>`:**
    - Creates a type with all properties of the given `Type` set as readonly.
    - Prevents modification of object properties after initialization.

   ```typescript
   type MutablePerson = {
     name: string;
   };
   
   type ReadonlyPerson = Readonly<MutablePerson>;
   // ReadonlyPerson has readonly property name
   ```

4. **`Record<Keys, Type>`:**
    - Creates an object type with keys from `Keys` and values of type `Type`.
    - Useful for creating dictionaries or mapping types.

   ```typescript
   type Person = {
     name: string;
     age: number;
   };
   
   type PersonMap = Record<string, Person>;
   // PersonMap maps string keys to Person objects
   ```

5. **`Pick<Type, Keys>`:**
    - Creates a type by picking specific properties `Keys` from the given `Type`.
    - Useful for extracting a subset of properties from an object.

   ```typescript
   type Person = {
     name: string;
     age: number;
     address: string;
   };
   
   type PersonInfo = Pick<Person, 'name' | 'age'>;
   // PersonInfo only includes properties name and age
   ```

6. **`Omit<Type, Keys>`:**
    - Creates a type by omitting specific properties `Keys` from the given `Type`.
    - Useful for excluding certain properties from an object.

   ```typescript
   type Person = {
     name: string;
     age: number;
     address: string;
   };
   
   type BasicPerson = Omit<Person, 'address'>;
   // BasicPerson excludes property address
   ```

7. **`Exclude<Type, ExcludedUnion>`:**
    - Creates a type by excluding values from `Type` that are assignable to `ExcludedUnion`.
    - Useful for narrowing down unions based on exclusion.

   ```typescript
   type NumberOrString = number | string;
   
   type OnlyNumbers = Exclude<NumberOrString, string>;
   // OnlyNumbers includes only number type
   ```

8. **`Extract<Type, Union>`:**
    - Creates a type by extracting values from `Type` that are assignable to `Union`.
    - Useful for narrowing down unions based on inclusion.

   ```typescript
   type NumberOrString = number | string;
   
   type OnlyNumbers = Extract<NumberOrString, number>;
   // OnlyNumbers includes only number type
   ```

9. **`NonNullable<Type>`:**
    - Creates a type by excluding `null` and `undefined` from the given `Type`.
    - Ensures that a type is not nullable.

   ```typescript
   type MaybeNumber = number | null | undefined;
   
   type NotNullableNumber = NonNullable<MaybeNumber>;
   // NotNullableNumber includes only number type
   ```

10. **`ReturnType<Type>`:**
- Extracts the return type of a function `Type`.
- Useful for inferring the return type of functions.

 ```typescript
 type GreetFunction = () => string;
 
 type GreetReturnType = ReturnType<GreetFunction>;
 // GreetReturnType is string
 ```

11. **`Parameters<Type>`:**
- Extracts the parameter types of a function `Type`.
- Useful for inferring the argument types of functions.

 ```typescript
 type MathFunction = (a: number, b: number) => number;
 
 type MathParameters = Parameters<MathFunction>;
 // MathParameters is [number, number]
 ```

12. **`RequiredKeys<Type>` and `OptionalKeys<Type>`:**
- Extracts the required and optional keys from an object `Type`.

 ```typescript
 type Person = {
   name: string;
   age?: number;
 };
 
 type RequiredKeysOfPerson = RequiredKeys<Person>;
 // RequiredKeysOfPerson is 'name'
 
 type OptionalKeysOfPerson = OptionalKeys<Person>;
 // OptionalKeysOfPerson is 'age'
 ```
---

## [Exercises](utility-exercises.md)

---

## Assignments

### Converting the Restaurant App to TypeScript

Convert the existing JavaScript-based Restaurant Application into TypeScript. TypeScript will help us catch potential
errors early and make the codebase more maintainable.

1. **Download Starter Files:**
    - Click on the following link to download the starter files: [Download repo as zip](https://github.com/ilkkamtk/TS-3/archive/refs/heads/main.zip).
    - Extract the contents of the downloaded zip file to your working directory.

2. **Identify and Resolve Type Errors:**
    - Navigate to the 'src' folder in the extracted files.
    - Open the TypeScript files within this 'src' folder.
    - You'll notice red squiggly lines in the code. These indicate type errors.
    - Your primary task is to fix these errors by adding appropriate type annotations to variables, functions,
      arguments, and parameters.

3. **Creating Interfaces/Types:**
    - Begin by creating types (or interfaces, depending on your preference) for the data structures used in the
      application.
    - Specifically, focus on creating types for the restaurants and menus that are obtained from the
      Restaurant API.
    - Additionally, ensure you use built-in TypeScript types such as `number`, `string`, `boolean`, etc., wherever they
      are applicable within the code.

4. **Adding Type Annotations:**
    - Scan through the code and identify variables, functions, arguments, and parameters that lack type annotations.
    - Add type annotations to these elements, matching them with the interfaces/types you created in step 3 where
      necessary.
    - Be thorough in your review and annotation to eliminate all type-related errors in the code.

5. **Testing:**
    - After adding type annotations, thoroughly test the application to ensure it functions correctly. Run `npm run dev`
      and open `index.html` with Live Server in VSCode.
    - Make any necessary adjustments to the code to ensure it operates as expected.
