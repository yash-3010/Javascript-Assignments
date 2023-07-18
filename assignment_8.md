# Inheritance, prototype, class, objects, new keyword

## Question 1: Answer
* a.
```javascript
class AlertBox {
  constructor(applicationName) {
    this.applicationName = applicationName;
  }

  showAlertBox(message) {
    const alertMessage = `${this.applicationName}: ${message}`;
    alert(alertMessage);
  }
}
```
* b.
```javascript
const alertBox = new AlertBox("My Application");
alertBox.showAlertBox("This is an alert message");
```

## Question 2: Answer
```javascript
class AlertBox {
  constructor(applicationName) {
    this.applicationName = applicationName;
  }

  showAlertBox(message) {
    const alertMessage = `${this.applicationName}: ${message}`;
    alert(alertMessage);
  }
}

class SuccessMessage extends AlertBox {
  showAlertBox(message) {
    const alertMessage = `${this.applicationName}: Success: ${message}`;
    alert(alertMessage);
  }
}

const successMessage = new SuccessMessage("My Application");
successMessage.showAlertBox("This is a success message");
```

## Question 3: Answer
```javascript
// Base constructor function
// Animal constructor function, initializes 'name' property for any animal.
function Animal(name) {
  this.name = name;
}

// 'speak' method for Animal prototype, logs animal sound.
Animal.prototype.speak = function () {
  console.log(`${this.name} makes a sound.`);
};

// Dog constructor function, extends Animal, sets 'breed' property.
function Dog(name, breed) {
  Animal.call(this, name); // Call Animal constructor to set 'name'.
  this.breed = breed; // Set 'breed' property for the Dog.
}

// Set Dog prototype to inherit from Animal prototype.
Dog.prototype = Object.create(Animal.prototype);

// Correct Dog prototype's constructor property to point to Dog.
Dog.prototype.constructor = Dog;

// Override 'speak' method for Dog prototype, specific to dogs.
Dog.prototype.speak = function () {
  console.log(`${this.name} barks loudly!`);
};

// Test
const dog1 = new Dog("Tommy", "Labrador"); // Create a Dog instance.
dog1.speak(); // Output: "Tommy barks loudly!" - Call Dog-specific 'speak' method.


```
