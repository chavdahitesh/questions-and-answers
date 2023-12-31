# questions-and-answers

1. **Difference between `null` and `undefined`**:

   - `undefined` represents a variable that has been declared but has not been assigned a value.
   - `null` represents an intentional absence of any object value.

   ```javascript
   let x; // undefined
   let y = null; // null
   ```

2. **Closure**:

   A closure is a function that has access to its own scope, the outer (enclosing) function's scope, and the global scope. It "closes over" variables from outer scopes, allowing those variables to remain accessible even after the outer function has finished executing.

   ```javascript
   function outer() {
     let outerVar = "I am from outer!";
     function inner() {
       console.log(outerVar); // Accessing outerVar from the outer scope
     }
     return inner;
   }

   const closureFunc = outer();
   closureFunc(); // Outputs: "I am from outer!"
   ```

3. **Event Loop**:

   The event loop is a mechanism that allows JavaScript to perform non-blocking asynchronous operations. It continuously checks the message queue for tasks to execute, ensuring that the main thread remains responsive.

4. **Promises**:

   Promises are objects representing the eventual completion or failure of an asynchronous operation. They provide a more structured way to handle asynchronous code compared to callbacks.

   ```javascript
   const promise = new Promise((resolve, reject) => {
     setTimeout(() => {
       resolve("Data fetched successfully!");
     }, 1000);
   });

   promise.then((result) => {
     console.log(result); // "Data fetched successfully!"
   });
   ```

5. **Hoisting**:

   Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase.

   ```javascript
   console.log(x); // undefined
   var x = 10;
   ```

6. **`this` Keyword**:

   The `this` keyword refers to the context in which a function is executed. Its value depends on how the function is called.

   ```javascript
   const obj = {
     name: "John",
     sayName: function () {
       console.log(this.name);
     },
   };

   obj.sayName(); // "John"
   ```

7. **Callback Functions**:

   Callback functions are functions passed as arguments to other functions and are executed later, often asynchronously.

   ```javascript
   function doSomethingAsync(callback) {
     setTimeout(() => {
       console.log("Task done!");
       callback();
     }, 1000);
   }

   doSomethingAsync(() => {
     console.log("Callback executed.");
   });
   ```

8. **Arrow Functions**:

   Arrow functions are a concise way to write functions in JavaScript.

   ```javascript
   const add = (a, b) => a + b;
   ```

9. **Prototypal Inheritance**:

   JavaScript uses prototypal inheritance, where objects inherit properties and methods from other objects via their prototype chain.

   ```javascript
   function Person(name) {
     this.name = name;
   }

   Person.prototype.greet = function () {
     console.log(`Hello, my name is ${this.name}`);
   };

   const person = new Person("Alice");
   person.greet(); // "Hello, my name is Alice"
   ```

10. **`let`, `const`, and `var`**:

    - `let` and `const` are block-scoped, and `const` variables cannot be reassigned.
    - `var` is function-scoped.

    ```javascript
    let x = 10;
    const y = 20;
    var z = 30;
    ```

11. **`bind()`, `call()`, and `apply()`**:

    These methods are used to control the value of `this` when invoking a function.

    ```javascript
    const obj = { value: 42 };

    function getValue() {
      console.log(this.value);
    }

    const boundFn = getValue.bind(obj);
    boundFn(); // Outputs: 42
    ```

12. **Spread Operator (`...`)**:

    The spread operator (`...`) is used to combine the elements of arrays or merge the properties of objects.

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

13. **Higher-Order Functions**:

    Higher-order functions are functions that take other functions as arguments or return functions as results.

    ```javascript
    function multiplyBy(factor) {
      return function (x) {
        return x * factor;
      };
    }

    const double = multiplyBy(2);
    console.log(double(5)); // 10
    ```

14. **Closure (Practical Use)**:

    Closures are often used to create private variables and encapsulate data.

    Closures are powerful because they allow functions to maintain access to variables from their outer scope even when the outer function has finished executing. This enables functions to have private variables, create data privacy, and implement various design patterns like the module pattern.

    Closures are commonly used in JavaScript for tasks like creating private variables, implementing currying, and handling asynchronous operations.

    ```javascript
    function counter() {
      let count = 0;
      return function () {
        return ++count;
      };
    }

    const increment = counter();
    console.log(increment()); // 1
    ```

