# Chapter 3: Classes and Inheritance

Before we get started with learning classes and inheritance, I want to go over some additional TypeScript features.

Up until now, if we wanted to run a TypeScript file, we would have needed to do:

```
tsc fileNAme.ts
```

to compile our ts file into a js file which we could then run:

```
node fileName.js
```

While it is important to know that TypeScript needs to compile into JavaScript, it doesn't make it any less annoying to have to do that over and over.

First, let's add the ability to run TS files with node. There are a few ways to do this, but we are going to be doing it with `ts-node`.

Let's install it globally running:

```
npm install -g ts-node typescript '@types/node'
```

Now we can run TS files quicker using:

```
ts-node fileName.ts
```

Awesome! So much easier! Again, this helps us for convenience, but it is still important to remember the TypeScript compiler process.

The next thing we want to look at is the tsc config file. Up until now, you might have just been using the default TypeScript rules, or using the ones set up in this repo. TypeScript has a config file that lets you modify the way the TypeScript Compiler will run your code. Think of this like adding mods to Vanilla JavaScript. TypeScript is a mod package, and we can turn certain settings on/off as we see fit.

To view your project's tsc config file run:

```
tsc --init
```

This will create a file called `tsconfig.json`. If you take a look at this, it will be look something like:

```
{
  "compilerOptions": {
    /* Visit https://aka.ms/tsconfig to read more about this file */

    /* Projects */
    // "incremental": true,                              /* Save .tsbuildinfo files to allow for incremental compilation of projects. */
    // "composite": true,                                /* Enable constraints that allow a TypeScript project to be used with project references. */
    // "tsBuildInfoFile": "./.tsbuildinfo",              /* Specify the path to .tsbuildinfo incremental compilation file. */
    // "disableSourceOfProjectReferenceRedirect": true,  /* Disable preferring source files instead of declaration files when referencing composite projects. */
    // "disableSolutionSearching": true,                 /* Opt a project out of multi-project reference checking when editing. */
    // "disableReferencedProjectLoad": true,             /* Reduce the number of projects loaded automatically by TypeScript. */

    /* Language and Environment */
    "target": "ES6",                                  /* Set the JavaScript language version for emitted JavaScript and include compatible library declarations. */
    // "lib": [],                                        /* Specify a set of bundled library declaration files that describe the target runtime environment. */
    // "jsx": "preserve",                                /* Specify what JSX code is generated. */
    // "experimentalDecorators": true,                   /* Enable experimental support for TC39 stage 2 draft decorators. */
    // "emitDecoratorMetadata": true,                    /* Emit design-type metadata for decorated declarations in source files. */
    // "jsxFactory": "",                                 /* Specify the JSX factory function used when targeting React JSX emit, e.g. 'React.createElement' or 'h'. */
    // "jsxFragmentFactory": "",                         /* Specify the JSX Fragment reference used for fragments when targeting React JSX emit e.g. 'React.Fragment' or 'Fragment'. */
    // "jsxImportSource": "",                            /* Specify module specifier used to import the JSX factory functions when using 'jsx: react-jsx*'. */
    // "reactNamespace": "",                             /* Specify the object invoked for 'createElement'. This only applies when targeting 'react' JSX emit. */
    // "noLib": true,                                    /* Disable including any library files, including the default lib.d.ts. */
    // "useDefineForClassFields": true,                  /* Emit ECMAScript-standard-compliant class fields. */
    // "moduleDetection": "auto",                        /* Control what method is used to detect module-format JS files. */

    /* Modules */
    "module": "commonjs",                                /* Specify what module code is generated. */
    // "rootDir": "./dist",                                  /* Specify the root folder within your source files. */
    "moduleResolution": "node",                       /* Specify how TypeScript looks up a file from a given module specifier. */
    // "baseUrl": ".",                                  /* Specify the base directory to resolve non-relative module names. */
    "paths": {
    // "*":["node_modules/*", "src/types/*"]
    },                                      /* Specify a set of entries that re-map imports to additional lookup locations. */
    // "rootDirs": [],                                   /* Allow multiple folders to be treated as one when resolving modules. */
    // "typeRoots": [],                                  /* Specify multiple folders that act like './node_modules/@types'. */
    // "types": [],                                      /* Specify type package names to be included without being referenced in a source file. */
    // "allowUmdGlobalAccess": true,                     /* Allow accessing UMD globals from modules. */
    // "moduleSuffixes": [],                             /* List of file name suffixes to search when resolving a module. */
    // "resolveJsonModule": true,                        /* Enable importing .json files. */
    // "noResolve": true,                                /* Disallow 'import's, 'require's or '<reference>'s from expanding the number of files TypeScript should add to a project. */

    /* JavaScript Support */
    // "allowJs": true,                                  /* Allow JavaScript files to be a part of your program. Use the 'checkJS' option to get errors from these files. */
    // "checkJs": true,                                  /* Enable error reporting in type-checked JavaScript files. */
    // "maxNodeModuleJsDepth": 1,                        /* Specify the maximum folder depth used for checking JavaScript files from 'node_modules'. Only applicable with 'allowJs'. */

    /* Emit */
    // "declaration": true,                              /* Generate .d.ts files from TypeScript and JavaScript files in your project. */
    // "declarationMap": true,                           /* Create sourcemaps for d.ts files. */
    // "emitDeclarationOnly": true,                      /* Only output d.ts files and not JavaScript files. */
    "sourceMap": true,                                /* Create source map files for emitted JavaScript files. */
    // "outFile": "./",                                  /* Specify a file that bundles all outputs into one JavaScript file. If 'declaration' is true, also designates a file that bundles all .d.ts output. */
    "outDir": "./dist",                                   /* Specify an output folder for all emitted files. */
    // "removeComments": true,                           /* Disable emitting comments. */
    // "noEmit": true,                                   /* Disable emitting files from a compilation. */
    // "importHelpers": true,                            /* Allow importing helper functions from tslib once per project, instead of including them per-file. */
    // "importsNotUsedAsValues": "remove",               /* Specify emit/checking behavior for imports that are only used for types. */
    // "downlevelIteration": true,                       /* Emit more compliant, but verbose and less performant JavaScript for iteration. */
    // "sourceRoot": "",                                 /* Specify the root path for debuggers to find the reference source code. */
    // "mapRoot": "",                                    /* Specify the location where debugger should locate map files instead of generated locations. */
    // "inlineSourceMap": true,                          /* Include sourcemap files inside the emitted JavaScript. */
    // "inlineSources": true,                            /* Include source code in the sourcemaps inside the emitted JavaScript. */
    // "emitBOM": true,                                  /* Emit a UTF-8 Byte Order Mark (BOM) in the beginning of output files. */
    // "newLine": "crlf",                                /* Set the newline character for emitting files. */
    // "stripInternal": true,                            /* Disable emitting declarations that have '@internal' in their JSDoc comments. */
    // "noEmitHelpers": true,                            /* Disable generating custom helper functions like '__extends' in compiled output. */
    // "noEmitOnError": true,                            /* Disable emitting files if any type checking errors are reported. */
    // "preserveConstEnums": true,                       /* Disable erasing 'const enum' declarations in generated code. */
    // "declarationDir": "./",                           /* Specify the output directory for generated declaration files. */
    // "preserveValueImports": true,                     /* Preserve unused imported values in the JavaScript output that would otherwise be removed. */

    /* Interop Constraints */
    // "isolatedModules": true,                          /* Ensure that each file can be safely transpiled without relying on other imports. */
    // "allowSyntheticDefaultImports": true,             /* Allow 'import x from y' when a module doesn't have a default export. */
    "esModuleInterop": true,                             /* Emit additional JavaScript to ease support for importing CommonJS modules. This enables 'allowSyntheticDefaultImports' for type compatibility. */
    // "preserveSymlinks": true,                         /* Disable resolving symlinks to their realpath. This correlates to the same flag in node. */
    "forceConsistentCasingInFileNames": true,            /* Ensure that casing is correct in imports. */

    /* Type Checking */
    // "strict": true,                                      /* Enable all strict type-checking options. */
    // "noImplicitAny": true,                            /* Enable error reporting for expressions and declarations with an implied 'any' type. */
    // "strictNullChecks": true,                         /* When type checking, take into account 'null' and 'undefined'. */
    "strictFunctionTypes": true,                      /* When assigning functions, check to ensure parameters and the return values are subtype-compatible. */
    // "strictBindCallApply": true,                      /* Check that the arguments for 'bind', 'call', and 'apply' methods match the original function. */
    // "strictPropertyInitialization": true,             /* Check for class properties that are declared but not set in the constructor. */
    // "noImplicitThis": true,                           /* Enable error reporting when 'this' is given the type 'any'. */
    // "useUnknownInCatchVariables": true,               /* Default catch clause variables as 'unknown' instead of 'any'. */
    // "alwaysStrict": true,                             /* Ensure 'use strict' is always emitted. */
    // "noUnusedLocals": true,                           /* Enable error reporting when local variables aren't read. */
    // "noUnusedParameters": true,                       /* Raise an error when a function parameter isn't read. */
    // "exactOptionalPropertyTypes": true,               /* Interpret optional property types as written, rather than adding 'undefined'. */
    // "noImplicitReturns": true,                        /* Enable error reporting for codepaths that do not explicitly return in a function. */
    // "noFallthroughCasesInSwitch": true,               /* Enable error reporting for fallthrough cases in switch statements. */
    // "noUncheckedIndexedAccess": true,                 /* Add 'undefined' to a type when accessed using an index. */
    // "noImplicitOverride": true,                       /* Ensure overriding members in derived classes are marked with an override modifier. */
    // "noPropertyAccessFromIndexSignature": true,       /* Enforces using indexed accessors for keys declared using an indexed type. */
    // "allowUnusedLabels": true,                        /* Disable error reporting for unused labels. */
    // "allowUnreachableCode": true,                     /* Disable error reporting for unreachable code. */

    /* Completeness */
    // "skipDefaultLibCheck": true,                      /* Skip type checking .d.ts files that are included with TypeScript. */
    "skipLibCheck": true                                 /* Skip type checking all .d.ts files. */
  },
  "include" :[
    "src/**/*.ts",
    "test/**/*.ts"
  ]
}
```

