*11-27-23*

**1.2.1**: Use attributes and methods to communicate with users,including the `type` attribute

**1.2.2**: Define **variables**, **data types**, and **scope**.

**1.2.3**: List keywords and reserved words. 

**1.2.4**: Store user input in variables and evaluate for appropriate responses using the console and built-in methods such as `alert()` and `prompt()`.

**1.2.5**: Distinguish between **concatenation** and addition 

**1.2.6**: Apply operators, including string concatenation (`+=`), strict comparison ( `===`, `!==`), matematical precedence and bitwise operaters.

**1.2.7**: Demonstrate how to use **expressions**.

**1.2.8**: Implement simple **event handlers**, including keyboard, mouse, and movile (gestures or touch) events.

---


**Objective 1.2.1**: JavaScript attributes and methods
**Objective 1.2.8**: Simple event handlers

> For any language, we need variables, data types, expressions, and operators.

```js
1+2 // expression
console.log(1+2); // 2 expressions but only 1 statement
```
# Communicating with the User

## Methods of the `window` Object:
- `alert()` method
- `prompt()` method
- `confirm()` method
## Methods of the `document` Object:
- `write()` method


*11/28/23*

# Working with Data in JavaScript

**variables**: a name space of memory

**datatype**: a definition of the type of information that a variable holds 


### JavaScript Data Types
1. primitive
2. Non-primitive

#### JavaScript Primitive Types (5)

| type | description|
|------|------------|
|`String`|Any sequence of alphanumeric characters written in quotes ( either single or double)|
|`number`|Simple numeric value written with or without decimals|
|`Boolean`|Store one of two values: true or false|
|`null`|Defines a value that DOES NOT exist|
|`undefined`|The value of a variable thats created but has NO value|


#### JavaScript Non-Primitive Data Types (2)

**Complex data types**
| type | description|
|------|------------|
|`array`|Special objects that can store more than one value at a time(a list of values)|
|`object`|Datastructures taht have their own methods and properties (values are stored as name:value pairs (kvp))|


*23-12-04*

## Declaring Variables 
| keyword | description|
|------|------------|
|`var`|declares a variable that can change; :-( hoisted|
|`let`|declares a variable that can change;  :-) not hoisted|
|`const`|declares a variable that cannot change|

```js
var name = "Scott";
let name = "Scott";

const NAME = "Scott";
```

```js
// we could change ar/let variables
name = "John";

//we cannot change const variables 
NAME = "John"; // error!
```

>[Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) allows a variable to be used before it is declared (which is really weird) hoisting variables is bad!
>>```js
>>favColor = "blue";
>>var favColor;
>>```

## Naming Variables
- should have meaningful and descriptive names {DO THIS EVERY TIME}
- JavaScript is **case-sensitive**
```js
let name; //valid
let Name; //valid
let NAME; //valid
```
>**Camel Casing** is a GOOD coding principle  (aka practice) 
>- **lower camelCase** (the first letter is lowercase)
>- **upper CamelCase** (Thefirst letter is uppercase)
```js
//a bad example
let x;
x = document.getElementById("output");

//a good example
let outputElement;
outputElement = document.getElementById("output");
```

> Variable Naming Rules: variables must ...
>   1. Variables must start with a letter or,
>   2. Variables must start with a dollar sign or,
>   3. Variables must start with an underscore
>
>```js
>let outputElement; // ok - starts with a letter
>let $outputElement; // ok - starts with a $ 
>let _outputElement; // ok - starts with an _
>```

## Variable Scope
>the scope of a variable is a region in the code from which the variable can be accessed.

```js   
//Any variables declared outside a function
//are accessible by ALL code

let name = "Scott"; // a global variable - any code can access it 

function printName(){
    console.log(name)//this works because name is a global variable 
}
//Any variables declared inside a function
//are accessible ONLY inside the function
function sayHi(){
    //msg is only accessible by the code inside this function
    let msg = "Hello, World";
    console.log(msg);
}
console.log(msg); //ERROR: because msg is local to sayHi();

```
## JavaScript Operators

### Assignment Operators

