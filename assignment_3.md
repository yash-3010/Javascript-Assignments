## Question 1: Answer

`Function declaration syntax` is the most common way to declare a function. It uses the `function` keyword followed by the function name, the parameters, and the body of the function. For example:
```
function hoistedFunction() {
  console.log('This is a hoisted function.');
}
```
`Function expression syntax` is less common, but it can be useful in some cases. It uses the `function` keyword followed by the body of the function, and the function name is assigned to a variable. For example:
```
var nonHoistedFunction = function() {
  console.log('This is not a hoisted function.');
};
```
The difference in hoisting behavior between function declaration syntax and function expression syntax is that `function declarations are hoisted, but function expressions are not`. This means that a function declaration will be available to the rest of the code even if it is declared after it is used, but a function expression will not be available until it is assigned to a variable.
```javascript
hoistedFunction();
nonHoistedFunction();

function hoistedFunction() {
  console.log('This is a hoisted function.');
}

var nonHoistedFunction = function() {
  console.log('This is not a hoisted function.');
};
```
```
This is a hoisted function.
Uncaught TypeError: nonHoistedFunction is not a function
```

## Question 2: Answer
* Date.now()
`The Date.now()` function returns the current time in milliseconds. For example:
```javascript
const now = Date.now();
console.log(now);
```
*  ?? (nullish coalescing operator)
The `??` operator is a new operator in JavaScript it is used to provide a default value when an expression evaluates to `null` or `undefined`. For example:
```javascript
const name = "Yash";
const age = null;

const greeting = name ?? "Hello, stranger!";
console.log(greeting); // Yash

const greeting2 = age ?? "This field is null or undefined";
console.log(greeting2); // This field is null or undefined

```
*  ?. (optional chaining operator)
The `?.` operator is another new operator in JavaScript it is used to chain method calls on an object even if the object is null or undefined. For example:
```javascript
const user = {
  name: "Yash",
  age: 22,
};

const greeting = user?.name?.toUpperCase();
console.log(greeting); // Yash
```

## Question 3: Answer
```javascript
const sentence = "I love going walkies";
const words = sentence.split(" ");
const [variable_1, variable_2, variable_3, variable_4] = words;
console.log(variable_1,variable_2,variable_3,variable_4);
```
```
I love going walkies
```
This code will split the sentence into an array of words using the `split()` method. The `split()` method takes a delimiter as an argument and returns an array of the words in the string, separated by the delimiter. In this case, the delimiter is the space character.
Then code will assign the elements of the words array to the four variables `variable_1`, `variable_2`, `variable_3`, and `variable_4` in a single statement. The `[]` syntax is called the "array destructuring" syntax. It allows us to assign the elements of an array to multiple variables in a single statement.

## Question 4: Answer
```javascript
const myObject = {
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails",
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10],
    },
  },
};

const y = myObject.x2.x3;
const secondElement = myObject.x2.x6.x8[1];

console.log(y);
console.log(secondElement);
```
## Question 5: Answer
```javascript
const myObject = {
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails",
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10],
    },
  },
};

const newObject = {
  ...myObject,
  x20: "Shinko",
  x21: [5, 40, 73, 19],
};
console.log(newObject);
```
## Question 6: Answer
```javascript
const myObject = {
  x1: "Samba",
  x2: {
    x3: {
      x4: {},
      x5: "Rails",
    },
    x6: {
      x7: -1,
      x8: [25, 8, 4, 10],
    },
  },
};

const newObject = {
  ...myObject,
  x20: "Shinko",
  x21: [5, 40, 73, 19],
};
const newArray = newObject.x2.x6.x8.concat(newObject.x21);
console.log(newArray); // (8) [25, 8, 4, 10, 5, 40, 73, 19]
```

## Question 7: Answer
* a. Function `f1` is pure, while function `f2` is impure.

Function `f1` is pure because it only depends on its input parameter num and does not modify the state of the application or have side effects. The output of `f1` will always be the same for the same input parameter.
Function `f2` is impure because it modifies the state of the application by changing the value of `aRandomNum`. The output of `f2` will depend on the value of `aRandomNum` at the time it is called.

* b. 
```
111
111
333
```
* The first call to `f1(aRandomNum)` passes the initial value of `aRandomNum`, which is 37. It logs the result of the calculation `37 * 3`, which is 111.
* Then, the call to `f2()` modifies the value of `aRandomNum` by multiplying it with 3, making it 111. It logs the new value of `aRandomNum`, which is also 111.
* Finally, the second call to `f1(aRandomNum)` passes the updated value of `aRandomNum`, which is 111. It performs the calculation `111 * 3` and logs the result, which is 333.

## Question 8: Answer

In JavaScript, the parenthesis for function parameters can be omitted in arrow functions if there is only one parameter. For example:
```javascript
const myFunction = x => x + 1;
console.log(myFunction(2)); //3
```

## Question 9: Answer
Arrow functions can not be used as object methods. This is because arrow functions do not have their own `this` binding. The `this` binding in an arrow function is the same as the `this` binding in the enclosing lexical scope. In the case of an object method, the `this` binding should be the object itself.

* For example:
```javascript
const myObject = {
    value:"I am value",
  firstMethod: () => {
    console.log(this.value);
  },
  secondMethod () {
    console.log(this.value);
  },
};
console.log(myObject.firstMethod()); // I am value
console.log(myObject.secondMethod()); // undefined
```
