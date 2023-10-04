# Javascript Basic Concepts.

---

## Variables in JavaScript.

---

In JavaScript, a variable is a named container for storing data values.
Variables are used to store and manage data that can be used or manipulated within a program.

1.  Var (Function-Scoped Variable):

Variables declared with var are function-scoped, which means they are accessible throughout the entire function in which they are declared.

```javascript
function example() {
  var x = 10;
  if (true) {
    var y = 20;
  }
  console.log(x); // Output: 10
  console.log(y); // Output: 20
}
example();
```

2.  Let (Block-Scoped Variable):

Variables declared with let are block-scoped, which means they are accessible only within the block in which they are declared.

```javascript
function example() {
  let x = 10;
  if (true) {
    let y = 20;
    console.log(x); // Output: 10
    console.log(y); // Output: 20
  }
  console.log(x); // Output: 10
  // console.log(y); // Error: y is not defined (outside the block)
}
example();
```

3.  Const (Block-Scoped Constant):

Variables declared with const are also block-scoped, and their values cannot be reassigned after they are declared. However, they can still be modified if they hold reference types like objects or arrays.

```javascript
const pi = 3.14;
// pi = 3.14159; // Error: Assignment to a constant variable
const person = { name: "John" };
person.age = 30; // Allowed (modifying object properties)
console.log(person); // Output: { name: 'John', age: 30 }
```

---

## Key differences between `let`, `var` and `const`.

---

In JavaScript, `let`, `var`, and `const` are used to declare variables, but they have different behaviors and scopes. Here's a summary of the key differences between them:

1. **Scope:**

   - `var`: Variables declared with `var` are function-scoped. They are accessible throughout the entire function in which they are declared.

   - `let` and `const`: Variables declared with `let` and `const` are block-scoped. They are accessible only within the block (e.g., within curly braces `{}`) in which they are declared.

   ```javascript
   function example() {
     if (true) {
       var x = 10;
       let y = 20;
       const z = 30;
     }
     console.log(x); // 10 (var is function-scoped)
     // console.log(y); // ReferenceError: y is not defined (let is block-scoped)
     // console.log(z); // ReferenceError: z is not defined (const is block-scoped)
   }
   ```

2. **Hoisting:**

   - `var` variables are hoisted, which means their declarations are moved to the top of their containing function or global scope during compilation. However, only the declarations are hoisted, not the initializations.

   - `let` and `const` variables are also hoisted but not initialized. This means you can't access their values before the line where they are declared.

   ```javascript
   console.log(x); // undefined
   var x = 10;

   console.log(y); // ReferenceError: y is not defined
   let y = 20;
   ```

3. **Reassignment:**

   - `var` and `let` variables can be reassigned to new values.

   ```javascript
   var a = 10;
   a = 20; // Valid

   let b = 30;
   b = 40; // Valid
   ```

   - `const` variables cannot be reassigned to new values after they are declared. However, for objects and arrays declared with `const`, you can modify their properties or elements.

   ```javascript
   const c = 50;
   // c = 60; // Error: Assignment to a constant variable

   const person = { name: "John" };
   person.age = 30; // Allowed (modifying object properties)
   ```

4. **Temporal Dead Zone (TDZ):**

   - Variables declared with `let` and `const` are subject to the Temporal Dead Zone (TDZ), which means you cannot access them before their declaration. This can lead to ReferenceErrors if you try to use them too early in the code.

   ```javascript
   console.log(x); // undefined
   var x = 10;

   // console.log(y); // ReferenceError: Cannot access 'y' before initialization
   let y = 20;
   ```

5. **Global Object Property:**

   - Variables declared with `var` at the global level become properties of the global object (e.g., `window` in browsers).

   ```javascript
   var globalVar = "I'm global!";
   console.log(globalVar); // I'm global!
   console.log(window.globalVar); // I'm global! (in a browser)
   ```

   - `let` and `const` variables declared at the global level do not become properties of the global object.

   ```javascript
   let globalLet = "I'm global too!";
   console.log(globalLet); // I'm global too!
   console.log(window.globalLet); // undefined (in a browser)
   ```

In modern JavaScript, it's generally recommended to use `let` and `const` for variable declarations as they provide better scoping and help avoid some common programming errors associated with `var`. Use `const` for values that shouldn't be reassigned and `let` for values that may change over time.

---

## DataTypes in JavaScript.

---