15. **Asynchronous Programming**:

    Asynchronous programming allows tasks to be executed without blocking the main thread.

    ```javascript
    setTimeout(() => {
      console.log("Async task completed.");
    }, 1000);
    console.log("Main thread continues...");
    ```

16. **`localStorage` vs. `sessionStorage`**:

    Both store key-value pairs but differ in scope and lifespan.

    - `localStorage` persists data until cleared by the user.
    - `sessionStorage` persists data only for the duration of a page session.
    - Typically, the storage limit for both is around 5-10 megabytes per domain.

17. **`fetch` API vs. `XMLHttpRequest`**:

    `fetch` is a modern API for making network requests and is promise-based, while `XMLHttpRequest` is older and callback-based.

18. **`==` vs. `===`**:

    `==` performs type coercion, while `===` enforces strict equality.

    ```javascript
    5 == "5"; // true (type coercion)
    5 === "5"; // false (strict equality)
    ```

19. **Handling Errors with `try...catch`**:

    `try...catch` is used to handle exceptions and errors in JavaScript.

    ```javascript
    try {
      // Code that might throw an error
      const result = undefinedVariable / 2;
    } catch (error) {
      console.error("An error occurred:", error);
    }
    ```

20. **Event Delegation**:

    Event delegation is a technique where you attach a single event listener to a common ancestor of multiple elements to handle events for all of them.

    ```javascript
    document
      .getElementById("parentElement")
      .addEventListener("click", (event) => {
        if (event.target.tagName === "LI") {
          // Handle the click on an LI element
          console.log("List item clicked:", event.target.textContent);
        }
      });
    ```

21. **Typeof null || []**

    ```javascript
    console.log(typeof null); // Output: object
    console.log(typeof []); // Output: object
    ```

    The `typeof` operator returns "object" when used with `null`, which is considered a bug in JavaScript.

22. **Event Bubbling**

    ```html
    <div id="parent">
      <div id="child">
        <button id="button">Click me</button>
      </div>
    </div>
    ```

    ```javascript
    document
      .getElementById("button")
      .addEventListener("click", function (event) {
        console.log("Button clicked");
        event.stopPropagation(); // Stop event bubbling
      });

    document.getElementById("child").addEventListener("click", function () {
      console.log("Child clicked");
    });

    document.getElementById("parent").addEventListener("click", function () {
      console.log("Parent clicked");
    });
    ```

    When the button is clicked, the event bubbles up from the child element to the parent element. Without `event.stopPropagation()`, all three event listeners would be triggered, resulting in the following output:

    ```
        Button clicked
        Child clicked
        Parent clicked
    ```

23. **Object Mutation**

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

24. **Object.freeze**

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

25. **Object.keys:**

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

26. **What is Output of belove equations and why ?**

  1) `[] == []` and `[] === []`

    These two arrays are distinct objects in memory, even though they have the same contents.
    The `==` operator checks if the two arrays reference the same object in memory, and since they do not, the comparison returns false.

    `Output->` The output of [] == [] and [] === [] is `false` because these two empty arrays are separate objects in memory.

  2) `{} == {}` and `{} === {}`
    
    The `==` operator checks for value equality for objects, which means it checks if the two objects reference the same object in memory.

    In this case, you have two separate and distinct empty objects `{}`. Even though they have the same contents (i.e., they are both empty objects), they are different objects in memory.
    
    So, both `{} == {}` and `{} === {}` will result in `false` because you are comparing two distinct empty object instances in memory.

  3) `null == undefined` and `null === undefined`

    `null == undefined:`

    The == operator checks for value equality and type coercion. In this case, null and undefined are considered equal in value and type, so null == undefined is true.
    
    `null === undefined:`
    The === operator checks for strict equality, meaning it compares both the value and the type of the operands. null and undefined have different types, so null === undefined is false.
  
  5) `0 == false` and `0 === false` 
  
    `0 == false` is true because of type coercion.
    `0 === false` is false because it checks both value and type without type coercion.

  6) `1 == "1"` && `1 === "1"`
    `1 == "1"`: This expression will return true. JavaScript will perform type coercion and convert the string "1" to a number before making the comparison, so it effectively becomes 1 == 1, which is true.

    `1 === "1"`: This expression will return false. The strict equality operator === does not perform type coercion, so it checks that 1 and "1" have different types (number and string, respectively) and therefore considers them not equal.
