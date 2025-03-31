# Object-Oriented Programming (OOP) in TypeScript
### Introduction
Object-Oriented Programming (OOP) is a programming paradigm that organizes code into objects, encapsulating data and behavior. TypeScript, being a superset of JavaScript, supports OOP principles such as classes, inheritance, polymorphism, and encapsulation.

# Key OOP Concepts in TypeScript
## 1. Classes and Objects
Classes serve as blueprints for creating objects. Objects are instances of classes.
```
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
```
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
```
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
```
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
```
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
### 5. Abstraction
Abstraction allows defining abstract classes that serve as templates for other classes, enforcing method implementation in derived classes.
```
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
# TypeScript-Specific OOP Features
## 1. Access Modifiers

- public: Accessible from anywhere.
- private: Accessible only within the class.
- protected: Accessible within the class and subclasses.
```
class Test {
    public publicVar = "I am public";
    private privateVar = "I am private";
    protected protectedVar = "I am protected";
}
```
## 2. Readonly Properties
Readonly properties can only be assigned once, either during initialization or in the constructor.
```
class User {
    readonly id: number;
    constructor(id: number) {
        this.id = id;
    }
}
```
## 3. Getters and Setters
Getters and setters allow controlled access to class properties.
```
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