There is a lot in here, so feel free to read into each thing on your own, but for now let us cover the important things in this file.

We can comment out a line if we want to turn off a specific TypeScript feature, or we can comment something in if we want to use it. We can also adjust some of the values if we want to change how our tsc interprets our TS code.

The important things to know:

```
 "target": "ES6",
```

You can change this line to be any specific version of JavaScript you want your TSC to output code as. For this project, I changed it to ES6, but it usally will default to something like ES2015.

```
"outDir": "./dist"
```

Commenting this in will allow our TSC to output JavaScript files into a folder at the root of the project called 'dist'. You can change this to be whatever you want it to be called, or located. It is usually standard practice to keep all your JS files organized

```
"removeComments": true,
```

Commenting this in will remove all the comments made in your TS file from the outputted JS file. You will still have the comments for your TS file, but again, your JS file will not share these comments.

```
"strict": true,
```

This is how we turn or tune the strictness that TypeScript will run on. Typically you should have some sort of strictness for your type checking, as that is the entire point of TypeScript over Vanilla JavaScript. It is up to you and your team to figure out how strict you want it to be. By default, it will be turned on which will be the very strict and encompass all the other strict checks listed below it. For this project, I turned strict off and only turned strictFunctionTypes on to assist with making test-specs (I am the only one working on this project at the time of writing so I know how my code is supposed to run and don't need TypeScript as a team dev tool to be strict).

Lastly, you can add:

```
 "include" :[
    "src/**/*.ts",
    "test/**/*.ts"
  ]
```

as the next key value pair to your tsconfig file (sibling to compileOptions). This will let you run test specs in TypeScript while also checking TypeScript code without having to change every file into JavaScript first. You do not need to add this if you don't plan on doing TypeScript Test-Driven Development.

**Now back to our regularly scheduled topics!**

---

## Abstract Classes and Interfaces

Classes are one of the most important features of TypeScript and they are used to create objects. In TypeScript, classes provide a way to define blueprints for creating objects, which allows you to create multiple instances of a class with the same properties and methods.

Classes in TypeScript look very similar to JavaScript classes. One of the key differences is the need to create type variables before the constructor

Let's first look at a simple Person class in JavaScript. It will just take in a name, age, and have a printName instance method that will log the instance name to the console.

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  printName() {
    console.log(`Hi my name is: ${this.name}`);
  }
}