In JavaScript, data types can be broadly categorized into two main categories:

    1. Primitive Data Types:
        These are simple, immutable data types that represent single values. They are stored directly in memory and are compared by their value. The primitive data types in JavaScript are:

        1. Number: Represents numeric values.
        2. String: Represents sequences of characters.
        3. Boolean: Represents true or false values.
        4. Null: Represents an intentional absence of any object or value.
        5. Undefined: Represents a variable that has been declared but hasn't been assigned a value.
        6. Symbol (ES6): Represents a unique and immutable value, often used as object property keys.
        7. BigInt (ES11): Represents large integers that can't be represented by the Number type.

    2. Non-Primitive (Reference) Data Types:
        These are more complex data types that can hold multiple values and are stored as references in memory. When you work with non-primitive types, you're actually working with references to the data stored elsewhere in memory. The non-primitive data types in JavaScript are:

        1. Object: Represents collections of key-value pairs and can hold various data types as values.
        2. Array: A specialized type of object that represents an ordered list of values.
        3. Function: A callable object that contains a block of code.
        4. Date: Represents date and time values.
        5. RegExp: Represents regular expressions used for pattern matching.
        6. Map (ES6): Represents a collection of key-value pairs with ordered keys.
        7. Set (ES6): Represents a collection of unique values.
        8. WeakMap (ES6): Similar to Map, but with weaker references to keys, allowing for garbage collection.
        9. WeakSet (ES6): Similar to Set, but with weaker references to values, allowing for garbage collection.

JavaScript is a dynamically typed language, which means that variables can hold values of different data types, and the data type of a variable can change during the execution of a program.

Here are some of the common data types in JavaScript, along with examples:

1. Number:-

Represents numeric values, including integers and floating-point numbers.

```javascript
var num1 = 42; // Integer
var num2 = 3.14; // Floating-point number
```

2. String:-

Represents sequences of characters enclosed in single or double quotes.

```javascript
var name = "John";
var message = "Hello, " + name + "!";
```

3. Boolean:-

Represents a true or false value.

```javascript
var isTrue = true;
var isFalse = false;
```

4. Array:-

Represents a collection of values, which can be of any data type. Arrays are indexed starting from 0.

```javascript
var colors = ["red", "green", "blue"];
var numbers = [1, 2, 3, 4, 5];
```

5. Object:-

Represents a collection of key-value pairs where the keys (properties) are strings, and the values can be of any data type.

```javascript
var person = {
  name: "Alice",
  age: 30,
  isStudent: false,
};
```

6. Null:-

Represents an intentional absence of any value or object.

```javascript
var emptyValue = null;
```

7. Undefined:-

Represents a variable that has been declared but not assigned a value, or a non-existent object property.

```javascript
var undefinedVar;
var obj = {};
var propertyValue = obj.property; // propertyValue is undefined
```

8. Function:-

Functions are first-class citizens in JavaScript and can be assigned to variables, passed as arguments, and returned from other functions.

```javascript
function add(a, b) {
  return a + b;
}

var result = add(3, 4); // result is 7
```

9. Symbol (ES6):-

Represents a unique and immutable value, often used as object property keys to avoid naming conflicts.

```javascript
var uniqueKey = Symbol("description");
```

10. BigInt (ES11):-

Represents large integers that cannot be represented by the Number data type.

```javascript
var bigIntValue = 1234567890123456789012345678901234567890n;
```

---

## Hoisting in JavaScript.

---

In JavaScript, hoisting is a behavior that occurs during the compilation phase where variable and function declarations are moved to the top of their containing scope.

This means that you can use a variable or function before it's actually declared in your code.

**_Here's an explanation of hoisting for variables and functions in JavaScript with examples:_**

1. Variable Hoisting :

Variable declarations using the var keyword are hoisted to the top of their containing function or global scope. However, only the declarations are hoisted, not the assignments.

```javascript
function hoistingExample() {
  console.log(x); // Output: undefined
  var x = 10;
  console.log(x); // Output: 10
}

hoistingExample();
```

2. Function Hoisting :

Function declarations are also hoisted to the top of their containing scope. This means you can call a function before it's declared in the code.

```javascript
hoistingExample();

function hoistingExample() {
  console.log("Hello, world!"); // Output: Hello, world!
}
```

NOTE :- It's important to note that function declarations are hoisted entirely, including both the function name and its definition.

However, function expressions (where a function is assigned to a variable) do not hoist the variable itself, only the function definition if it's declared using function

```javascript
// Function expression (not hoisted)
var myFunc = function () {
  console.log("This won't be hoisted");
};

// Function declaration (hoisted)
function myFunctionDeclaration() {
  console.log("This will be hoisted");
}
```

## Event Bubbling:

```javascript
<div id="parent">
  <div id="child">
    <button id="button">Click me</button>
  </div>
</div>
```

