**1. What is the difference in hoisting behaviour between a function created using function declaration syntax and that created using a function expression syntax? Give an example.**
In JavaScript, hoisting is a behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. This means that you can use a variable or a function before its actual declaration in the code.

However, there is a difference in hoisting behavior between a function created using function declaration syntax and that created using a function expression syntax.

Function Declaration:
When you use the function declaration syntax, the entire function is hoisted to the top of the current scope, and you can call the function before its actual declaration in the code.
Example of function declaration hoisting:

```
// Function declaration
hoistedFunction(); // This works even before the function declaration
function hoistedFunction() {
  console.log('This is a hoisted function.');
}
```
Function Expression:
When you use the function expression syntax, only the variable declaration is hoisted to the top of the current scope, not the entire function. As a result, you cannot call the function before its actual declaration in the code.
Example of function expression hoisting:

```
try {
  nonHoistedFunction(); // This will throw an error: nonHoistedFunction is not a function
} catch (error) {
  console.error(error.message);
}

var nonHoistedFunction = function () {
  console.log('This is a non-hoisted function expression.');
};
```

**2. Write the usage of following functions operators and give an example.**
#####a. Date.now()
Date.now() is a static method in JavaScript's Date object that returns the current timestamp in milliseconds since the Unix Epoch (January 1, 1970, 00:00:00 UTC). It provides a convenient way to get the current time without having to create a new Date object.

Here's how you can use Date.now():
```
console.log(Date.now());
```
output: ```1689427548535```
#####b. ?? (nullish coalescing operator)
The nullish coalescing operator ?? allows you to select the first non-null and non-undefined value from a list of operands. It is similar to the logical OR operator ||, but it only returns the right-hand operand if the left-hand operand is null or undefined. For all other falsy values like 0, false, '' (empty string), etc., the left-hand operand will be returned.

Here's the syntax of the nullish coalescing operator:
```
leftOperand ?? rightOperand
```
Explanation:
If the leftOperand is not null or undefined, the leftOperand will be returned.
If the leftOperand is null or undefined, the rightOperand will be returned.
Examples:

Using the nullish coalescing operator:
```
const value1 = null;
const value2 = undefined;
const value3 = 0;
const value4 = '';
const value5 = 42;

const result1 = value1 ?? 'default'; // 'default'
const result2 = value2 ?? 'default'; // 'default'
const result3 = value3 ?? 'default'; // 0
const result4 = value4 ?? 'default'; // ''
const result5 = value5 ?? 'default'; // 42
```
Comparing with the logical OR operator:
```
const value6 = 0;
const value7 = '';
const result6 = value6 || 'default'; // 'default' (0 is falsy)
const result7 = value7 || 'default'; // 'default' (empty string is falsy)

const result8 = value6 ?? 'default'; // 0 (0 is not null or undefined)
const result9 = value7 ?? 'default'; // '' (empty string is not null or undefined)
```
#####c. ?. (optional chaining operator)
In JavaScript, the ?. operator is known as the "optional chaining operator." It was introduced in ECMAScript 2020 (ES11) and provides a convenient way to access properties and methods of nested objects or arrays without having to explicitly check for the existence of each level.

The optional chaining operator ?. short-circuits the expression and returns undefined if any of the nested properties or methods are null or undefined. This prevents errors from occurring when trying to access properties or methods of non-existent or nullish values.

Here's the syntax of the optional chaining operator:

```
object?.property
object?.method()
```
Explanation:

If object is null or undefined, the expression will short-circuit, and undefined will be returned.
If object is not null or undefined, the property or method access will be attempted.
Examples:

Using optional chaining to access nested properties:
```
const person = {
  name: 'John',
  address: {
    city: 'New York',
    zipcode: '10001'
  }
};

// Without optional chaining
const city1 = person.address && person.address.city;
console.log(city1); // 'New York'

// With optional chaining
const city2 = person.address?.city;
console.log(city2); // 'New York'

const city3 = person.location?.city;
console.log(city3); // undefined (location is not defined in the person object)
```
Using optional chaining to call methods:
```
javascript
Copy code
const calculator = {
  add: (a, b) => a + b,
  subtract: (a, b) => a - b
};

// Without optional chaining
const sum1 = calculator.add && calculator.add(5, 3);
console.log(sum1); // 8

// With optional chaining
const sum2 = calculator.add?.(5, 3);
console.log(sum2); // 8

const product = calculator.multiply?.(5, 3);
console.log(product); // undefined (multiply method is not defined in the calculator object)
```

