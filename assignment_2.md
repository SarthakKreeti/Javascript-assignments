**1. If we execute this Javascript, what will the browser's console show?
var text = 'outside';
function logIt(){
console.log(text);
var text = 'inside';
};
logIt();**
```
undefined
```
The reason of undfined output is that, the declaration of the text variable inside the logIt() is hoisted at the top , which makes the value of text undefined .

**2. Write a regular expression to reverse the first and last name**

```
const fullName = "Sarthak Tiwari";
const reversedFullName = fullName.replace(/^(\w+)\s+(\w+)$/, "$2 $1");

console.log(reversedFullName); // Output: Tiwari Sarthak
```
Explanation of the regular expression:

^: Matches the start of the string.
(\w+): Matches and captures one or more word characters (letters, digits, or underscores) representing the first name.
\s+: Matches one or more whitespace characters (spaces or tabs) between the first and last names.
(\w+): Matches and captures one or more word characters representing the last name.
$: Matches the end of the string.

In the replacement part \$2 \$1, \$2 refers to the second captured group (the last name) and \$1 refers to the first captured group (the first name). So, the replace() method effectively swaps the first and last names in the fullName string, resulting in the reversedFullName variable containing the reversed order.
**3. Write a Regular expression to validate email address**
```
function check_match(s){
 const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    let a=regex.test(s);
    if(a==true){
    console.log("Email verified");
    return ;
    }
    console.log("Not an email");
    return ;
}
check_match("sarthak.tiwari@kreeti.com");
check_match("sar.tiwari20@gmail.com");
check_match("sarthak tiwari");
check_match("hello@department.company.org");
```
output:
```
Email verified
Email verified
Not an email
Email verified
```
**4. Find the Output
var x = 100;
console.log(x);
function test(){
var x = 250;
console.log(x);
if (x > 100) {
let x = 350;
console.log(x);
}
console.log(x);
}
test();
console.log(x);**
```
100
250
350
250
100
```
**explanation**
because the scope of the let x variable is inside the if block and the scope of var x is global.

**5. What is the difference of output between these two expressions? Give your reasons for it:
a. 12 == “12”
b. 12 === “12”
c. Number(12) === 12**

ans a.
```
true
```
"==" is a loose equality comparision operator which means ,it changes the data type of the two operands into a same type and then performs compariosn. 

ans b.
```
false
```
"===" is a strict equality comparision operator so it comapres the two operands in the same data type only, hence the output is false.

ans c.

```
true
```
because Number is an inbuilt class in javascript and Number(12) is an object of that class , on the other hand 12 is a numeric literal in JavaScript. It represents a numeric value but belongs to the same class.


**6. What is NaN?**

NaN stands for "Not-a-Number" and is a special value in JavaScript that represents an unrepresentable or undefined numeric value. It is a result of an operation that cannot produce a meaningful numeric result.

Here are a few key points about NaN:

1. NaN is a value of the Number data type.
NaN is considered a numeric value, but it is not equal to any other value, including itself.
2. NaN is the result of operations that involve undefined or invalid mathematical operations, such as dividing zero by zero, taking the square root of a negative number, or performing arithmetic with non-numeric operands.
3. NaN is also returned when attempting to parse a string that does not represent a valid number.
Here are some examples of NaN:

```
console.log(0/0);      // Output: NaN
console.log(Math.sqrt(-1));  // Output: NaN
console.log(parseInt('abc')); // Output: NaN
console.log(NaN === NaN);  // Output: false
```

In the first example, dividing zero by zero results in NaN. The second example attempts to calculate the square root of a negative number, which is also NaN. In the third example, trying to parse the string 'abc' as an integer results in NaN. Lastly, the comparison NaN === NaN returns false because NaN is not equal to itself.

When working with NaN, it's important to be aware that any arithmetic operation involving NaN will also result in NaN. To check if a value is NaN, you can use the isNaN() function or the Number.isNaN() method.

```
console.log(isNaN(NaN));  // Output: true
console.log(Number.isNaN(NaN));  // Output: true
```
Both isNaN() and Number.isNaN() return true if the provided value is NaN, and false otherwise.

NaN serves as a useful indicator for identifying invalid or undefined numeric values in JavaScript.