let newPerson1 = new Person("John Smith", 20);
```

This will look similar to TypeScript version, but notice the type declarations above the constructor

To create a class in TypeScript, you can use the `class` keyword, followed by the name of the class. Here's an example:

```typescript
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  printName(): void {
    console.log(`Hi my name is: ${this.name}`);
  }
}

let newPerson1 = new Person("John Smith", 20);

newPerson1.printName();
```

In this example, we've defined a class called 'Person' with two properties: 'name' and 'age'. We've also defined a constructor method that takes in two parameters and assigns them to the corresponding properties of the class. Finally, we've defined a 'printName' instance method that logs a message to the console.

One of the benefits of using classes in TypeScript is that you can define interfaces that describe the shape of the class. For example, we could define an interface for our Person class like this:

```typescript
interface PersonInterface {
  name: string;
  age: number;
  printName(): void;
}

class Person {
  name: string;
  age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  printName(): void {
    console.log(`Hi my name is: ${this.name}`);
  }
}

let newPerson1: PersonInterface = new Person("John Smith", 20);

newPerson1.printName();
```

## Access Modifiers

Access modifiers are a key feature of object-oriented programming that allow you to control how properties and methods of a class can be accessed.

In TypeScript, there are three access modifiers that can be used to control access to class members:

- Public
- Private
- Protected

Let's take a closer look at each of these access modifiers.

### Public Access Modifier

The `public access modifier` is the default access modifier in TypeScript. It allows class members to be accessed from anywhere, both inside and outside of the class. Here's an example:

```typescript
class Person {
  public name: string;
  public age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  printName(): void {
    console.log(`Hi my name is: ${this.name}`);
  }
}
```

In this example, all the properties and methods are marked as public. This means they can be accessed from anywhere, including outside of the class. For example:

```typescript
const newPerson = new Person("John Smith", 20);
console.log(newPerson.name); // logs: "John Smith"
newPerson.printName(); // logs: Hi my name is: John Smith
```

### Private Access Modifier

The `private access modifier` restricts access to class members to only within the class. This means that the properties and methods marked as private cannot be accessed from outside the class. Here's an example:

```typescript
class Person {
  private name: string;
  private age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  printName(): void {
    console.log(`Hi my name is: ${this.name}`);
  }
}