```html
document.getElementById("button").addEventListener("click", function(event) {
console.log("Button clicked"); event.stopPropagation(); // Stop event bubbling
}); document.getElementById("child").addEventListener("click", function() {
console.log("Child clicked"); });
document.getElementById("parent").addEventListener("click", function() {
console.log("Parent clicked"); });
```

When the button is clicked, the event bubbles up from the child element to the parent element.

Without event.stopPropagation(), all three event listeners would be triggered,
resulting in the following output:

```
    Button clicked
    Child clicked
    Parent clicked
```

## async await

The async keyword is used to declare an asynchronous function, which automatically returns a promise. Within an async function, you can use the await keyword to pause the execution of the function until a promise is resolved or rejected. The await keyword can only be used inside an async function.

Here's an example to demonstrate the usage of async/await

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = "Data received";
      resolve(data);
    }, 2000);
  });
}

async function getData() {
  try {
    const result = await fetchData();
    console.log(result); // Output: Data received
  } catch (error) {
    console.error(error);
  }
}

getData();
```

## Promise

A promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. It is a way to handle asynchronous code in a more readable and manageable way.
In JavaScript, a promise can be in one of three states:

Pending: The initial state of a promise. It is neither fulfilled nor rejected.

Fulfilled: The state of a promise when the asynchronous operation is completed successfully. In this state, the promise returns a value.

Rejected: The state of a promise when the asynchronous operation encounters an error or fails. In this state, the promise returns an error or a reason for the failure.

A promise can be created using the Promise constructor, which takes a callback function with two parameters: resolve and reject. Inside this callback function, you perform the asynchronous operation and call either resolve(value) to fulfill the promise with a value or reject(error) to reject the promise with an error.

Once a promise is created, you can chain then() and catch() methods to handle the fulfillment or rejection of the promise. The then() method is called when the promise is fulfilled, and it takes a callback function that receives the fulfilled value as an argument. The catch() method is called when the promise is rejected, and it takes a callback function that receives the rejection reason as an argument.

Here's an example of using a promise in JavaScript:

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = "Data received";
      resolve(data);
    }, 2000);
  });
}

fetchData()
  .then((data) => {
    console.log(data); // Output: Data received
  })
  .catch((error) => {
    console.error(error);
  });
```

In the above example, the fetchData() function returns a promise that resolves with the value 'Data received' after a delay of 2000 milliseconds. We chain the then() method to handle the fulfilled value and log it to the console. If an error occurs during the asynchronous operation, the catch() method is called to handle the rejection.

Promises provide a more structured and readable way to handle asynchronous code compared to traditional callbacks. They are widely used in JavaScript and are also supported in Angular for handling asynchronous operations, such as making HTTP requests or working with asynchronous APIs.

## Typeof null | [] - object

```JavaScript
 console.log(typeof null); // Output: object
 console.log(typeof []); // Output: object
```

The typeof operator returns "object" when used with null or [], which is considered a bug in JavaScript.

## Object Mutation:

```javascript
var person = {
  name: "John",
  age: 30,
};

person.age = 31;
console.log(person); // Output: { name: "John", age: 31 }

person.city = "New York";
console.log(person); // Output: { name: "John", age: 31, city: "New York" }
```

The properties of the `person` object can be modified after it is created by directly assigning new values to them.

## Object.freeze:

```javascript
var person = {
  name: "John",
  age: 30,
};

Object.freeze(person);

person.age = 31; // Modification is silently ignored
console.log(person); // Output: { name: "John", age: 30 }

person.city = "New York"; // Addition is silently ignored
console.log(person); // Output: { name: "John", age: 30 }
```

`Object.freeze()` prevents any modifications to the `person` object, making it read-only.

## Object.keys:

```javascript
var person = {
  name: "John",
  age: 30,
  city: "New York",
};

var keys = Object.keys(person);
console.log(keys); // Output: ["name", "age", "city"]
```

`Object.keys()` returns an array of property names of the `person` object. In this case, it returns `["name", "age", "city"]`.

## Spread Operators:

```javascript
var arr1 = [1, 2, 3];
var arr2 = [4, 5, 6];

var combinedArray = [...arr1, ...arr2];
console.log(combinedArray); // Output: [1, 2, 3, 4, 5, 6]

var obj1 = { name: "John" };
var obj2 = { age: 30 };

var mergedObject = { ...obj1, ...obj2 };
console.log(mergedObject); // Output: { name: "John", age: 30 }
```

The spread operator (`...`) is used to combine the elements of arrays or merge the properties of objects.
