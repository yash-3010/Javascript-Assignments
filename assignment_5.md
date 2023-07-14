# Topics: IIFE, call apply, bind, anonymous functions, Inner function, HOF

## Question 1: Answer

An IIFE (Immediately Invoked Function Expression) is a JavaScript function that is enclosed in parentheses and immediately invoked.

IIFEs are used in JavaScript for a few reasons:

* To prevent polluting the global namespace: When you define a function in JavaScript, it is added to the global namespace. This means that the function can be accessed from anywhere in your code. If you have a function that you only want to use in a specific part of your code, you can use an IIFE to prevent it from polluting the global namespace.
* To encapsulate code: IIFEs can be used to encapsulate code, which means that the code is not accessible from outside the IIFE. This can be useful if you want to keep your code organized or if you want to prevent other parts of your code from interfering with the code in the IIFE.
* To execute code asynchronously: IIFEs can be used to execute code asynchronously, which means that the code will not be executed until the IIFE is finished executing. This can be useful if you want to do something that takes a long time to execute, such as making a network request.

Here is an example of an IIFE:

```javascript
(function () {
  console.log("This is an IIFE");
})();
```
```console
This is an IIFE
```

## Question 2: Answer

The **bind()** method in JavaScript is used to create a new function that has the same body as the original function, but with a different this value. The **call()** and **apply()** methods are also used to create new functions with different this values, but they work in slightly different ways.

The this keyword in JavaScript refers to the object that is executing the function. When a function is called, the this value is set to the object that called the function. However, you can use the **bind()**, **call()**, and **apply()** methods to change the this value for a function.

* The **bind()** method takes two or three arguments: the first argument is the this value for the new function, and the second and third arguments are the arguments that will be passed to the new function when it is called. For example, the following code creates a new function that has the **obj** object as its this value:

```javascript
const obj = {name:"yash"};
const myFunction = function () {
  console.log(this);
};

const boundFunction = myFunction.bind(obj);

boundFunction();
```
```
{name: 'yash'}
```
* The **call()** method takes the same two or three arguments as the **bind()** method, but it passes the arguments to the new function after setting the this value. For example, the following code creates a new function that has the **obj** object as its this value, and then calls the new function with the argument "hello":
```javascript
const myFunction = function (message) {
  console.log(this, message);
};

const boundFunction = myFunction.call(obj, "hello");
const obj = {name:"yash"};
```
```
{name: 'yash'} 'hello'
```

* The **apply()** method takes the same two or three arguments as the **bind()** method, but it passes the arguments to the new function as an array. For example, the following code creates a new function that has the **obj** object as its this value, and then calls the new function with the array ["hello", "world"] as its argument:
```javascript
const obj = {name:"yash"};
const myFunction = function (message1, message2) {
  console.log(this, message1, message2);
};

const boundFunction = myFunction.apply(obj, ["Hello", "Sir"]);
```
```
{name: 'yash'} 'Hello' 'Sir'
```
**_The **bind()** method is the most flexible of the three methods, because it allows you to specify the this value for the new function explicitly. The **call()** and **apply()** methods are more specialized, and they are typically used when you want to pass arguments to the new function._**

## Question 3: Answer


A higher-order function (HOF) is a function that takes another function as an argument or returns another function as its result. HOFs are a powerful tool in JavaScript because they allow you to abstract away functionality and make your code more reusable.

Here is an example of a HOF in JavaScript:
```javascript
function map(array, callback) {
  const mappedArray = [];

  for (const element of array) {
    mappedArray.push(callback(element));
  }

  return mappedArray;
}

function square(number) {
  return number * number;
}

const array = [1, 2, 3, 4, 5];
const mappedArray = map(array, square);

console.log(mappedArray);
```
```
(5) [1, 4, 9, 16, 25]
```
The map() function is a HOF because it takes another function as an argument, the callback function. The callback function is responsible for transforming each element in the array. In this example, the callback function is the square() function, which squares each element in the array.

The map() function is different from a regular function because it can be used to abstract away functionality. In this example, the map() function abstracts away the logic for transforming each element in the array. This makes the code more reusable, because we can use the map() function with any function that we want to transform an array.

Here are some other examples of HOFs in JavaScript:

* filter()
* reduce()
* sort()
* every()
* some()

# Question 4: Answer
**Javascript**
```javascript
function multiplyBy(number) {
  return function (otherNumber) {
    return number * otherNumber;
  };
}

const multiplyByTwo = multiplyBy(2);

console.log(multiplyByTwo(5));
console.log(multiplyByTwo(10));
```
**Console**
```
10
20
```

## Question 5: Answer

**Javascript**
```javascript
function sortArray(array, ascending) {
  const sortedArray = [];

  for (const number of array) {
    sortedArray.push(number);
  }

  for (let i = 0; i < sortedArray.length - 1; i++) {
    for (let j = i + 1; j < sortedArray.length; j++) {
      if (ascending) {
        if (sortedArray[i] > sortedArray[j]) {
          const temp = sortedArray[i];
          sortedArray[i] = sortedArray[j];
          sortedArray[j] = temp;
        }
      } else {
        if (sortedArray[i] < sortedArray[j]) {
          const temp = sortedArray[i];
          sortedArray[i] = sortedArray[j];
          sortedArray[j] = temp;
        }
      }
    }
  }

  return sortedArray;
}

const array = [1, 5, 3, 2, 4];
const ascendingArray = sortArray(array, true);
const descendingArray = sortArray(array, false);

console.log(ascendingArray);
console.log(descendingArray);
```
**Console**
```
(5) [1, 2, 3, 4, 5]
(5) [5, 4, 3, 2, 1]
```