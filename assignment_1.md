**1. Write a program that declares a variable using var, let, and const and prints
the value to the console.**

```
var x="Sarthak Tiwari";
console.log(x);
const y=45;
console.log(y);
let b=3.45;
console.log(b);
```
**output**
```
Sarthak Tiwari
45
3.45

```
**2. Write a program that reassigns a value to a variable declared with let and
prints the new value to the console**.
```
let b=3.45;
b=4;
console.log(b);
```
**output**
```
4
```

**3. Write a program that tries to reassign a value to a variable declared with
const and prints the message to the console**
```
const b=3.45;
b=4;
console.log(b);
```
**output**
```
ERROR!
/tmp/AWQZILMtT0.js:2
b=4;
 ^

TypeError: Assignment to constant variable.
    at Object.<anonymous> (/tmp/AWQZILMtT0.js:2:2)
    at Module._compile (node:internal/modules/cjs/loader:1254:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1308:10)
    at Module.load (node:internal/modules/cjs/loader:1117:32)
    at Module._load (node:internal/modules/cjs/loader:958:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47
```
**4. Write a program to declare a const, let, var variable within an if statement and
try to access the variable outside the if block, what is the result?**

1.var declaration:
```
if(true){
var x="Sarthak Tiwari";
}
console.log(x);
```
**output**
```
Sarthak Tiwari
```
2.const declaration:
```
if(true){
const y=45;
}
console.log(y);
```
**output**
```
console.log(y);
            ^

ReferenceError: y is not defined
    at Object.<anonymous> (/tmp/AWQZILMtT0.js:8:13)
    at Module._compile (node:internal/modules/cjs/loader:1254:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1308:10)
    at Module.load (node:internal/modules/cjs/loader:1117:32)
    at Module._load (node:internal/modules/cjs/loader:958:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47
```
3.let declaration:
```
if(true){
let b=3.45;
}
console.log(b);
```
**output**
```
ERROR!
/tmp/AWQZILMtT0.js:5
console.log(b);
            ^

ReferenceError: b is not defined
    at Object.<anonymous> (/tmp/AWQZILMtT0.js:5:13)
    at Module._compile (node:internal/modules/cjs/loader:1254:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1308:10)
    at Module.load (node:internal/modules/cjs/loader:1117:32)
    at Module._load (node:internal/modules/cjs/loader:958:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47
```
**3. Write a program that tries to reassign a value to a variable declared with
const and prints the message to the console**
```
const b=3.45;
b=4;
console.log(b);
```
**output**
```
ERROR!
/tmp/AWQZILMtT0.js:2
b=4;
 ^

TypeError: Assignment to constant variable.
    at Object.<anonymous> (/tmp/AWQZILMtT0.js:2:2)
    at Module._compile (node:internal/modules/cjs/loader:1254:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1308:10)
    at Module.load (node:internal/modules/cjs/loader:1117:32)
    at Module._load (node:internal/modules/cjs/loader:958:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47
```

**5. Write a program that concatenates two or more strings and prints the result to
the console.**
```
let s1 = "Sarthak";
let s2 = "Tiwari";
let s3=s1+" "+s2;
console.log(s3);
```
**output**
```
Sarthak Tiwari
```
**6. Write a program that takes a string as input and prints the length of the string to the console.**
```
let s1 = "Sarthak";
console.log(s1.length);
```
**output**
```
7
```

**7. Write a program that converts a string to uppercase and prints the result to
the console.**
```
let s1 = "Sarthak";
console.log(s1.toUpperCase());
```
**output**
```
SARTHAK
```
