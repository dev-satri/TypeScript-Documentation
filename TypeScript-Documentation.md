
# TypeScript Documentation

## Data Types

<details>
  <summary>Click to expand</summary>


<br>


In TypeScript, there are several data types that can be used to define variables, functions, and other constructs. These data types include:
Boolean: represents a value that can be either true or false.
```typescript
let isCompleted: boolean = false;
```

Number: represents both integer and floating-point numbers.
```typescript
let age: number = 30;
let price: number = 4.99;
```

String: represents a sequence of characters.
```typescript
let name: string = "John";
let message: string = `Hello, ${name}!`;
```

Array: represents a collection of values of the same type.
```typescript
let numbers: number[] = [1, 2, 3, 4];
let names: string[] = ["John", "Jane", "Bob"];
```

Tuple: represents an array with a fixed number of elements, where each element may have a different type.
```typescript
let person: [string, number] = ["John", 30];
```

Enum: represents a set of named constants.
```typescript
enum Color {
  Red,
  Green,
  Blue,
}

let backgroundColor: Color = Color.Red;
```

Any: represents any type of value.
```typescript
let x: any = 10;
x = "hello";
```

Void: represents the absence of any type. It is commonly used as the return type of functions that do not return a value.
```typescript
function logMessage(message: string): void {
  console.log(message);
}
```

Null and Undefined: represent the absence of a value. They are typically used to indicate that a variable does not have a value.
```
let notDefined: undefined = undefined;
let noValue: null = null;
```
</details>











## Functions in TypeScript

<details>

<summary>Click to expand</summary>


<br>

In TypeScript, functions are defined using the function keyword, followed by the function name, and then the parameter list in parentheses. The function body is enclosed in curly braces, and the return type, if any, is specified after the parameter list using a colon.
`Example 1`
Function with no parameters and no return type:
```typescript
function sayHello(): void {
  console.log("Hello!");
}
```
`Example 2`
Function with one parameter and a return type:
```typescript
function double(number: number): number {
  return number * 2;
}
```
`Example 3`
Function with multiple parameters and a return type:
```typescript
function addNumbers(a: number, b: number): number {
  return a + b;
}
```
`Example 4`
Function with optional parameters and a return type:
```typescript
function buildName(firstName: string, lastName?: string): string {
  if (lastName) {
    return firstName + " " + lastName;
  } else {
    return firstName;
  }
}
```
The question mark after the lastName parameter indicates that it is optional.
`Example 5`
Function with default parameter values and a return type:
```typescript
function calculatePrice(price: number, taxRate: number = 0.1): number {
  return price + (price * taxRate);
}
```
The taxRate parameter has a default value of 0.1, which means that it is optional and will default to 0.1 if no value is provided.
`Example 6`
Arrow function with implicit return type:
```
const multiply = (a: number, b: number) => a * b;
```
</details>



## Conditional Statements in TypeScript

<details>

<summary>Click to expand</summary>

<br>


In TypeScript, conditional statements are used to execute different blocks of code based on a condition. The two main types of conditional statements are the if statement and the switch statement.
`If Statement`
The if statement is used to execute a block of code if a condition is true. The basic syntax is as follows:
```typescript
if (condition) {
  // code to execute if the condition is true
}
```
Here's an example:
```typescript
let x: number = 10;

if (x > 5) {
  console.log("x is greater than 5");
}
```
`If-else Statement`
The if-else statement is used to execute one block of code if a condition is true and another block of code if the condition is false. The basic syntax is as follows:
```typescript
if (condition) {
  // code to execute if the condition is true
} else {
  // code to execute if the condition is false
}
```
Here's an example:
```typescript
let x: number = 10;

if (x > 5) {
  console.log("x is greater than 5");
} else {
  console.log("x is less than or equal to 5");
}
```
`If-else if Statement`
The if-else if statement is used to execute different blocks of code based on multiple conditions. The basic syntax is as follows:
```typescript
if (condition1) {
  // code to execute if condition1 is true
} else if (condition2) {
  // code to execute if condition2 is true
} else {
  // code to execute if all conditions are false
}
```
Here's an example:
```typescript
let x: number = 10;

if (x > 20) {
  console.log("x is greater than 20");
} else if (x > 10) {
  console.log("x is greater than 10");
} else {
  console.log("x is less than or equal to 10");
}
```
`Switch Statement`
The switch statement is used to execute different blocks of code based on the value of an expression. The basic syntax is as follows:
```typescript
switch (expression) {
  case value1:
    // code to execute if expression is equal to value1
    break;
  case value2:
    // code to execute if expression is equal to value2
    break;
  default:
    // code to execute if expression is not equal to any of the values
    break;
}
```
Here's an example:
```typescript
let dayOfWeek: number = 3;
let dayName: string;

switch (dayOfWeek) {
  case 1:
    dayName = "Sunday";
    break;
  case 2:
    dayName = "Monday";
    break;
  case 3:
    dayName = "Tuesday";
    break;
  case 4:
    dayName = "Wednesday";
    break;
  case 5:
    dayName = "Thursday";
    break;
  case 6:
    dayName = "Friday";
    break;
  case 7:
    dayName = "Saturday";
    break;
  default:
    dayName = "Invalid day";
    break;
}

console.log(dayName);
```
These are the main types of conditional statements in TypeScript. They are used to make the code more flexible and adaptable to different scenarios.

  
</details>






## Loops in TypeScript

<details>

<summary>Click to expand</summary>

<br>

In TypeScript, loops are used to execute a block of code repeatedly. There are two main types of loops: for loops and while loops.
`For Loops`
The for loop is used to execute a block of code for a specified number of times. The basic syntax is as follows:
```typescript
for (initialization; condition; increment/decrement) {
  // code to execute
}
```
Here's an example:
```typescript
 for (let i: number = 0; i < 5; i++) {
  console.log(i);
}
 ```
 `While Loops`
The while loop is used to execute a block of code while a specified condition is true. The basic syntax is as follows:
```typescript
while (condition) {
  // code to execute
}
```
Here's an example:
```typescript
let i: number = 0;

while (i < 5) {
  console.log(i);
  i++;
}
```
`Do-While Loops`
The do-while loop is similar to the while loop, but it executes the block of code at least once, regardless of whether the condition is true or false. The basic syntax is as follows:

```typescript
do {
  // code to execute
} while (condition);
```
Here's an example:

```typescript
let i: number = 0;

do {
  console.log(i);
  i++;
} while (i < 5);
```
`For-in Loops`
The for-in loop is used to loop through the properties of an object. The basic syntax is as follows:

```typescript
for (let property in object) {
  // code to execute
}
```
Here's an example:
```typescript
let person = { name: "John", age: 30, city: "New York" };

for (let property in person) {
  console.log(property + ": " + person[property]);
}
```
</details>



### [:fast_forward: Next: OOP using TypeScript](https://github.com/dev-satri/TypeScript-Documentation/blob/main/ObjectOrientedProgramming.md)

