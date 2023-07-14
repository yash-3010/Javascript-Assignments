# JS (Arrays and their built in methods)

## Question 1: Answer
**Javascript**
```javascript
function firstLetter(string) {
  const words = string.split(" ");
  const firstLetters = words.map((word) => word[0]);
  return firstLetters.join(" ");
}

const string = "Azad Ram Madiha Yash";
const firstLetters = firstLetter(string);
console.log(firstLetters);
```
**Console**
```console
A R M Y
```

## Question 2: Answer
**Javascript**
```javascript
const array = [1, -4, 12, 0, -3, 29, -150];

let sum = 0;

array.forEach((number) => {
  if (number > 0) {
    sum += number;
  }
});

console.log(sum);
```
**Console**
```console
42
```

## Question 3: Answer
**Javascript**
```javascript
const array = [1, 2, 3, 4, 5];

const squaredArray = array.map((number) => number * number);

console.log(squaredArray);
```
**Console**
```console
(5) [1, 4, 9, 16, 25]
```

## Question 4: Answer

### Solution 1: Using an iterator
**Javascript**
```javascript
const array = [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name: 'Vice-president James' }, { id: 3016, name: 'House-captain Otis' }, { id: 4818, name: 'Prefect Finneas' }];

const ids = [];

for (const i=0;i<array.length;i++) {
  ids.push(i.id);
}

console.log(ids);
```
**Console**
```console
(4) [2100, 2114, 3016, 4818]
```

### Solution 2: Using a built-in method

**Javascript**
```javascript
const array = [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name: 'Vice-president James' }, { id: 3016, name: 'House-captain Otis' }, { id: 4818, name: 'Prefect Finneas' }];

const ids = array.map((person) => person.id);

console.log(ids);
```
**Console**
```console
(4) [2100, 2114, 3016, 4818]
```
