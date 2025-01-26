# JavaScript Comments  

Comments in JavaScript are text within the code used for making notes or disabling certain parts of the code during testing.  

### Types of Comments in JavaScript  

JavaScript has two types of comments:  

1. **Single-line comments**  
Single-line comments start with `//`. All text after `//` until the end of the line will be ignored during program execution.
**Example:**
   ```javascript
   // The following function returns the sum of the input parameters
   function sum(a,b) {
	   return a + b;
   }
   
   let a = 15; // Declaration of variable a
   let b = 25; // Declaration of variable b
	
   console.log(sum(a,b));   
   ```


2. **Multi-line comments**
Multi-line comments start with `/*` and end with `*/`. The text between `/*` and `*/` is ignored during program execution.  

**Example:**
   ```javascript
   /* 
   The following function performs the following actions:
   Calculates the sum of the input values
   Outputs the result to the console
   */   
   function sum(a,b) {
	   let c = a + b;
	   console.log(c); 
   }
   
   let a = 15; // Declaration of variable a
   let b = 25; // Declaration of variable b
   
   sum(a,b) 
   ```

## Why Use Comments in JavaScript

1. **Explaining elements in the code.** It is useful to write notes that clarify complex parts of the code. Text explanations make it easier to work with the code later, whether for yourself after a period of time or for other developers.
2. **Formal documentation of functions.** For formal documentation, there is a special syntax called [JSDoc](https://jsdoc.app/).  
3. **Testing code.** Comments are used to disable specific parts of the code without deleting them from the script.

## FAQs on JavaScript Comments

### What are single-line comments in JavaScript?  

Single-line comments in JavaScript are comments placed on one line and start with `//`.

### How to create a multi-line comment in JavaScript?

To create a multi-line comment, use `/*` to start the comment and `*/` to end it.

### Do comments affect the execution speed of a program?

No, because comments are ignored during program execution. However, they increase the document size as they add extra characters to the code.

### How to disable a code fragment without deleting it?

To prevent a specific code fragment from executing during program runtime without deleting it, you can comment it out. In the following example, the value of variable `a` will not be displayed in the console.

**Example:**
```javascript
let a = 15; // Declaration of variable a
let b = 25; // Declaration of variable b
   
//console.log(a);
console.log(b);
```

