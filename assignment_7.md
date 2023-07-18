# Topics: DOM, events, Ajax

## Question 1: Answer
```html
<!DOCTYPE html>
<html>
<head>
<title>Add Item to List</title>
</head>
<body>
<input type="text" id="itemInput" />
<button id="addButton">Add Item</button>
<ul id="list"></ul>
<script>
const itemInput = document.getElementById("itemInput");
const addButton = document.getElementById("addButton");
const list = document.getElementById("list");

addButton.addEventListener("click", () => {
  const item = itemInput.value;
  if (item !== "") {
    const li = document.createElement("li");
    li.textContent = item;
    list.appendChild(li);
    itemInput.value = "";
  }
});
</script>
</body>
</html>
```

## Question 2: Answer
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>JS DOM paragraph styling</title>
</head>
<body>
<p id ="text">It is a long established fact that a reader
will be distracted by the readable content of a page when
looking at its layout. </p>
<div>
<button id="jsstyle"> Style </button>
</div>
<script>
const paragraph = document.getElementById("text");
const button = document.getElementById("jsstyle");

button.addEventListener("click", () => {
  paragraph.style.fontSize = "18px";
  paragraph.style.backgroundColor = "orange";
  paragraph.style.fontFamily = "sans-serif";
});
</script>
</body>
</html>
```

## Question 3: Answer
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>Rectangle Area Calculator</title>
</head>
<body>
<h1>Rectangle Area Calculator</h1>
<input type="number" id="width" placeholder="Width" />
<input type="number" id="height" placeholder="Height" />
<button id="calculate">Calculate</button>
<p id="area"></p>
<script>
const widthInput = document.getElementById("width");
const heightInput = document.getElementById("height");
const calculateButton = document.getElementById("calculate");
const areaParagraph = document.getElementById("area");

calculateButton.addEventListener("click", () => {
  const width = widthInput.value;
  const height = heightInput.value;
  const area = width * height;
  areaParagraph.textContent = `The area of the rectangle is ${area}`;
});
</script>
</body>
</html>
```
## Question 4: Answer
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>Form Submission Alert</title>
</head>
<body>
<form action="#">
  <input type="text" name="name" placeholder="Your name" />
  <input type="email" name="email" placeholder="Your email" />
  <button type="submit">Submit</button>
</form>
<script>
const form = document.querySelector("form");

form.addEventListener("submit", (event) => {
  event.preventDefault();
  alert("Thank you for submitting your form!");
});
</script>
</body>
</html>
```
## Question 5: Answer
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>Browser Window Resize Alert</title>
</head>
<body>
<script>
window.addEventListener("resize", () => {
  alert("The browser window has been resized!");
});
</script>
</body>
</html>

```

## Question 6: Answer
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>AJAX Text File Fetch</title>
</head>
<body>
<button id="fetch">Fetch Data</button>
<p id="data"></p>
<script>
const button = document.getElementById("fetch");
const dataParagraph = document.getElementById("data");

button.addEventListener("click", () => {
  const xhr = new XMLHttpRequest();
  xhr.open("GET", "assignment_5.md", true);
  xhr.onload = () => {
    if (xhr.status === 200) {
      dataParagraph.textContent = xhr.responseText;
    } else {
      dataParagraph.textContent = "Error fetching data";
    }
  };
  xhr.send();
});
</script>
</body>
</html>

```
## Question 7: Answer
```html
<!DOCTYPE html>
<html>
<head>
<title>Fetch and Display Image from API</title>
</head>
<body>
<h1>Fetch and Display Image from API</h1>
<img id="image" />
<div>
<button id="fetch-image">Fetch Image</button>
</div>
<script>
function fetchImage() {
  var xhr = new XMLHttpRequest();

  xhr.open("GET", "https://dog.ceo/api/breeds/image/random");

  xhr.responseType = "json";

  xhr.onload = function() {
    if (xhr.status === 200) {
      var data = xhr.response;
      var img = document.getElementById("image");
      img.src = data.message;
    } else {
      console.log("Error fetching image.");
    }
  };
  xhr.send();
}
var button = document.getElementById("fetch-image");
button.addEventListener("click", fetchImage);

</script>
</body>
</html>

```