# JQUERY

## Question 1: Answer
```html
<!DOCTYPE html>
<html>
<head>
  <title>Change Background Color on Button Click</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <button id="clickMe">Click Me</button>

  <script>
    $(document).ready(function() {
      $("#clickMe").click(function() {
        $("body").css("background-color", "red");
      });
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
  <title>Append Text using jQuery</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <p id="myPara">This is the original paragraph.</p>
  <p id="newPara">This is the new paragraph.</p>

  <script>
    $(document).ready(function() {
      const originalText = $("#myPara").text();
      $("#newPara").append(originalText);
    });
  </script>
</body>
</html>

```

## Qusetion 3: Answer
```html
<!DOCTYPE html>
<html>
<head>
  <title>Form with jQuery Submission</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <form id="myForm">
    <input type="text" id="myInput" placeholder="Enter text...">
    <input type="submit" value="Submit">
  </form>

  <script>
    $(document).ready(function() {
      $("#myForm").submit(function(event) {
        event.preventDefault();
        const inputText = $("#myInput").val();
        alert("You entered: " + inputText);
      });
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
  <title>Highlight First and Last List Items with jQuery</title>
  <style>
    .highlighted {
      color: red;
    }
  </style>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <ul id="myList">
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
    <li>Item 5</li>
  </ul>

  <script>
    $(document).ready(function() {
      const $firstItem = $("#myList li:first");
      const $lastItem = $("#myList li:last");
      $firstItem.addClass("highlighted");
      $lastItem.addClass("highlighted");
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
  <title>Add Row to Table with jQuery</title>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <table id="myTable">
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>Occupation</th>
    </tr>
  </table>

  <script>
    $(document).ready(function() {
      function addRowToTable(name, age, occupation) {
        const newRow = $("<tr></tr>");
        newRow.append(`<td>${name}</td>`);
        newRow.append(`<td>${age}</td>`);
        newRow.append(`<td>${occupation}</td>`);
        $("#myTable").append(newRow);
      }

      addRowToTable("John", "30", "Developer");
    });
  </script>
</body>
</html>

```