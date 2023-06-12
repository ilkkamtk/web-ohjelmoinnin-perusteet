# Bundler
Bundlers are used for optimizing and organizing code. Bundlers take modular code structures, consisting of multiple JavaScript and CSS files, and combine them into a single, optimized bundle that can be served to the browser. They support modern JavaScript module systems, optimize code through various transformations, perform asset management, and enhance the developer experience with features like live reloading and hot module replacement. Popular bundlers such as Webpack, Rollup, and Parcel provide developers with powerful tools to improve performance, streamline development workflows, and support modern web development practices.

## Example with Rollup

1. Install Rollup and the necessary plugins:
```shell
npm install rollup rollup-plugin-typescript2 rollup-watch rollup-plugin-livereload -D
```

2. Create a Rollup configuration file, typically named `rollup.config.js`, in the root of your project:
```javascript
import typescript from 'rollup-plugin-typescript2';
import { watch } from 'rollup';

export default {
  input: './src/index.ts',
  output: {
    file: './build/bundle.js',
    format: 'cjs',
  },
  plugins: [
    typescript(),
  ],
  watch: {
    clearScreen: false,
    include: 'src/**',
    exclude: 'node_modules/**',
  },
};

```

In this configuration, we specify the entry point of our application (`index.ts`), the output file and format for the bundled code (`bundle.js`), and the Rollup plugin to handle TypeScript files.

3. Create a `tsconfig.json` file in the root of your project to configure TypeScript:
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

4. Update your HTML file to reference the bundled file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>First App</title>
    <script src="build/bundle.js" defer></script>
</head>
<body>
<h1 id="greeting"></h1>
</body>
</html>
```

5. Create your entry point TypeScript file, `index.ts`, where you can import and use your `greeting` function:
```typescript
import greeting from './functions/greeting';

const h1Element = document.getElementById('greeting');
if (h1Element) {
  h1Element.textContent = greeting('TypeScript');
}
```

6. Modify package.json to add start scripts for development and building:
```json
"scripts": {
  "build": "rollup -c",
  "dev": "rollup -c -w"
},
```

6. When developing run:
```shell
npm run dev
```
7. When compiling the final code run:
```shell
npm run build
```
  - This will bundle your TypeScript code and its dependencies into a single `bundle.js` file in the `dist` directory. You can then open your HTML file in the browser to see the result.