const newPerson = new Person("John Smith", 20);
console.log(newPerson.name); // logs: // ERROR: Property 'name' is private and only accessible within class 'Person'.
```

_P.S, Until July 2022 TypeScript was the only way to create private variable methods for classes. JavaScript added this feature recently, but JavaScript declares private variables using '#'. Make sure not to get them flipped!_

### Protected Access Modifier

The protected access modifier is similar to the private access modifier in that it restricts access to class members to within the class. However, it also allows subclasses to access these members. Here's an example:

```typescript
class Person {
  protected name: string;
  protected age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  public printName(): void {
    console.log(`Hi my name is: ${this.name}`);
  }
}

class Developer extends Person {
  public printNameAndTitle() {
    console.log(`Hi I am ${this.name}, and I am a developer`);
  }
}

const newPerson = new Person("John Smith", 20);
console.log(newPerson.name); // logs: // ERROR: Property 'name' is protected and only accessible within class 'Person' and its subclasses.
const newDev = new Developer("Jane Doe", 25);
newDev.printName(); // logs "Hi my name is: Jane Doe
newDev.printNameAndTitle(); // logs: Hi I am Jane Doe, and I am a developer
```

** This is a great time to take a break from reading and jump into some code! Head over to the hero.ts file located in the problems directory in this directory.**

Generics
Chapter 3 Coding Test