
# TypeScript Documentation

## Data Types and Variables in TypeScript
### Declaring Variables in TypeScript
In TypeScript, variables can be declared using let, const, or var. However, let and const are recommended over var.

let: Allows variable reassignment but not redeclaration within the same scope.

const: Declares a read-only variable (cannot be reassigned).

var: Function-scoped variable (not recommended due to scoping issues).
`Example`
```
let name: string = "John";
const age: number = 30;
var city: string = "New York";
```
### Built-in Data Types
TypeScript provides several built-in data types:

1. Number

Represents numeric values (both integers and floating-point numbers).
```
let num: number = 42;
let pi: number = 3.14;
```
2. String

Represents textual data, enclosed within single ('), double ("), or backticks (` for template literals).
```
let greeting: string = "Hello, TypeScript!";
let message: string = `Welcome, ${greeting}`;
```
3. Boolean

Represents true or false values.
```
let isActive: boolean = true;
```
4. Array

Represents a collection of values of the same type.
```
let numbers: number[] = [1, 2, 3, 4, 5];
let names: Array<string> = ["Alice", "Bob", "Charlie"];
```
5. Tuple

Represents an array with fixed types at specific positions.
```
let person: [string, number] = ["Alice", 25];
```
6. Enum

Defines a set of named constants.
```
enum Color {
  Red,
  Green,
  Blue
}
let myColor: Color = Color.Green;
```
7. Any

Represents a type that can hold any value (not recommended for type safety).
```
let randomValue: any = 10;
randomValue = "Hello";
randomValue = true;
```
8. Void

Used for functions that do not return any value.
```
function logMessage(): void {
  console.log("This function returns nothing");
}
```
9. Null and Undefined

Represents absence of value.
```
let empty: null = null;
let notAssigned: undefined = undefined;
```
10. Never

Represents values that never occur, typically used for functions that throw an error.
```
function throwError(message: string): never {
  throw new Error(message);
}
```
## Type Inference
TypeScript can infer types based on the assigned value, reducing the need for explicit type annotations.
```
let inferredString = "Hello"; // TypeScript infers type as string
let inferredNumber = 42;      // TypeScript infers type as number
```
## Type Assertions
Used when you know more about a value's type than TypeScript does.
```
let someValue: any = "Hello TypeScript";
let strLength: number = (someValue as string).length;
```


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
## OOP in TypeScript
Object-oriented programming (OOP) is a programming paradigm that uses objects to represent and manipulate data. TypeScript is an object-oriented programming language that supports classes, inheritance, and other OOP features.
</br>
Here's an example of using classes in TypeScript:
```
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  sayHello(): void {
    console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
  }
}

let person1 = new Person("John", 30);
person1.sayHello(); // output: Hello, my name is John and I'm 30 years old.
```
In this example, we define a Person class with two properties (name and age) and a method (sayHello). We also define a constructor that takes two arguments (name and age) and initializes the corresponding properties.

We then create a new Person object (person1) using the new keyword and passing the required arguments to the constructor. Finally, we call the sayHello method on the person1 object, which outputs a message with the person's name and age.
</br>

Object-oriented programming (OOP) is a programming paradigm that uses objects to represent and manipulate data. TypeScript is an object-oriented programming language that supports classes, inheritance, and other OOP features.

Here's an example of using classes in TypeScript:

```
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  sayHello(): void {
    console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
  }
}

let person1 = new Person("John", 30);
person1.sayHello(); // output: Hello, my name is John and I'm 30 years old.
```
In this example, we define a Person class with two properties (name and age) and a method (sayHello). We also define a constructor that takes two arguments (name and age) and initializes the corresponding properties.

We then create a new Person object (person1) using the new keyword and passing the required arguments to the constructor. Finally, we call the sayHello method on the person1 object, which outputs a message with the person's name and age.
</br>
Here's an example of using inheritance in TypeScript:
```
class Employee extends Person {
  salary: number;

  constructor(name: string, age: number, salary: number) {
    super(name, age);
    this.salary = salary;
  }

  getSalary(): void {
    console.log(`${this.name}'s salary is ${this.salary}.`);
  }
}

let employee1 = new Employee("Jane", 25, 50000);
employee1.sayHello(); // output: Hello, my name is Jane and I'm 25 years old.
employee1.getSalary(); // output: Jane's salary is 50000.
```
In this example, we define an Employee class that extends the Person class. The Employee class has an additional property (salary) and a method (getSalary) that outputs the employee's salary.

We use the super keyword in the Employee constructor to call the parent class constructor and initialize the name and age properties. We then create a new Employee object (employee1) and call both the sayHello and getSalary methods on it, which output messages with the person's name and age, and the employee's salary, respectively.

These are just a few examples of how to use OOP in TypeScript. The language also supports other OOP features, such as access modifiers (public, private, and protected) and interfaces, which allow for more advanced and flexible programming patterns.