> Assign the value of the right operand to the left operand.
>
>> `=` - Assignment Operator
>>>```js
>>> x = 25;
>>>userId = "caseydiya";
>>> pi = 3.145
>>>```
>
>>`+=` - Addition Assignment Operator
>> Adds together the operands and assigns the result to the left operand.
>>>```js
>>> x = 25;
>>> x += 1;
>>> // x is now equal to 26
>>>```
>>>
>>`-=` - Subtraction Assignment Operator
>> Subtracts the right operand from the left operand and assigns the result to the left operand
>>>```js
>>> x = 25;
>>> x -= 1;
>>> // x is now equal to 24
>>>```
>
>> `*=` - Multiplication Assignment Operator
>> Multiplies together the operands and assigns the result to the left operand.
>>>```js 
>>> x = 25;
>>> x *= 2;
>>>// x is now equal to 50
>>>```
>
>>`/=` - Division Assignment Operator
>>Divides the left operand by the right operand and assigns the result to the left operand
>>>```js
>>> x = 25;
>>> x /=2;
>>> // x is now equal to 12.5
>>>```
>
>> `%=` - Modulus Assignment Operator
>>Divides the left operand by the right operand and assigns the ***remainder*** to the left operand.
>>>```js
>>> x = 25;
>>> x %= 2;
>>> // x is now equal to 1
>>>```

### Arithmetic Operators

>
>> `**` - Exponentaiation Operator
>> Returns the result of raising the first operand to the power of the second operand
>
>>`*` - Multiplication Operator
>> Returns the product of the operands
>
>>`/` - Division Operator
>> Returns the quotient of its operand where the left operand is the dividend and the right operand is the divisor
>
>> `%` - Remainder Operator
>> Returns the remainder left over when the left operand is divded by a the right operand
>
>>`+` - Addition Operator
>> Returns the sum of numeric operands or string concatenation
>
>> `-` - Subtraction Operator
>> Returns the difference between the left and right operand
>

### Logical Operators

>> `&&` - And Logical Operator
>> Evaluates to `true` when both operands are `true`
>>>```js
>>> x = 25;
>>> y = 10;
>>> z = 35;
>>> (X < y) && (y < z); // returns true
>>> (x < y) && (y < z); // returns false
>>>```
>
>>`||` - Or Logical Operator 
>> Evaluates to `true` when either operand is `true`
>>>```js
>>> x = 25;
>>> y = 10;
>>> z = 35;
>>> (X > y) || (y < z); // returns true
>>>```
>
>>`!` - Not Logical Operator
>> Evalueates to `true` if the operand is `false` and `false` if the operand is `true`
>>>```js
>>> x = 25;
>>> y = 10;
>>> !(x > y); // returns false
>>>!(x < y); // returns true
>>>```
>

### Comparison operators

>
>> `<` - Less than Operator
>> Returns `true` if the left operand is less than the right operand, and `false` otherwise
>
>>`>` - Greater than Operator
>> Returns `true` if the left operand is greater than the right operand, and `false` otherwise
>
>>`<=` - Less than or equal to operator
>> Returns `true` if the left operand is less than or equal to the right operand and `false` otherwise
>
>> `>=` - Greater than or equal to operator
>> Returns `true` if the left operand is Greater than or equal to the right operand and `false` otherwise
>
>>`instanceof` - Instanceof Operator
>> The instanceof operator tests to see if the prototype property of a constructor appears anywhere in the prototype chain of an object. The return value is a boolean value.
>
>> `in` - In Operator
>> Returns `true` if the specified property is in the specified object or its prototype chain
>

### Conditional Operators

>> `?:` - Ternary Operator
>> Evaluates to one of two different values based on a condition
>>```(condition) ? val1 : val2```
>>
>>>```js
>>> x = 25;
>>> y = 10;
>>> (x < y) ? true : false;
>>>
>>> if (x < y) {
>>>     true;
>>> }else{
>>>    false;
>>> }
>>>```

### Unary Operators

>
>> `delete` - Delete Operator
>> Removes a property from an object
>
>> `void` - void Operator
>> evaluates the given expression and then returns undefined
>
>> `typeof` - typeof operator
>> Returns a string indicating the type of the operand's value
>
>> `+` - Addition Operator
>> Returns the sum of numeric operands or string concatenation
>
>> `-` - Subtraction Operator
>> Returns the difference between the left and right operand
>
>> `~` - Bitwise NOT Operator
>> Returns a number or Bigint whose binary representation has a 1 in each bit position for which teh corresponding bit of the operand is 0, and a 0 otherwise
>
>> `!` - Not Logical Operator
>> Evalueates to `true` if the operand is `false` and `false` if the operand is `true`
>>>```js
>>> x = 25;
>>> y = 10;
>>> !(x > y); // returns false
>>>!(x < y); // returns true
>>>```
>
>> `await` - In Operator
>> Returns `true` if the specified property is in the specified object or its prototype chain
>

### Increment and Decrement Operators

>> `x++` - Post Increment Operator
>> Increments a variable by 1 after it's used
>>> ```js
>>> let x = 25;
>>> console.log(x++); // Returns 25
>>> ```
>
>> `++x` - Pre Increment operator 
>> Increments a variable by 1 before it's used
>>>```js
>>> let x = 25;
>>> console.log(++x); // Returns 26
>>>```
>
>> `x--` - Post Decrement Operator
>> Decrements a variable by 1 after it's used
>>> ```js
>>> let x = 25;
>>> console.log(x--); // Returns 25
>>> ```
>
>> `--x` - Pre Increment operator 
>> Decrements a variable by 1 before it's used
>>>```js
>>> let x = 25;
>>> console.log(--x); // Returns 26
>>>```

