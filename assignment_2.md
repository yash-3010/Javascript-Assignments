# Topic: Scope, Hoisting, Control Structures, Regex, Numbers

## Question 1: Answer

```console
undefined
```

The function tries to log the value of the variable _text_ to the console, but the variable _text_ is not declared in the global scope, so it is _undefined_.

## Question 2: Answer

**Javascript**

```javascript
const reverseName = (name) => {
  const regex = /^(.+) (.+)$/;
  const match = regex.exec(name);
  if (match) {
    const firstName = match[1];
    const lastName = match[2];
    return `${lastName} ${firstName}`;
  } else {
    return name;
  }
};
const name = "Yash Barman";
console.log(name);
console.log(reverseName(name));
```

**Console**

```console
Yash Barman
Barman Yash
```

## Question 3: Answer

**Javascript**

```javascript
function validateEmail(email) {
  const regex = /^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$/;
  return regex.test(email);
}
const email1 = "yash.barman@kreeti.com";
const email2 = "yashbarman_kreeti";

console.log(validateEmail(email1));
console.log(validateEmail(email2));
```

**Console**

```console
true
false
```

## Question 4: Answer

**Javascript**

```javascript
var x = 100; // This is the global variable `x`.

console.log(x); // 100 - This logs the value of the global variable `x` to the console.

function test() {
  var x = 250; // This is the local variable `x` in the function `test()`.

  console.log(x); // 250 - This logs the value of the local variable `x` to the console.

  if (x > 100) {
    let x = 350; // This is the local variable `x` in the if statement.
    console.log(x); // 350 - This logs the value of the local variable `x` to the console.
  }

  console.log(x); // 250 - This logs the value of the local variable `x` to the console.
}

test();
console.log(x); // 100 - This logs the value of the global variable `x` to the console.
```

**Console**

```console
100
250
350
250
100
```

## Question 5: Answer

|    Expression     | Output |                                                                                                Reason                                                                                                |
| :---------------: | :----: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|    12 == "12"     |  true  |                    The values of the two expressions are equal, but their types are different. The == operator does not compare the types of the expressions, so it returns true.                    |
|    12 === "12"    | false  |                       The values of the two expressions are equal, but their types are different. The === operator compares the types of the expressions, so it returns false.                       |
| Number(12) === 12 |  true  | The value of the expression Number(12) is the number 12, which is the same as the value of the expression 12. The === operator compares the values and types of the expressions, so it returns true. |

## Question 6: Answer

NaN is a special value in JavaScript that stands for "Not a Number". It is used to represent a value that cannot be represented as a number.

* The NaN value is not equal to any other value, including itself. This means that if you compare NaN to any other value, the comparison will always return false.
* The NaN value is also not a number, so you cannot use it in mathematical operations. If you try to use NaN in a mathematical operation, the operation will usually return NaN.
* The NaN value is a special value that is used to represent a value that cannot be represented as a number.