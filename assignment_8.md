
**1) Create a Class AlertBox.
AlertBox:
Constructor:
take 1 variable(applicationName) and store it as an instance variable.
Methods:
showAlertBox(message) which shows an alert dialog with the message
In format “{applicationName}: {message}”.
ii) Create a new instance of AlertBox and show a message.
**
```
class AlertBox{
    constructor(applicationName){
        this.applicationName=applicationName;
    }
    showAlertBox(message){
          console.log(this.applicationName+' '+message);   
    }
}
const a=new AlertBox("Sarthak's Application");
a.showAlertBox("is running fine");
```
output:
```
Sarthak's Application is running fine
```

**2) Create a new class SuccessMessage which extends AlertBox. Override the showAlertBox method.
SuccessMessage <- AlertBox 
showAlertBox(message) - shows alert messages in this format. “{applicationName}:
Success: {message}”. Create a new instance of SuccessMessage and call the showAlertBox method.**

```
class SuccessMessage extends AlertBox{
    showAlertBox(message){
          console.log(this.applicationName+' success '+message);   
    }
}
const b=new SuccessMessage("Sarthak's Application");
b.showAlertBox('is running fine');
```
output:
```
Sarthak's Application success is running fine
```

**3) What is inheritance and prototypes? Can you achieve inheritance using prototypes If yes, how? ( Give examples )**

1.Class-Based Inheritance (ES6):
In modern JavaScript (ES6 and later), you can use the class syntax to implement class-based inheritance. This approach provides a more familiar and syntactically cleaner way to define classes and their inheritance relationships.

```
// Class-based inheritance (ES6)
class Animal {
  constructor(name) {
    this.name = name;
  }

  sayHello() {
    console.log(`Hello, I'm ${this.name}`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  bark() {
    console.log('Woof! Woof!');
  }
}

const animal = new Animal('Generic Animal');
const dog = new Dog('Buddy', 'Golden Retriever');

animal.sayHello(); // Output: Hello, I'm Generic Animal
dog.sayHello();    // Output: Hello, I'm Buddy
dog.bark();        // Output: Woof! Woof!
```

In this example, we use the class keyword to define the Animal and Dog classes. The Dog class extends the Animal class using the extends keyword. The super() function is used in the Dog constructor to call the parent class constructor and set the name property. The methods are defined within the class body directly.

2. Prototype-Based Inheritance :(Traditional JavaScript)
In traditional JavaScript, you can use prototype-based inheritance to achieve the same effect without using the class syntax.

```
// Prototype-based inheritance (Traditional JavaScript)
function Animal(name) {
  this.name = name;
}

Animal.prototype.sayHello = function() {
  console.log(`Hello, I'm ${this.name}`);
};

function Dog(name, breed) {
  Animal.call(this, name);
  this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function() {
  console.log('Woof! Woof!');
};

const animal = new Animal('Generic Animal');
const dog = new Dog('Buddy', 'Golden Retriever');

animal.sayHello(); // Output: Hello, I'm Generic Animal
dog.sayHello();    // Output: Hello, I'm Buddy
dog.bark();        // Output: Woof! Woof!
```
In this example, we use constructor functions to define the Animal and Dog classes. The Dog prototype is linked to the Animal prototype using Object.create(Animal.prototype), and we manually set the constructor property to Dog. The methods are defined on the prototypes using Animal.prototype.methodName = function().

Both examples achieve inheritance, but the difference lies in the syntax and approach. The class-based inheritance (ES6) provides a more structured and intuitive way to define classes and their relationships, while the prototype-based approach (Traditional JavaScript) offers a more direct manipulation of object prototypes. It's essential to understand both approaches, as they are both used in different codebases and libraries.