# TypeScript
TypeScript is an open-source programming language that is a typed superset of JavaScript. It was developed by Microsoft and is designed to address some of the shortcomings of JavaScript by adding optional static typing, class-based object-oriented programming, and other features that are not present in JavaScript.

TypeScript code can be compiled to JavaScript, which means that it can be used in any environment where JavaScript is supported, such as web browsers and Node.js. By providing optional static typing, TypeScript helps to catch errors during development time, making the code more reliable and easier to maintain. TypeScript also provides features like interfaces, enums, and classes that make it easier to write object-oriented code in JavaScript.

# Setting Up
## 1. Setup
### Install Node.js (if not installed)
TypeScript requires Node.js to run. Download and install it from:
[https://nodejs.org/](https://nodejs.org/)
After installation, check if Node.js and npm are installed
```
node -v
npm -v
```
### 2. Install TypeScript
Run the following command to install TypeScript globally
```
npm install -g typescript
```
Verify the installation:
```
tsc -v
```
If you see a version number, TypeScript is installed.

### 3. Create a TypeScript Project
Create a new folder and navigate into it:
```
mkdir typescript-demo
cd typescript-demo
```
Initialize a new project (optional but recommended):
```
npm init -y
```
### 4. Create a TypeScript File
Inside the `typescript-demo` folder, create a new file `index.ts`:
```
function greet(): string {
    return `Hello, World !`;
}

console.log(greet());
```
### 5. Compile TypeScript to JavaScript
```
tsc index.ts
```
This will generate a `index.js` file in the same directory.
### 6. Run the JavaScript File
Run the generated JavaScript file using Node.js:
```
node index.js
```
Output:
```
Hello, World !
```

## Data Types
In TypeScript, there are several data types that can be used to define variables, functions, and other constructs. These data types include:
Boolean: represents a value that can be either true or false.
```
let isCompleted: boolean = false;
```

Number: represents both integer and floating-point numbers.
```
let age: number = 30;
let price: number = 4.99;
```

String: represents a sequence of characters.
```
let name: string = "John";
let message: string = `Hello, ${name}!`;
```

Array: represents a collection of values of the same type.
```
let numbers: number[] = [1, 2, 3, 4];
let names: string[] = ["John", "Jane", "Bob"];
```

Tuple: represents an array with a fixed number of elements, where each element may have a different type.
```
let person: [string, number] = ["John", 30];
```

Enum: represents a set of named constants.
```
enum Color {
  Red,
  Green,
  Blue,
}

let backgroundColor: Color = Color.Red;
```

Any: represents any type of value.
```
let x: any = 10;
x = "hello";
```

Void: represents the absence of any type. It is commonly used as the return type of functions that do not return a value.
```
function logMessage(message: string): void {
  console.log(message);
}
```

Null and Undefined: represent the absence of a value. They are typically used to indicate that a variable does not have a value.
```
let notDefined: undefined = undefined;
let noValue: null = null;
```
### [:fast_forward: Next: TypeScript Documentation](https://github.com/dev-satri/TypeScript-Documentation/blob/main/TypeScript-Documentation.md)
