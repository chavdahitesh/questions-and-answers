## OPPS CONCEPT

Here is a list of Object-Oriented Programming (OOP) concepts in JavaScript with simple real-life examples:

1. [Objects:](##Q1)

   Objects are instances of classes that encapsulate data and behavior.
   In real life, an object can be represented by a car. A car object would have properties like color, model, and methods like start, stop, and accelerate.

2. [Classes:](##Q2)

   Classes are blueprints for creating objects. In real life, a class can be represented by a car manufacturer.
   The class would define the common properties and behaviors that all cars produced by that manufacturer would have.

3. [Inheritance:](##Q3)

   Inheritance allows objects to inherit properties and methods from a parent class.
   In real life, we can think of a parent class as a generic vehicle class, and child classes like car, motorcycle, and bicycle inheriting properties and behaviors from the vehicle class.

4. [Encapsulation:](##Q4)

   Encapsulation is the bundling of data and methods within an object.
   In real life, think of a bank account object that encapsulates the account balance and methods like deposit and withdraw.
   The data (account balance) is hidden from direct access and can only be manipulated through the defined methods.

5. [Polymorphism:](##Q5)

   Polymorphism allows objects of different classes to be treated as if they belong to a common parent class. 
   In real life, consider a music player that can play different types of media, such as songs, podcasts, or audiobooks. 
   The music player can have a play method that can accept any type of media object and play it accordingly.

6. [Abstraction:](##Q6)

   Abstraction focuses on providing simplified interfaces to complex systems. In real life, think of a remote control for a TV.
   The remote control provides simple buttons like power, volume, and channel, abstracting the complex inner workings of the TV.

7. [Method Overriding:](##Q7)
   
   Method overriding allows a child class to provide its own implementation of a method inherited from a parent class.
   In real life, consider a shape class with a calculateArea method. The child classes like rectangle and circle can override
   the calculateArea method to provide their own specific implementations.

These are some of the key OOP concepts in JavaScript, and understanding and implementing them can help in creating well-structured, reusable, and maintainable code.


**##Q1 - Explain Objects with example**

In JavaScript, objects can be created using object literals or by using the `new` keyword with a constructor function. 
Here's an example of creating an object using object literals:

```javascript
// Creating an object using object literal
let person = {
  name: "John",
  age: 30,
  profession: "Developer"
};

// Accessing object properties
console.log(person.name); // Output: "John"
console.log(person.age); // Output: 30

// Modifying object properties
person.profession = "Designer";
console.log(person.profession); // Output: "Designer"
```

In this example, we create an object called `person` using object literal notation. The object has properties such as `name`, `age`, and `profession`, which store information about the person.

We can access the properties of the object using the dot notation (`objectName.propertyName`). 

For example, `person.name` gives us the value "John". 

We can also modify the properties of the object by assigning new values to them.


Another way to create objects in JavaScript is by using constructor functions and the `new` keyword. 

Here's an example:

```javascript
// Creating an object using constructor function
function Person(name, age, profession) {
  this.name = name;
  this.age = age;
  this.profession = profession;
}

// Creating an instance of the object
let person = new Person("John", 30, "Developer");

// Accessing object properties
console.log(person.name); // Output: "John"
console.log(person.age); // Output: 30
```

In this example, we define a constructor function `Person` that takes parameters `name`, `age`, and `profession`. 

Inside the constructor function, we use the `this` keyword to assign values to the object's properties. 

We then create an instance of the object using the `new` keyword and pass the required arguments.

We can access the properties of the object in the same way as before, using the dot notation (`objectName.propertyName`).

Both methods allow us to create and manipulate objects in JavaScript, but the constructor function approach provides a way to define a blueprint for creating multiple instances of the same object type.



**##Q2- Explain Classes with example.**

In JavaScript, the concept of classes was introduced in ECMAScript 2015 (ES6) to provide a more structured and object-oriented approach to programming. 
Classes in JavaScript are blueprints for creating objects with predefined properties and methods. 

Here's an example:

```javascript
// Defining a class
class Animal {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  makeSound() {
    console.log("The animal makes a sound");
  }
}

// Creating an instance of the class
let animal = new Animal("Leo", 5);

// Accessing class properties
console.log(animal.name); // Output: "Leo"
console.log(animal.age); // Output: 5

// Calling class methods
animal.makeSound(); // Output: "The animal makes a sound"
```

In this example, we define a class called `Animal` using the `class` keyword. 
The class has a constructor method that is called when an object is created from the class. 
The constructor method is used to initialize the object's properties (`name` and `age`) based on the arguments passed during object creation.

The class also has a method called `makeSound()` that defines the behavior of making a sound. 
When we create an instance of the class using the `new` keyword and call the `makeSound()` method, it will execute the code inside the method.

Classes in JavaScript can also have inheritance, where one class can inherit properties and methods from another class. 

Here's an example:

```javascript
// Defining a child class
class Dog extends Animal {
  constructor(name, age, breed) {
    super(name, age);
    this.breed = breed;
  }

  makeSound() {
    console.log("The dog barks");
  }
}

// Creating an instance of the child class
let dog = new Dog("Buddy", 3, "Labrador");

// Accessing inherited properties
console.log(dog.name); // Output: "Buddy"
console.log(dog.age); // Output: 3

// Calling inherited method
dog.makeSound(); // Output: "The dog barks"
```

In this example, we define a child class called `Dog` that extends the `Animal` class. 
The `Dog` class has its own constructor method that initializes the `name`, `age`, and `breed` properties. 
It also overrides the `makeSound()` method to define the behavior specific to dogs.

When we create an instance of the `Dog` class, we can access the inherited properties (`name` and `age`) from the `Animal` class using the dot notation. We can also call the inherited `makeSound()` method, which will execute the code specific to the `Dog` class.

Classes in JavaScript provide a way to create reusable and structured code, making it easier to organize and manage objects and their behavior.



**##Q3 - Explain Inheritance with example**

Inheritance is a fundamental concept in object-oriented programming that allows a class to inherit properties and methods from another class. In JavaScript, you can achieve inheritance using the `extends` keyword. Here's an example:

```javascript
// Parent class
class Animal {
  constructor(name) {
    this.name = name;
  }

  eat() {
    console.log(`${this.name} is eating.`);
  }
}

// Child class
class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  bark() {
    console.log(`${this.name} is barking.`);
  }
}

// Creating an instance of the child class
let dog = new Dog("Buddy", "Labrador");

// Accessing inherited properties and methods
console.log(dog.name); // Output: "Buddy"
dog.eat(); // Output: "Buddy is eating."
dog.bark(); // Output: "Buddy is barking."
```

In this example, we have a parent class called `Animal` and a child class called `Dog`. The `Dog` class extends the `Animal` class using the `extends` keyword, which means it inherits the properties and methods of the `Animal` class.

The `Animal` class has a constructor that takes a `name` parameter and assigns it to the `name` property. It also has an `eat()` method that logs a message indicating that the animal is eating.

The `Dog` class has its own constructor that takes a `name` and `breed` parameter. It calls the `super()` method inside its constructor to call the constructor of the parent class and pass the `name` parameter. This ensures that the `name` property is initialized in the child class. The `Dog` class also has its own `bark()` method.

When we create an instance of the `Dog` class, we can access the inherited property `name` from the `Animal` class using the dot notation. We can also call the inherited `eat()` method, as well as the `bark()` method defined in the `Dog` class.

Inheritance allows us to create a hierarchy of classes, where child classes can inherit and extend the functionality of parent classes, making code more reusable and organized.

**##Q4 - Explain Encapsulation with example**

Encapsulation is a fundamental principle in object-oriented programming that involves bundling data and methods together within a class, and controlling access to that data through methods. It helps in achieving data hiding and abstraction, allowing objects to maintain their internal state and behavior.

Here's an example to explain encapsulation in JavaScript:

```javascript
class Person {
  constructor(name, age) {
    this._name = name;
    this._age = age;
  }

  getName() {
    return this._name;
  }

  getAge() {
    return this._age;
  }

  setName(name) {
    this._name = name;
  }

  setAge(age) {
    if (age > 0) {
      this._age = age;
    }
  }
}

let person = new Person("John", 25);

console.log(person.getName()); // Output: "John"
console.log(person.getAge()); // Output: 25

person.setName("Jane");
person.setAge(-30); // This won't change the age as it's less than 0

console.log(person.getName()); // Output: "Jane"
console.log(person.getAge()); // Output: 25
```

In this example, we have a `Person` class with private properties `_name` and `_age`. These properties are prefixed with an underscore conventionally to indicate that they are intended to be private and should not be accessed directly from outside the class.

The class provides getter and setter methods (`getName()`, `getAge()`, `setName()`, `setAge()`) to access and modify the private properties. These methods act as a layer of encapsulation, allowing controlled access to the data.

When we create an instance of the `Person` class, we can use the getter methods to retrieve the values of the private properties (`_name` and `_age`). We can also use the setter methods to modify the values, applying any necessary logic or validation.

Encapsulation helps in maintaining the integrity of the object's data by preventing direct access to the private properties. It allows the class to have control over how the data is accessed and modified, ensuring that it follows the desired rules and constraints.


**##Q5 - Explain Polymorphism with example.**

Polymorphism is a concept in object-oriented programming that allows objects of different classes to be treated as objects of a common superclass. It enables you to use a single interface to represent different types of objects and perform different actions based on the specific object type.

Here's an example to explain polymorphism in JavaScript:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  makeSound() {
    console.log("Animal is making a sound.");
  }
}

class Dog extends Animal {
  makeSound() {
    console.log("Dog is barking.");
  }
}

class Cat extends Animal {
  makeSound() {
    console.log("Cat is meowing.");
  }
}

// Creating instances of different classes
let animal = new Animal("Animal");
let dog = new Dog("Buddy");
let cat = new Cat("Whiskers");

// Calling the makeSound() method on different objects
animal.makeSound(); // Output: "Animal is making a sound."
dog.makeSound(); // Output: "Dog is barking."
cat.makeSound(); // Output: "Cat is meowing."
```

In this example, we have a parent class called `Animal` and two child classes called `Dog` and `Cat`. Each class has a `makeSound()` method that outputs a specific sound based on the object type.

We create instances of the `Animal`, `Dog`, and `Cat` classes and assign them to variables `animal`, `dog`, and `cat`, respectively.

Even though the `makeSound()` method is defined in the parent class `Animal`, when we call this method on the `dog` and `cat` objects, the specific implementation of the method in the respective child classes is executed. This is polymorphism in action.

Polymorphism allows us to treat objects of different classes as if they are objects of a common superclass. It provides flexibility and extensibility to our code, allowing us to write generic code that can work with different types of objects, without needing to know their specific types at compile-time.

**##Q6 - Explain Abstraction with example.**

Abstraction is one of the fundamental concepts in object-oriented programming (OOP). 
It involves simplifying complex systems by breaking them down into smaller, more manageable parts while hiding unnecessary details. In JavaScript, abstraction is achieved through classes and objects. Let's explore abstraction with an example in JavaScript OOP.

Suppose we want to create a program to model different shapes, such as circles and rectangles, and calculate their areas.
We can use abstraction to create a base class called `Shape` that defines the common properties and methods for all shapes. Then, we can create specific shape classes like `Circle` and `Rectangle` that inherit from the `Shape` class and provide their own implementations for calculating area.

Here's an example:

```javascript
// Base class: Shape
class Shape {
  constructor() {
    this.type = "Shape";
  }

  // Abstract method to calculate area
  calculateArea() {
    throw new Error("Subclasses must implement calculateArea");
  }

  // Common method to display shape type
  displayType() {
    console.log(`This is a ${this.type}`);
  }
}

// Subclass: Circle
class Circle extends Shape {
  constructor(radius) {
    super();
    this.type = "Circle";
    this.radius = radius;
  }

  // Implementation of calculateArea for Circle
  calculateArea() {
    return Math.PI * this.radius * this.radius;
  }
}

// Subclass: Rectangle
class Rectangle extends Shape {
  constructor(width, height) {
    super();
    this.type = "Rectangle";
    this.width = width;
    this.height = height;
  }

  // Implementation of calculateArea for Rectangle
  calculateArea() {
    return this.width * this.height;
  }
}

// Create instances of Circle and Rectangle
const circle = new Circle(5);
const rectangle = new Rectangle(4, 6);

// Calculate and display areas
circle.displayType(); // Output: This is a Circle
console.log(`Area of Circle: ${circle.calculateArea()}`); // Output: Area of Circle: 78.53981633974483

rectangle.displayType(); // Output: This is a Rectangle
console.log(`Area of Rectangle: ${rectangle.calculateArea()}`); // Output: Area of Rectangle: 24
```

In this example, `Shape` serves as an abstraction of a generic shape. It defines a common method `calculateArea` as an abstract method, which is intended to be implemented by subclasses. The `Circle` and `Rectangle` subclasses inherit from `Shape` and provide their own implementations for calculating the area, thus demonstrating the concept of abstraction in JavaScript OOP.


**##Q7 - Method overriding with example.**

In JavaScript, method overriding can be achieved by defining a method with the same name in both the parent class and the child class. Here's an example:

```javascript
class Animal {
  makeSound() {
    console.log("The animal makes a sound");
  }
}

class Dog extends Animal {
  makeSound() {
    console.log("The dog barks");
  }
}

let animal = new Animal();
let dog = new Dog();

animal.makeSound(); // Output: "The animal makes a sound"
dog.makeSound(); // Output: "The dog barks"
```

In this example, we have a parent class called `Animal` with a method called `makeSound()`. 
The child class `Dog` extends the `Animal` class and overrides the `makeSound()` method with its own implementation.

When we create an object of the `Animal` class and call the `makeSound()` method, 
it will execute the implementation defined in the `Animal` class. 
However, when we create an object of the `Dog` class and call the `makeSound()` method, 
it will execute the implementation defined in the `Dog` class, overriding the implementation in the `Animal` class.