### Concatination vs Addition

>> The `+` operator functions differently based on the data type.
>>>```js
>>> let x = 25;
>>> let y = 25 + 1; // + performs arithmetic addition
>>> let z += 30; // += perfomrs arithmetic addition
>>>
>>> let first = "Casey"; 
>>> let last = "Diya";
>>> let name = first + last; // + performs concatenation
>>> let fullName = first; // fullName = "Casey"
>>> fullName += " ";      // fullName = "Casey " 
>>> FullName += last;     // fullName = "Casey Diya"
>>>```

### strict comparison operators

>
>> `===` - Strict equality Operator
>> checks whether its two operands are equal, returning a Boolean result. (Always considers operands of different types to be different)
>
>> `!==` - void Operator
>> checks whether its two operands are not equal, returning a Boolean result. Unlike the inequality operator, the strict inequality operator always considers operands of different types to be different. 
>

## Inline Scripting, Simple User Events, and Basic Event Handlers
>> Objective 1.2.8: Implement simple event handlers, including keyboard, mouse and mobile (gesture and touch) events
### The ```onload``` Event Handler
**The onload event is the first event that's fired by the web browser.**

```<body onload="alert('Hello World');"```

**Everywhere You Can Add a Script**
1. Inline
2. In the ```<head>``` Element
3. In the ```<body>``` Element

***Where is the proper location for loading scripts in a page?***
Inline scripts should never be used. When scripts are placed in the head, page loading may be deferred(The content is loaded AFTER the script) therefore the proper loacation for loading scripts in an HTML page is at the very bottom of the body element.


## Glossary

>**camelCase** is a common naming convention that is used in scripting languages, in which two words are placed together with no space between and the second (and sometimes first) word capitalized. In JavaScript, commonly used for variable, function, object and class names.

>**concatination** is used for joining two or more strings end-to-end

>**dot notation** is a reference used to access a property or method of an object

>**event handler** is a piece of code that processes and responds to an event by intercepting the event and associating executable code with it.

>**inline scripting** is used to place JavaScript code within an HTML tag, rather than between the file's tags

>**operand** is data that is to be operated upon or manipulated in some manner.

>**operator** is a symbol character that is used in programming expressions to instruct the program on how to store or manipulate (operate on) a value

>**parsing** is a process of analyzing the code.

>**precedence** is the order in which operators in an expression are evaluated when the expression has several operators.

>**scope** is an area in the code from where variables can be accessed.

>**variable** is a named space of meomory that holds a value. The value can change depending on a condition or information passed to the program, or by reassignment of a new variable.

>**hoisting** occurs when all variable declarations are moved to the top of their scope while interpreting. This behavior allows JavaScript variables to be used before they are even declared

>**`toFixed(num)`** is a method that converts a number into a string, and keeps only the specified number of decimals ( specified by `num`).


# Functions, Methods, and Events

## Calling a Function
### Passing Arguments to Functions
#### Passing by value
#### Passing by reference
### Returning Values from Functions

## Built-In Functions
> ```parseInt()```
>
>```parseFloat()```
>

## Methods 
Functions that are part of a class (e.g ```calcArea()``` method of the Rectangle class)

## THe ```this``` Keyword
> The ```this``` keyword refers to the **current owner** of a ***function***

## Glossary

> **argument** a value or expression containing data or code passed on to a function or procedure.

> **calling statement** a statement that transfers program execution to a subroutine, procedure, or function. WHen the subtoutine is complete, execution transfers back to the command following the call statement.

> **casting** a technique for variable control in which a variables value is changed from one data type to another

>**floating-point calculation** a calculation in which the decimal point can move as needed to account for significant digits

>**function** a named block of code that can be called when needed

>**global variable** a variable declared outside of any function, whose value can be accessed from any function or script block on the page

>**local variable** a variable declared inside of any function, whose value cannot be accessed from any function or script block on the page other than the one in which it was declared 

>**loosely typed language** a scripting or programming language that does not require the developer to declare a variable's data type and allows a variable's data type to change. JavaScript is loosley typed

> **pass by value** a mode that describes when values are passed to a function, and the function's parameters receive a copy of its arguments value.

>**pass by reference** a mode that describes when values are passed to a function, and the function's parameters recieve its arguments actual value

>**event bubbling and event capturing** these are the ways in which events are propagated in the HTML DOM, which in turn defines the order in which the elements of the DOM receive the event