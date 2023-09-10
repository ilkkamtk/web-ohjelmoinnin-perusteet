# Toolchain - TypeScript
## Node.js
- [Node material here](node.md)

## npm
- [npm material here](npm.md)

## TypeScript
- Install TypeScript globally: `npm i -g typescript`
- Create a folder for your first TypeScript project.
- Navigate to that folder in your terminal
- Initialise new npm project: `npm init -y`
- Write a new HTML file `index.html`:
  ```HTML
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>First App</title>
      <script src="build/main.js" defer></script>
  </head>
  
  <body>
      <h1><!-- greeting is printed here--></h1>
  </body>
  
  </html>
   ```
- Write a configuration file called `tsconfig.json`:
  ```json
    {
        "compilerOptions": {
          "outDir": "./build",
          "target": "ESNext",
          "module": "ESNext",
          "noImplicitAny": true,
          "strict": true
        },
        "include": ["./src/**/*"]
    }

  ```
  - **"compilerOptions"**: specifies the compiler options for TypeScript.
  - **"outDir": "./dist"**: specifies the output directory for the compiled JavaScript files.
  - **"target": "ESNext"**: sets the target ECMAScript version to "ESNext". Compiler will transpile your code to the latest ECMAScript version available.
  - **"module": "ESNext"**: sets the module code generation to "ESNext". Compiler will generate ECMAScript modules using the `import` and `export` syntax supported by modern JavaScript environments.
  - **"noImplicitAny"**: ensure that all variables, parameters, and return types have explicit type annotations.
  - **"include"**: specifies the file inclusion patterns for the TypeScript compiler.
- Write new TypeScript file `src/main.ts`
  ```typescript
  const greeting = (name: string) => {
    console.log(`Hello ${name}!`);
  };

  greeting('Frank');
  ```
- Compile TypeScript to JavaScript. Run this command in the terminal: `tsc`
- You should now have `main.js` in `build` folder.
- Open `index.html` with Live Server extension in VSCode.


