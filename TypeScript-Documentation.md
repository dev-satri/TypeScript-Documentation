
# TypeScript Documentation

## Functions in TypeScript
In TypeScript, functions are defined using the function keyword, followed by the function name, and then the parameter list in parentheses. The function body is enclosed in curly braces, and the return type, if any, is specified after the parameter list using a colon.
`Example 1`
Function with no parameters and no return type:
```
function sayHello(): void {
  console.log("Hello!");
}
```
`Example 2`
Function with one parameter and a return type:
```
function double(number: number): number {
  return number * 2;
}
```
`Example 3`
Function with multiple parameters and a return type:
```
function addNumbers(a: number, b: number): number {
  return a + b;
}
```
`Example 4`
Function with optional parameters and a return type:
```
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
```
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
## Conditional Statements in TypeScript
In TypeScript, conditional statements are used to execute different blocks of code based on a condition. The two main types of conditional statements are the if statement and the switch statement.
`If Statement`
The if statement is used to execute a block of code if a condition is true. The basic syntax is as follows:
```
if (condition) {
  // code to execute if the condition is true
}
```
Here's an example:
```
let x: number = 10;

if (x > 5) {
  console.log("x is greater than 5");
}
```
`If-else Statement`
The if-else statement is used to execute one block of code if a condition is true and another block of code if the condition is false. The basic syntax is as follows:
```
if (condition) {
  // code to execute if the condition is true
} else {
  // code to execute if the condition is false
}
```
Here's an example:
```
let x: number = 10;

if (x > 5) {
  console.log("x is greater than 5");
} else {
  console.log("x is less than or equal to 5");
}
```
`If-else if Statement`
The if-else if statement is used to execute different blocks of code based on multiple conditions. The basic syntax is as follows:
```
if (condition1) {
  // code to execute if condition1 is true
} else if (condition2) {
  // code to execute if condition2 is true
} else {
  // code to execute if all conditions are false
}
```
Here's an example:
```
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
```
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
```
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
## Loops in TypeScript
In TypeScript, loops are used to execute a block of code repeatedly. There are two main types of loops: for loops and while loops.
`For Loops`
The for loop is used to execute a block of code for a specified number of times. The basic syntax is as follows:
```
for (initialization; condition; increment/decrement) {
  // code to execute
}
```
Here's an example:
 ```
 for (let i: number = 0; i < 5; i++) {
  console.log(i);
}
 ```
 `While Loops`
The while loop is used to execute a block of code while a specified condition is true. The basic syntax is as follows:


```
while (condition) {
  // code to execute
}
```
Here's an example:

```
let i: number = 0;

while (i < 5) {
  console.log(i);
  i++;
}
```
`Do-While Loops`
The do-while loop is similar to the while loop, but it executes the block of code at least once, regardless of whether the condition is true or false. The basic syntax is as follows:

```
do {
  // code to execute
} while (condition);
```
Here's an example:

```
let i: number = 0;

do {
  console.log(i);
  i++;
} while (i < 5);
```
`For-in Loops`
The for-in loop is used to loop through the properties of an object. The basic syntax is as follows:

```
for (let property in object) {
  // code to execute
}
```
Here's an example:
```
let person = { name: "John", age: 30, city: "New York" };

for (let property in person) {
  console.log(property + ": " + person[property]);
}
```
### [:fast_forward: Next: OOP using TypeScript](https://github.com/dev-satri/TypeScript-Documentation/blob/main/ObjectOrientedProgramming.md)

