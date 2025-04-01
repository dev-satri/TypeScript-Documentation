# Object-Oriented Programming (OOP) in TypeScript
### Introduction
Object-Oriented Programming (OOP) is a programming paradigm that organizes code into objects, encapsulating data and behavior. TypeScript, being a superset of JavaScript, supports OOP principles such as classes, inheritance, polymorphism, and encapsulation.

# Key OOP Concepts in TypeScript
## 1. Classes and Objects
Classes serve as blueprints for creating objects. Objects are instances of classes. 
<br><br>`code`
```typescript
class Person {
    name: string;
    age: number;
    
    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
    
    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

const person1 = new Person("John Doe", 25);
person1.greet();
```
## 2. Encapsulation
Encapsulation is the concept of restricting direct access to some components of an object, making the code more secure and modular.
**Access Modifiers in TypeScript**

| **Access Modifier** | **Scope of Access** | **Use Case / When to Use** | **Example** |
|---------------------|---------------------|----------------------------|-------------|
| **public** | Accessible from anywhere | ✅ Use when class members should be freely accessible | `public name: string;` |
| **private** | Accessible only within the same class | ✅ Use to restrict access and enforce encapsulation | `private balance: number;` |
| **protected** | Accessible within the same class and its subclasses | ✅ Use when child classes need access but not external classes | `protected calculateTax(): void {}` |
| **readonly** | Can be accessed anywhere but cannot be modified after initialization | ✅ Use for defining constants or immutable properties | `readonly id: number;` |


<br>`code`
```typescript
class BankAccount {
    private balance: number;
    
    constructor(initialBalance: number) {
        this.balance = initialBalance;
    }
    
    deposit(amount: number) {
        this.balance += amount;
    }
    
    withdraw(amount: number) {
        if (amount <= this.balance) {
            this.balance -= amount;
        } else {
            console.log("Insufficient funds.");
        }
    }
    
    getBalance(): number {
        return this.balance;
    }
}

const account = new BankAccount(1000);
account.deposit(500);
console.log(account.getBalance());
account.withdraw(2000);
```
## 3. Inheritance
Inheritance allows a class to inherit properties and methods from another class, promoting code reusability.
<br><br>`code`
```typescript
class Person {
    name: string;
    age: number;
    
    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
    
    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

const person1 = new Person("John Doe", 25);
person1.greet();
```
```typescript
class Employee extends Person {
    salary: number;
    
    constructor(name: string, age: number, salary: number) {
        super(name, age);
        this.salary = salary;
    }
    
    showSalary() {
        console.log(`${this.name} earns ${this.salary} per year.`);
    }
}

const employee1 = new Employee("Alice", 30, 50000);
employee1.greet();
employee1.showSalary();
```
## 4. Polymorphism
Polymorphism allows methods to have different implementations depending on the object that calls them.
<br><br>`code`
```typescript
class Animal {
    makeSound(): void {
        console.log("Some generic animal sound");
    }
}

class Dog extends Animal {
    makeSound(): void {
        console.log("Woof!");
    }
}

class Cat extends Animal {
    makeSound(): void {
        console.log("Meow!");
    }
}

const animals: Animal[] = [new Dog(), new Cat()];
animals.forEach(animal => animal.makeSound());
```
## 5. Abstraction
Abstraction allows defining abstract classes that serve as templates for other classes, enforcing method implementation in derived classes.
<br><br>`code`
```typescript
abstract class Vehicle {
    abstract move(): void;
}

class Car extends Vehicle {
    move(): void {
        console.log("Car is driving.");
    }
}

class Boat extends Vehicle {
    move(): void {
        console.log("Boat is sailing.");
    }
}

const vehicles: Vehicle[] = [new Car(), new Boat()];
vehicles.forEach(vehicle => vehicle.move());
```
---
# Interfaces in TypeScript OOP
## 1. Defining and Implementing an Interface
An interface defines the shape of an object and ensures that any class implementing it adheres to the contract.
<br><br>`code`
```typescript
interface Animal {
    name: string;
    makeSound(): void;
}

class Dog implements Animal {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    makeSound(): void {
        console.log("Woof!");
    }
}

const myDog = new Dog("Buddy");
myDog.makeSound(); // Output: Woof!
```
Here, the `Dog` class implements the `Animal` interface, ensuring it has both `name` and `makeSound()`.
## 2. Interfaces with Optional and Readonly Properties
- Optional properties are marked with `?`.
- Readonly properties prevent modification after initialization.

`code`
```typescript
interface Car {
    readonly brand: string;
    model: string;
    year?: number; // Optional
}

const myCar: Car = {
    brand: "Toyota",
    model: "Corolla",
};

// myCar.brand = "Honda"; // Error: Cannot assign to 'brand' because it is a read-only property.
```
## 3. Interface for Function Types
Interfaces can also define the structure of functions.
<br><br>`code`
```typescript
interface MathOperation {
    (a: number, b: number): number;
}

const add: MathOperation = (x, y) => x + y;
console.log(add(5, 3)); // Output: 8
```
## 4. Extending Interfaces
Interfaces can extend other interfaces to inherit properties.
<br><br>`code`
```typescript
interface Person {
    name: string;
    age: number;
}

interface Employee extends Person {
    jobTitle: string;
}

const employee: Employee = {
    name: "Alice",
    age: 30,
    jobTitle: "Software Engineer",
};
```
## 5. Interface vs Abstract Class
| Feature          | Interface                | Abstract Class           |
|------------------|--------------------------|--------------------------|
| Implementation   | No                       | Can have implementations |
| Inheritance      | Supports multiple        | Supports single inheritance |
| Properties       | Only declarations        | Can have implemented properties |
| Constructor      | No                       | Yes                      |
Use an interface when you only need to enforce a contract, and use an abstract class when you need partial implementations.
---
# TypeScript-Specific OOP Features
## 1. Access Modifiers

- public: Accessible from anywhere.
- private: Accessible only within the class.
- protected: Accessible within the class and subclasses.

`code`
```typescript
class Test {
    public publicVar = "I am public";
    private privateVar = "I am private";
    protected protectedVar = "I am protected";
}
```
## 2. Readonly Properties
Readonly properties can only be assigned once, either during initialization or in the constructor.
<br><br>`code`
```typescript
class User {
    readonly id: number;
    constructor(id: number) {
        this.id = id;
    }
}
```
## 3. Getters and Setters
Getters and setters allow controlled access to class properties.
<br><br>`code`
```typescript
class Rectangle {
    private _width: number;
    private _height: number;
    
    constructor(width: number, height: number) {
        this._width = width;
        this._height = height;
    }
    
    get area(): number {
        return this._width * this._height;
    }
}

const rect = new Rectangle(10, 5);
console.log(rect.area);
```