#####3. Write 2 JS statements, where:
#####a. 1st one will split the words of the sentence "I love going walkies" into an array.
```
let s="I love going walkies";
let arr=s.split(' ');
console.log(arr);
```
output:
```
[ 'I', 'love', 'going', 'walkies' ]
```
#####b. 2nd one will assign the elements of the resultant array into 4 variables (in a single statement).
```
const[a,b,c,d]=arr;
console.log('a ='+a+' '+'b= '+b+' '+'c ='+c+' '+'d ='+d);
```
output:
```
a =I b= love c =going d =walkies
```
####<< Given object for Questions 4, 5 (and possibly 6)>>
```
const myObject = {
x1: "Samba",
x2: {
x3: {
x4: {},
x5: "Rails",
},
x6: {
x7: -1,
x8: [25, 8, 4, 10]
},
}
};
```
**4. For the given object, write a single line destructuring assignment to get these values:**
**a. x3 (store result in variable name y)**
```
const y=myObject.x2.x3;
console.log(y);
```
output:
```
{ x4: {}, x5: 'Rails' }
```
**b. 2nd element of x8 (use any variable name for result)**
```
const a=myObject.x2.x6.x8[1];
console.log(a);
```
output:
```
8
```
**5. Write JS code to create another object (named newObject), which contains all attributes from the given objects, and the following key value pairs:**

**a. Key: x20
Value: “Shinko”**
```
const newObject=Object.create(myObject);
newObject.x20='Shinko';
for (const key in newObject) {
  console.log(`${key}:`, newObject[key]);
}
```
output:
```
x20: Shinko
x1: Samba
x2: { x3: { x4: {}, x5: 'Rails' }, x6: { x7: -1, x8: [ 25, 8, 4, 10 ] } }
```
**b. Key: x21
Value: [5, 40, 73, 19]**
```
newObject.x21=[5, 40, 73, 19];
for (const key in newObject) {
  console.log(`${key}:`, newObject[key]);
}
```
output:
```
x20: Shinko
x21: [ [ 5, 40, 73, 19 ] ]
x1: Samba
x2: { x3: { x4: {}, x5: 'Rails' }, x6: { x7: -1, x8: [ 25, 8, 4, 10 ] } }
```
**6. Create a new array newArray , which combines elements from arrays stored inside attributes x8 and x21 of the object created in Q5.**
```
var arr1=newObject.x21;
var arr2=newObject.x2.x6.x8;
arr1=(arr1).concat(arr2);
console.log(arr1);
```
output:
```
[
   5, 40, 73, 19,
  25,  8,  4, 10
]
```

**7. For the given JS program:**
```
let aRandomNum = 37;
function f1(num) {
console.log(num * 3);
}
function f2() {
aRandomNum *= 3;
console.log(aRandomNum);
}
f1(aRandomNum);
f2();
f1(aRandomNum);
```
**a. Out of the 2 functions f1 and f2, which one is pure and which one is impure? Give reasons for the conclusion.**
f1 is a pure function because its output depends solely on its input parameter and it has no side effects.
f2 is an impure function because it modifies external state (the global variable aRandomNum).

**b. What will be the output of the program (the 3 output values)?**
```
111 // 37*3 (num=37)
111 // 37*3 (aRandom=37*3)
333 // 111*3 (since aRandom=111)
```

**8. In case of arrow functions, in which case the parenthesis for function parameters can be omitted? Give an example.**
In arrow functions, you can omit the parentheses for function parameters when the function takes only one parameter. If there are no parameters or more than one parameter, you must include the parentheses.

Here's an example of an arrow function where the parentheses can be omitted:

```
// Arrow function with one parameter (parentheses can be omitted)
const square = num => num * num;

console.log(square(5)); // Output: 25
```
In the example above, the arrow function square takes one parameter num and returns its square. Since it has only one parameter, we can omit the parentheses around num, making it a concise one-liner arrow function.

However, if the function takes multiple parameters, or if it doesn't take any parameters, you need to include the parentheses:

```
// Arrow function with multiple parameters (parentheses are required)
const add = (a, b) => a + b;

console.log(add(3, 7)); // Output: 10

// Arrow function with no parameters (parentheses are required)
const getRandomNumber = () => Math.random();

console.log(getRandomNumber()); // Output: (random number between 0 and 1)
```

**9. Can arrow functions be used as object methods? Why or why not?**
Yes, arrow functions can be used as object methods, but there are some considerations to keep in mind.

Arrow functions have a unique behavior regarding their this context. Unlike regular functions, arrow functions do not have their own this binding. Instead, they inherit the this value from the surrounding lexical scope (i.e., the context in which they were created).

This can lead to some unexpected behavior when using arrow functions as object methods, especially if you rely on the this keyword within the method. Let's take a look at an example to illustrate this:

```
const obj = {
  data: 42,
  regularFunction: function() {
    console.log(this.data);
  },
  arrowFunction: () => {
    console.log(this.data);
  }
};

obj.regularFunction(); // Output: 42
obj.arrowFunction();   // Output: undefined
```
In this example, obj is an object with two methods: regularFunction and arrowFunction. The regularFunction is a regular function and uses this to access the data property of the object correctly. On the other hand, arrowFunction is an arrow function, and when we call it, this inside the arrow function refers to the global this (if not inside any other function), and since there is no data property in the global scope, it logs undefined.

This behavior of arrow functions makes them less suitable for object methods when you need to access the object's properties or use dynamic context.

If you need to access the object's properties or want to have dynamic this context, it's better to use regular functions as object methods. However, if you don't rely on the this context and want to maintain the lexical scope of the surrounding code, arrow functions can be used effectively as object methods.