**1. Write a JavaScript program that adds a new item to the list whenever a user inputs a text into the input field and clicks the button.**

here is the **index.html** file where we will apply our javascript program
```
<!DOCTYPE html>
<html>
<head>
  <title>User Input List Example</title>
</head>
<body>
  <div>
    <input type="text" id="inputField">
    <button id="addButton">Add</button>
  </div>
  <div id="container"></div>

  <script src="practise.js"></script>
</body>
</html>
```
and here is the embedded javascript file **practise.js**
```
const container = document.getElementById('container');
const inputField = document.getElementById('inputField');
const addButton = document.getElementById('addButton');
const myList = [];

addButton.addEventListener('click', function() {
  const item = inputField.value;
  myList.push(item);

  renderList();
  inputField.value = '';
});

function renderList() {
    container.innerHTML = '';
  const ulElement = document.createElement('ul');
  myList.forEach(function(item) {
    const liElement = document.createElement('li');
    liElement.textContent = item;
    ulElement.appendChild(liElement);
  });

  container.appendChild(ulElement);
}
```

**2. Write a JS function to change the font size,bg-color, and font-family for the paragraph in the HTML snippet below on clicking the button**
```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>JS DOM paragraph styling</title>
</head>
<body>
 
<p id="text">It is a long established fact that a reader
will be distracted by the readable content of a page when
looking at its layout.</p>
<div>
<button id="jsstyle">Style</button>
</div>

<script>
  const para = document.getElementById("text");
  const button = document.getElementById("jsstyle");
  button.addEventListener("click", function() {
    para.style.fontFamily = "Arial"; 
    para.style.fontSize= "50px";
    para.style.backgroundColor="pink";
  });
</script>
</body>
</html>
```


**3. Write a JavaScript program that calculates the area of a rectangle when the user inputs the width and height into two input fields and clicks a button.**
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Rectangle Area Calculator</title>
</head>
<body>
  <h1>Rectangle Area Calculator</h1>
  <label for="length">Length:</label>
  <input type="number" step="any" id="length" placeholder="Enter length">

  <label for="breadth">Breadth:</label>
  <input type="number" step="any" id="breadth" placeholder="Enter breadth">

  <button id="calculate">Calculate Area</button>

  <p id="output"></p>

  <script>
    const button = document.getElementById("calculate");
    const length_input = document.getElementById("length");
    const breadth_input = document.getElementById("breadth");
    const area = document.getElementById("output");

    let length = 0;
    let breadth = 0;

    button.addEventListener('click', function() {
      length = parseFloat(length_input.value);
      breadth = parseFloat(breadth_input.value);

      if (!isNaN(length) && !isNaN(breadth)) {
        const rectangleArea = length * breadth;
        area.textContent = "The area of rectangle is " + rectangleArea;
      } else {
        area.textContent = "Please enter valid numbers for length and breadth.";
      }
    });
  </script>
</body>
</html>
```
**4. Write a JavaScript program that displays an alert message to the user when they submit a form.**
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Practise form</title>
</head>
<body>
  <h1>Form</h1>
  <label for="name">Name</label>
  <input type="text" step="any" id="name" placeholder="Enter name">
  <br>
  <label for="roll">Roll no.</label>
  <input type="text" step="any" id="roll" placeholder="Enter roll no.">
  <br>
  <button id="submit" onclick="showAlert()">Submit</button>
  <script>
   function showAlert(){
    alert("This a an alert box");
   }
  </script>
</body>
</html>
```

**5. Write a JavaScript program that displays an alert message to the user when they resize the browser window.**
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Practise form</title>
</head>
<body>
  <script>
   function showAlert(){
    alert("You are resizing the window");
   }
   window.addEventListener("resize", showAlert);
  </script>
</body>
</html>
```
**6. Write a JavaScript program that uses AJAX to fetch and display data from a text file when the user clicks on a button.**
This is my text file ajax_practise.txt:
```
Hi my name is sarthak Tiwari !
This file is fetched using ajax.
```
This is the js program which uses AJAX to fetch practise.txt

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Fetch Text File with Ajax</title>
</head>
<body>
  <button id="fetchText">Fetch Text</button>
  <pre id="content"></pre>

  <script>
    document.getElementById("fetchText").addEventListener("click", function() {
      const xhr = new XMLHttpRequest();
      xhr.open("GET", "ajax_practise.txt", true);
      xhr.onreadystatechange = function() {
        if (xhr.readyState === 4 && xhr.status === 200) {
          const textContent = xhr.responseText;
          document.getElementById("content").textContent = textContent;
        }
      };
      xhr.send();
    });
  </script>
</body>
</html>
```

**7. Write a JavaScript program that uses AJAX to fetch and display an image from an API when the user clicks on a button**
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Fetch and Display Image with AJAX</title>
</head>
<body>
  <button id="fetchImage">Fetch Random Image</button>
  <div id="imageContainer">
    <!-- The fetched image will be displayed here -->
  </div>

  <script>
    // Function to fetch and display the image
    function fetchImage() {
      const imageContainer = document.getElementById("imageContainer");

      // Make an AJAX request using Fetch API
      fetch("https://source.unsplash.com/random")
        .then(response => {
          // Check if the response is successful (status 200)
          if (!response.ok) {
            throw new Error("Failed to fetch image");
          }
          return response.url;
        })
        .then(imageUrl => {
          // Create an <img> element and set the image source
          const imgElement = document.createElement("img");
          imgElement.src = imageUrl;
          imgElement.alt = "Random Image";

          // Add the <img> element to the imageContainer
          imageContainer.innerHTML = "";
          imageContainer.appendChild(imgElement);
        })
        .catch(error => {
          console.error(error);
          imageContainer.innerHTML = "Failed to fetch image.";
        });
    }

    // Attach click event to the button
    const fetchButton = document.getElementById("fetchImage");
    fetchButton.addEventListener("click", fetchImage);
  </script>
</body>
</html>

```

