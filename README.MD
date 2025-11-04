# LESSON TWO - Node.js Modules #

## 1. Introduction ##
These notes cover Node.js, TypeScript modules, Git workflow, and common Node.js core modules. They combine practical explanations, corrected information, and structured guidance for understanding and applying these concepts.

---

## 2. Git and Project Setup ##

### Cloning and Initialising a Project ###
You can clone a Git repository to start working on it locally. After cloning, you may want to detach the project from its original remote repository to make it independent.

**Commands:**
- `git clone <repository-url>` – clones the repository locally.
- `git remote remove origin` – removes the link to the original GitHub repository.
- `git remote -v` – verifies that no remote is attached.

After detaching, you can connect the project to a new GitHub repository and continue development freely.

### npm Setup ###
Use npm to install dependencies and build your project:
- `npm install` – installs all dependencies specified in `package.json`.
- `npm run build` – compiles TypeScript files into JavaScript and creates a `dist` folder.

---

## 3. TypeScript Modules ##

### Creating Modules ###
In TypeScript, modules allow you to split code into reusable files. You can export functions, classes, or constants from one file and import them into others. This makes your code more organised and maintainable.

**Key points:**
- `export` makes a function, class, or constant available to other files.
- `export default` allows a single default export per module.
- Named exports can coexist with a default export.

### Importing Modules ###
You can import modules in several ways:
- Named imports: `import { add, subtract } from './math';`
- Import all as alias: `import * as math from './math';`
- Default import: `import multiply from './math';`
- Mixed: `import multiplyDefault, { addMultiple, Calculator } from './math';`

This flexibility allows you to access only the parts of a module you need or everything under an alias.

### TypeScript Configuration ###
Modifying the TypeScript configuration is essential for proper module handling:
- `module: 'commonjs'` or `'es2022'` ensures compatibility with Node.js module resolution.
- `rootDir` and `outDir` define the source and output directories.
- `esModuleInterop: true` helps import CommonJS modules seamlessly.

`tsconfig.json` example:
```json
{
  "compilerOptions": {
    "target": "es2016",
    "module": "commonjs",
    "rootDir": "./src",
    "outDir": "./dist",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true
  }
}
```
This configuration ensures TypeScript can correctly compile and resolve modules for Node.js.

---

## 4. Node.js Core Modules ##
| Module | Purpose                                                         | Main Functions                   |
| ------ | --------------------------------------------------------------- | -------------------------------- |
| `http` | Create HTTP server and handle web requests/responses            | `http.createServer()`            |
| `url`  | Parse and manipulate URLs                                       | `url.parse()`                    |
| `util` | Utility functions, convert callback-based functions to promises | `util.promisify()`               |
| `path` | Handle file and directory paths                                 | `path.join()`, `path.basename()` |

---

## 5. Working with Paths in Node.js ##
Node.js provides the `path` module (imported via `import path from 'node:path'`) to handle filesystem paths in a consistent and platform-independent way.

- `path.join()` – combines multiple path segments into a single path, automatically handling separators for different operating systems.
- `path.basename()` – extracts the last part of a path (e.g., filename) without including the rest of the directory.

These functions help prevent errors related to manually concatenating strings for file paths.

---

## 6. Useful npm Libraries ##
- Use `npm search <library>` to find packages.
- Example libraries:
  - `axios` for HTTP requests.
  - `pdfkit` for PDF processing.
  - Image resizing libraries.
- Node core modules (prefixed with `node:`) do not require installation.

---

## 7. References and Links ##
- https://aka.ms/tsconfig/module
- https://www.npmjs.com/

---

## 8. Console Commands ##
1. git clone https://github.com/TryCatchMeIfYouCanDev/node-basic.git node-basics  // clone project
2. git remote remove origin  // detach from GitHub remote
3. git remote -v  // check remote
4. npm install  // install dependencies
5. npm run build  // compile TypeScript
6. npm start  // run project with ts-node

*End of Class Notes Summary*