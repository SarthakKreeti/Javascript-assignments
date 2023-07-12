**1. What is an IIFE (Immediately Invoked Function Expression) and why would you use it in JavaScript? Give an example of IIFE.**
An IIFE, which stands for Immediately Invoked Function Expression, is a JavaScript design pattern that involves creating and executing a function immediately after its declaration. It is typically used to create a new scope, encapsulate variables, and avoid polluting the global namespace.

An IIFE is formed by wrapping a function expression inside parentheses and immediately invoking it using additional parentheses. This way, the function is declared and executed in a single step without needing to assign it to a variable or explicitly call it later.

Here's an example of an IIFE:

```
(function(name){
    console.log("Hello my name is "+ name);
})("sarthak");

```
**output**

```
Hello my name is sarthak
```
The benefits of using an IIFE include:

1. Encapsulation: The variables and functions defined inside the IIFE are not accessible from the outside, preventing naming conflicts with other code.
2. Isolation: The IIFE creates a new scope, allowing you to safely define temporary variables without affecting the global scope or other code.
3. Modularity: The IIFE can be used to define self-contained modules or plugins that expose only specific functions or variables to the outside world.

**2. What is the purpose of using the bind() method in JavaScript and how is it different from call() and apply()?**

The bind(), call(), and apply() methods in JavaScript are used to manipulate the this context and invoke functions with a specified context. Although they serve a similar purpose, they differ in how they handle the function invocation and passing arguments. Here's an overview of each method:

**bind():** The bind() method creates a new function with a specified this context and optional arguments. It does not immediately invoke the function but returns a new function that can be called later. The bind() method is useful when you want to set the this value for a function permanently.
Example:

```
const obj = {
  name: 'Sarthak',
  greet: function() {
    console.log('Hello, ' + this.name);
  }
};

const boundGreet = obj.greet.bind(obj);
boundGreet(); // Output: "Hello, Sarthak"

```
In this example, bind() is used to create a new function boundGreet with the this context set to the obj object. When boundGreet() is invoked, it prints "Hello, John" because the this value inside the greet function refers to obj.

**call():** The call() method invokes a function with a specified this context and individual arguments passed directly. It immediately executes the function with the provided arguments.
Example:

```
const obj = {
  name: 'Sarthak',
  greet: function(greeting) {
    console.log(greeting + ', ' + this.name);
  }
};

obj.greet.call(obj, 'hey!'); // Output: "Hey!, Sarthak"
```
In this example, call() is used to invoke the greet function with the this context set to the obj object and the argument 'Hello'. The function is executed immediately with the provided context and arguments.

**apply():** The apply() method is similar to call() but accepts an array-like object or an actual array as the second argument. It immediately executes the function with the specified this context and an array of arguments.
Example:

```
const obj = {
  name: 'Sarthak',
  greet: function(greeting) {
    console.log(greeting + ', ' + this.name);
  }
};
obj.greet.apply(obj, ['Hi! ']); // Output: "Hi! , Sarthak"
```


In this example, apply() is used to invoke the greet function with the this context set to the obj object and an array ['Hello'] as the argument. The function is executed immediately with the provided context and arguments.

Its imortant to note that , multiple arguments cannot be passed in the apply method ,as it will take only first argument in the function call , instead we can use the ```...``` operator.
```
const obj={
    name:'sarthak',
    greet: function(x,y){
        console.log(x+y+this.name)
    }
};
const arr=['hi! ','what is up '];
obj.greet.apply(obj,arr); // output: hi! what is up sarthak

```


**3. What is a Higher-Order Function (HOF) in JavaScript and how is it different from regular functions? Explain with an example.**
In JavaScript, a Higher-Order Function (HOF) is a function that takes one or more functions as arguments and/or returns a function as its result. In other words, it treats functions as values, allowing you to manipulate and operate on them.

Here are some key characteristics of Higher-Order Functions:

Accepting Functions as Arguments: A Higher-Order Function can receive one or more functions as parameters. It can then use or apply those functions within its own implementation.

Returning Functions: A Higher-Order Function can generate and return a new function as its result. This enables you to create functions dynamically or based on certain conditions.

Enhancing Abstraction and Composition: Higher-Order Functions promote abstraction and code reusability by providing a way to encapsulate common functionality in functions that can be easily composed and reused in different contexts.

Encapsulating Control Flow: Higher-Order Functions can abstract complex control flow patterns, such as loops or conditionals, into reusable functions. They allow you to pass in custom logic as functions to control the behavior of the Higher-Order Function.

Here's an example to illustrate the concept of a Higher-Order Function:
```
function multiplyBy(factor) {
  return function(number) {
    return number * factor;
  };
}

const double = multiplyBy(2);
const triple = multiplyBy(3);

console.log(double(5));  // Output: 10
console.log(triple(5));  // Output: 15
```
In this example, the multiplyBy() function is a Higher-Order Function that takes a factor argument. It returns an inner function that multiplies a given number by the factor.

When we invoke multiplyBy(2), it returns a new function that doubles any number passed to it. We assign this function to the variable double. Similarly, multiplyBy(3) returns a function that triples any number, assigned to the variable triple.

By calling double(5), we pass the number 5 to the double function, which multiplies it by 2, resulting in the output of 10. Similarly, triple(5) multiplies 5 by 3, giving the output of 15.

The Higher-Order Function multiplyBy() encapsulates the common functionality of multiplication, allowing us to generate specific multiplier functions (double, triple) on the fly. This demonstrates the ability of Higher-Order Functions to create new functions and manipulate behavior based on function inputs.


**4. Write a function called multiplyBy that takes a number as input and returns a new function that multiplies any number passed into it by the original number.**
```

const multiBy=function(factor){
    return function(number){
        return factor*number;
    }
}

const double=multiBy(2);
const triple=multiBy(3);
console.log(triple(double(10))); //output : 60
console.log(triple(30));         //output : 90
```

**5. Write a function named sortArray that takes in two parameters:** 
**1. An array of numbers**
**2. A boolean value ascending that indicates whether the array should be sorted in ascending or descending order.**
**● The sortArray function should return the sorted array. Use an anonymous function to do the actual sorting, rather than using the built-in sort method.**

using bubble sort we can perform the above task
```
 let sorted_arr=function(arr,asc){
     if(asc==true){
         for(var i=0;i<arr.length-1;i++){
             for(var j=0;j<arr.length-1-i;j++){
                 if(arr[j]>arr[j+1]){
                     var temp=arr[j];
                     arr[j]=arr[j+1];
                     arr[j+1]=temp;
                 }
             }
         }
         return arr;
     }
         for(var i=0;i<arr.length-1;i++){
             for(var j=0;j<arr.length-1-i;j++){
                 if(arr[j]<arr[j+1]){
                     var temp=arr[j];
                     arr[j]=arr[j+1];
                     arr[j+1]=temp;
                 }
             }
         }
     return arr;
 }
 arr=[1,3,5,6,2];
 sorted_arr(arr,true);
 console.log(arr);
 sorted_arr(arr,false);
 console.log(arr);
```
