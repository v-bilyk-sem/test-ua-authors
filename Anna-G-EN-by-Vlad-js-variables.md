# JavaScript Variables

A variable is a memory cell designated for storing data. It is used to store, retrieve, and modify values of any data type.

In JavaScript, a variable can be declared using the following keywords:

- **var**; 
- **let**; 
- **const**.

To start using variables, you need to understand how to:  

- Create a variable and assign a value to it.  
- Change the value of a variable.  
- Name variables correctly according to accepted standards.  

The following sections will cover these steps and other important information with code examples.

## Declaring a Variable in JavaScript

A declaration is the process of defining a variable using a keyword and a specified name.

**Example**

```javascript
var userName;
let distance;
const SPEED_OF_LIGHT = 299792458;
```

## Variable Initialization in JavaScript

Initialization is the process of assigning an initial value when declaring a variable.

### Undefined Value

In JavaScript, a variable is automatically assigned the value `undefined` by default if no specific value is set at the time of declaration.

**Example**

```javascript
let age; // Declaration and initialization with undefined
```

## Assigning a Value to a Variable in JavaScript

Assignment is the process of giving a variable a specific value. This is done using the equals sign (`=`), which acts as the assignment operator.

**Example**

```javascript
let firstName;
firstName = "John"; // Assignment

let lastName;
lastName = "Dou"; // Assignment
```

Declaring a variable and assigning it a specific initial value.

**Example**

```javascript
let number = 10;
let description = "The best book ever";
let isOnline = true;
```

## Keywords for Declaring JavaScript Variables

### The `var` Keyword

It was the only way to declare variables from 1995 until the introduction of the ECMAScript 6 (ES6) standard in 2015. With the release of ES6, the new keywords `let` and `const` were introduced, providing more convenient and safer tools for working with variables by ensuring block scope.

Currently, the use of `var` is mostly needed for maintaining legacy systems running on older JavaScript versions or scripts in older web browsers.

**Example**

```javascript
var price = 120;
var lastname;

lastname = "Black";
```

#### Features of `var`  

##### 1. A variable declared using **var** has global or function scope.  

A variable declared outside a function block is part of the global scope, meaning it is accessible anywhere in the code.

**Example**

```javascript
var number = 120;
console.log(number); 

function printNumber() {
    console.log(number);
}

printNumber();
```

**Output**

```
120
120
```

##### 2. A variable declared inside a function is accessible within that function.

Even if the code is executed inside nested blocks, `var` ignores block scope, which applies to structures like `if`, `for`, and `while`.

**Example**

```javascript
var number = 120; 

function printResult() {
    if (number > 100) {
        var message = `The number ${number} is greater than 100.`;
    }
    console.log(message); 
}

printResult();
```

**Output**

```
The number 120 is greater than 100.
```

Variables declared with `var` can be redeclared within their scope without causing an error.

**Example**

  ```javascript
  var number = 10;
  var number = 35;

  console.log(number);
  ```
  **Output**

  ```
  35
  ```

### The `let` Keyword

Variables declared using the `let` keyword have block scope. This means they are accessible only within the block in which they are declared.  

Use the `let` keyword if the variable's value may change during program execution.  

Example of using `let`:

**Example**

```javascript
let x = 10;
let y = x + 2;
let sum = 0;

sum = x + y;
console.log(sum);
```

**Output**

```
22
```

The example, that demonstrates the block scope of variables declared with the `let` keyword.

**Example**

```javascript
let number = 150;
let message = "Hello, Jack!"; 

function printMessage() {
    if (number > 100) {
        let message = "Hello, Bob!";
        console.log(message);
    }
    console.log(message);
}

printMessage();
```

**Output**

```
Hello, Bob!
Hello, Jack!
```

### The `const` Keyword

Variables declared using the `const` keyword also have block scope.

They are immutable, meaning they are constants. When declaring a constant, you must assign a value immediately. Attempting to change the value of a constant will result in an error. 

**Example** of declaring variables with `const`:

```javascript
const PI = 3.14;
const COLOR_BLACK = "#000";
const myBirthday = "10.02.2000";
```

The example, that demonstrates what happens when trying to assign a new value to a constant.

**Example**

```javascript
const myBirthday = "10.02.2000";

myBirthday = "12.03.2000"; // TypeError: Assignment to constant variable
```

## Single Statement for Declaring Multiple Variables

Using one of the keywords `var`, `let`, or`const`, multiple variables can be declared in a single statement. In this case, they must be separated by commas, and their data types can be different.

Declaring multiple variables in one statement and on a single line:

**Example**

```javascript
let x = 10, y = 21, z = 5;
let userName = "Mykola", userAge = 15;
```

Each variable is placed on a new line.

**Example**

```javascript
let toy = "Teddy Bear", 
toyCount = 8,
price = 100;

let userName = "Mykola", 
userAge = 15;
```

