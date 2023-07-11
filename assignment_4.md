**1. Given a string “Azad Ram Madiha Yash”. Return a string with the first letter of every word from the string. (Use built in methods).**
```
let myString = "Azad Ram Madiha Yash";
let wordsArray = myString.split(" ");
let newString = wordsArray.map(word => word[0]).join("");
console.log(newString);
```
**output**
```
ARMY
```
**2. Given an array [1, -4, 12, 0, -3, 29, -150]. Calculate the sum of all positive numbers (use built in array methods).**
```
 var arr=[1, -4, 12, 0, -3, 29, -150];
 var sum =arr.reduce((accu,curr)=>{
     if(curr>0)
     return accu+curr;    //if curent value is >0 returning accumulator + current value
     return accu;         // if current value is negative return accumulator
     },0);
console.log(sum);     
```
**output**
```
42
```

**3. Given an array [1, 2, 3, 4, 5]. Create a new array with the square of each element(use built in array methods).**
```
var arr=[1,2,3,4,5];
var brr=arr.map(x=>x*x);
console.log(brr);
```
**output**
```
[ 1, 4, 9, 16, 25 ]
```

**4. Given an array [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name: 'Vice-president James' }, { id: 3016, name: 'House-captain Otis' }, { id: 4818, name: 'Prefect Finneas' }]. Create an array containing just the id of every individual. (write two solution one using iterator and another using built-in method)**
by using iterator :

```
var arr= [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name: 'Vice-president James' }, { id: 3016, name: 'House-captain Otis' }, { id: 4818, name: 'Prefect Finneas' }];
var brr=[];
for(var i=0;i<arr.length;i++){
    brr.push(arr[i].id);
}
console.log(brr);
```
with the help of inbuilt method:

```
var arr= [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name: 'Vice-president James' }, { id: 3016, name: 'House-captain Otis' }, { id: 4818, name: 'Prefect Finneas' }];
var brr=arr.map(x=>x.id);
console.log(brr);
```



