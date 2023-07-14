# Topics: Data types, variables, and Strings

## Question 1: Answer

**Javascript**
```javascript
var var_variable = "This is a variable declared using var";
console.log(var_variable);

let let_variable = "This is a variable declared using let";
console.log(let_variable);

const const_variable = "This is a variable declared using const";
console.log(const_variable);
```
**Console**
```console
This is a variable declared using var
This is a variable declared using let
This is a variable declared using const
```

## Question 2: Answer

**Javascript**
```javascript
let my_var = "This is the initial value";
console.log(my_var);

my_var = "This is the new value";
console.log(my_var);

```
**Console**
```console
This is the initial value
This is the new value
```

## Question 3: Answer

**Javascript**
```javascript
const my_const = "This is the initial value";
console.log(my_const);

my_const = "This is the new value";
console.log(my_const);

```
**Console**
```console
This is the initial value
Uncaught TypeError: Assignment to constant variable.
    at <anonymous>:4:10
```

## Question 4: Answer

**Javascript**
```javascript
if (true) {
  const const_var = "This is a const variable";
  var var_var = "This is a var variable";
  let let_var = "This is a let variable";
}
console.log(var_var);

console.log(const_var);

console.log(let_var);

```
**Console**
```console
This is a var variable
Uncaught ReferenceError: const_var is not defined
    at <anonymous>:8:13
```
```console
Uncaught ReferenceError: let_var is not defined
    at <anonymous>:8:13
```

## Question 5: Answer

**Javascript**
```javascript
const string1 = "This is ";
const string2 = "a string ";
const string3 = "concatenated.";
const concatenated_string = string1 + string2 + string3;
console.log(concatenated_string);

```
**Console**
```console
This is a string concatenated.
```
## Question 6: Answer

**Javascript**
```javascript
const string = prompt("Enter a string: ");
const length = string.length;
console.log("The length of the string is: " + length);
```
* Entered "Yash"

**Console**
```console
The length of the string is: 4
```
## Question 7: Answer

**Javascript**
```javascript
const string = "yash barman";
console.log(string);
const uppercase_string = string.toUpperCase();
console.log(uppercase_string);

```
**Console**
```console
yash barman
YASH BARMAN
```