### Declaring Multiple Variables Using Destructuring

Destructuring allows unpacking values from arrays or properties from objects into separate variables in a single line. It is especially useful when working with arrays and objects.

The following example with an array demonstrates that:
- On the left of the equals sign `=`, variables are described inside square brackets `[]`, indicating where array elements will be unpacked.  
- On the right, an array is specified, whose values are distributed among the variables on the left.

**Example**

```javascript
const [x, y, z] = [10, 32, 89];
let [firstName, lastName, age] = ["James", "Brown", 43];

console.log(x);
console.log(y);
console.log(lastName);
```

**Output**

```javascript
10
32
Brown
```

## JavaScript Data Types

Variables can store the following data types:
- Numbers
- Text (strings)
- Boolean values 
- Objects and other types

Strings represent text values. In JavaScript, strings can be written using double quotes (`""`), single quotes (`''`), or backticks (\`\`). Backticks allow embedding variables inside them, as demonstrated in the example with the `finalGreeting` variable.

**Example**

```javascript
let itemCount = 122; // Integer
let total = 68.12; // Floating-point number

const name = "Alya";
let greeting = 'Hi there!';
let finalGreeting = `${greeting} My name is Pavlo.`;

let hasAccess = false;

let user = { name: "Nick", age: 30 }; // Object

console.log(finalGreeting);
console.log(user);
console.log(user.age);
```

**Output**

```javascript
Hi there! My name is Pavlo.
{ name: "Nick", age: 30 }
30
```

## JavaScript Scopes

A scope defines the accessibility of variables.

JavaScript has several types of scopes:

- Global  
- Function  
- Block

### Global Scope

Variables and functions can be used throughout the entire code where they are defined. This means they are accessible in different functions, code blocks, and any other part of the program where needed.  

Variables declared with `var`, `let`, and `const` exhibit similar behavior when declared outside a block—they all belong to the global scope.

**Example**

```javascript
var globalVar = "I am a global var";
let globalLet = "I am a global let";
const globalConst = "I am a global const";

function showGlobalVariables() {
  console.log(globalVar);   
  console.log(globalLet);  
  console.log(globalConst); 
}

function modifyVariables() {
  globalVar = "Changed global var";   
  globalLet = "Changed global let";

  console.log(globalVar);  
  console.log(globalLet);  
  console.log(globalConst); 
}

showGlobalVariables();
modifyVariables();
```

**Output**

```javascript
I am a global var
I am a global let
I am a global const
Changed global var
Changed global let
I am a global const
```

### Function Scope

Function scope allows a function to have its own private space, where it can declare and use its variables. Variables defined inside a function are not accessible outside of it.

Variables declared with `var`, `let`, and `const` behave similarly when declared inside a function. Below are code examples demonstrating variables declared with these keywords.  

However, it is important to remember that variables declared with the `var` keyword ignore block scope, which applies to structures like `if`, `for`, and `while`.

**Example**

```javascript
function processStudentData() {
  var studentName = "John Doe";  
  var studentAge = 21;         
  var studentCourse = "Computer Science";

  if (studentAge > 18) {
    var status = "Adult";

    console.log(`Status inside if: ${status}`);
  }

  console.log(`Status outside if: ${status}`);
  console.log(`Student: ${studentName}, Age: ${studentAge}, Course: ${studentCourse}`);
}

processStudentDataVar();
```

**Output**

```javascript
Status inside if: Adult
Status outside if: Adult
Student: John Doe, Age: 21, Course: Computer Science
```

Example that demonstrates the scope of a variable declared with the `let` keyword.

**Example**

```javascript
function processProductData() {
  let productName = "Laptop";    
  let productQuantity = 3;       
  let productPrice = 500;        
  let totalPrice = productQuantity * productPrice;

  if (productQuantity > 2) {
    let discount = 0.1; 
    totalPrice = totalPrice * (1 - discount);

    console.log(`Discount applied inside if: ${discount * 100}%`);
  }

  // console.log(`Discount outside if: ${discount}`); // ReferenceError: discount is not defined
  console.log(`Product: ${productName}, Quantity: ${productQuantity}, Price per item: $${productPrice}`);
  console.log(`Total Price: $${totalPrice}`); 
}

processProductDataLet();
```

**Output**

```javascript
Discount applied inside if: 10%
Product: Laptop, Quantity: 3, Price per item: $500
Total Price: $1350
```

Example of variables declared using the `const` keyword.

**Example**

```javascript
function processInstrumentData() {
  const instrumentName = "Guitar";  
  const instrumentType = "String";  
  const instrumentPrice = 200;      

  console.log(`Instrument: ${instrumentName}, Type: ${instrumentType}, Price: $${instrumentPrice}`); 
}

processInstrumentDataConst();
```

**Output**

```javascript
Instrument: Guitar, Type: String, Price: $200
```

## Block Scope

Until 2015, JavaScript had only global and function scope.  

The introduction of block scope with `let` and `const` in ECMAScript 6 provided better control over the visibility of variables within code blocks. This allows writing clean, reliable code where variables are restricted to their block and cannot be accidentally modified or affect other parts of the program.  

Variables declared inside a block `{ }` are not accessible outside of it.

Variables declared inside a JavaScript function are *local* to that function. Local variables have a scope limited to the function's boundaries:

- Local variables can only be accessed inside the function where they are declared.
- Since each function has its own scope, variables with the same name can be used in different functions without conflicts.

Local variables are created when a function is called and are automatically deleted after the function completes.

**Example**

```javascript
function calculateTotal(price, quantity) {
  let total = price * quantity;
  
  if (total > 150) {
    let discount = 0.1;  
    total *= (1 - discount); 
    console.log(`Discount applied: ${discount * 100}%`);
  }

  console.log(`Total price: $${total}`);
}

calculateTotal(80, 2); 
calculateTotal(100, 2);
```

**Output**

```javascript
Total price: $160  
Discount applied: 10%
Total price: $180 
```

## Rules for Naming JavaScript Variables

When declaring variables, it is important to follow naming rules.

- A name can contain letters, numbers, the `$` symbol, and the `_` symbol.  
- The first character of a name must not be a number.  
- A variable should have a clear, meaningful name. For example, to store user data: `lastName`, `firstName`.  
- When creating a name consisting of multiple words, `camelCase` is commonly used.  
- JavaScript has a list of reserved words that cannot be used as variable names.  
- Variable names are case-sensitive. For example, `age` and `AGE` are different variables.

## JavaScript Dollar Sign `$`

In JavaScript, the dollar sign does not have a strictly defined purpose and is not used as a standard programming language operator. Its meaning is determined by its use in popular libraries and frameworks, as well as its acceptance as a valid character in variable and function names.

In JavaScript, variables that start with the dollar sign (`$`) can be used to indicate jQuery objects or to distinguish them from other types of variables.

```javascript
let $paragraphs = $('p'); // Element selected by tag type
const $element = $('#myElement'); // Element selected by ID

$element.addClass('selected'); // Adding a class
$element.removeClass('selected'); // Removing a class
```

The dollar sign is used in template literals, which were introduced in ECMAScript 6 (ES6) for convenient string interpolation and working with multi-line texts in JavaScript.  

Template literals are enclosed in backticks. They allow inserting expressions into a string using placeholders in the format `${expression}`.


**Example**

```javascript
let x = 10;
let y = 20;
let sum = `The sum of ${x} and ${y} is ${x + y}.`;
console.log(sum);
```

**Output**

```javascript
The sum of 10 and 20 is 30.
```

## JavaScript Underscore `_`  

The underscore symbol is not commonly used in JavaScript.  

It can be used to indicate a variable as private.

**Example**

```javascript
let _firstName = "Olya";
let _lastName = "Black";
```

This symbol can serve as a placeholder variable. The underscore indicates that a variable is temporary and serves a specific purpose, such as iteration or acting as a callback parameter.  

Below is an example of its usage. The function is defined using arrow function syntax and accepts any number of arguments, which are passed into the `args` array.  

The array method `args.find()` searches for the first element that meets the conditions:  

- `!isNaN(_)`. The `isNaN()` function checks whether a value is not a number (NaN). Since `!` is used, the condition checks whether the value is a number.  
- `typeof _ === "number"`. The `typeof` operator determines the type of a variable, and then it is compared to the string `"number"` to ensure the element is indeed a number.  

The underscore `_` represents each individual argument while iterating through the `args` array.

**Example**

```javascript
const findValidNumber = (...args) => 
  args.find(_ => !isNaN(_) && typeof _ === "number");
```

The same function, but with a specified variable name. This variant is more commonly used in practice.

**Example**

```javascript
const findValidNumber = (...args) => 
  args.find(arg => !isNaN(arg) && typeof arg === "number");
```

## Frequently Asked Questions About Variables in JavaScript

### 1. What is a variable in JavaScript?

It is a container that allows storing data of any type, such as strings, numbers, arrays, etc.

### 2. What is the difference between var, let, and const?

A variable declared with the `var` keyword has either function scope or global scope. It remains visible outside the block.

`let` and `const`, introduced in the ES6 standard, have block scope. They do not allow redeclaring a variable within the same scope.

The value of a variable declared with `const` cannot be changed after initialization. This keyword is used to declare immutable values.

### 3. Can the value of a variable declared with const be changed?

The value of a variable declared with `const` cannot be changed after initialization. However, if the variable contains an object or an array, its content (properties or elements) can be modified, but not the variable itself.

### 4. What is variable scope?

Scope determines where a variable is accessible in a program.
