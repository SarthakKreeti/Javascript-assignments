**1. Create a button with the ID "clickMe" that, when clicked, changes the background color of the body element to red using jQuery.**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
</head>
<body>
    <button id="click_me">Click me</button>
    <script>
      $(document).ready(function(){
        $("#click_me").click(function(){
          $("p").css("background-color", "yellow");
        });
      });
    </script>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam atque maiores in, illum temporibus sed doloribus molestiae nam quaerat nulla? Rem aspernatur quod iste nemo adipisci. Laudantium et nesciunt at?</p>
</body>
</html>
```
**2. Write a jQuery function that takes the text inside a paragraph element with the ID "myPara" and appends it with another paragraph element with the ID "newPara" using jQuery.**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
</head>
<body>
    <button id="click_me">concatinate text</button>
    <p id="myPara"> is a trainee at Kreeti Technologies</p>
    <p id="newPara">Sarthak Tiwari</p>
    <script>
        $(document).ready(function(){
            var x=$("#newPara").text();
            var y=$("#myPara").text();
          $("#click_me").click(function(){$("#newPara").html(x+y);})
        });
      </script>
</body>
</html>
```
**3. Create a form that has a text input field with the ID "myInput" and a submit button. Write a jQuery function that alerts the user with the text they entered in the input field when they click the submit button.**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
</head>
<body>
    <input type="text" id="myInput" placeholder="Your name...">
    <button id="submit">Submit</button>

    <script>
        $(document).ready(function(){
          $("#submit").click(function(){
            var x=$("#myInput").val();
            alert(x);
          })
        });
      </script>
</body>
</html>
```
**4. Create a list with the ID "myList" that contains five list items. Write a jQuery function to highlight the first and last list items in the list with red color.**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
</head>
<body>
    
    <button id="highlight">Highlight</button>
    <ol id="myList">
        <li>
          Sarthak Tiwari
        </li>
        <li>
            Yash Barman
        </li>
        <li>
            Harsh Tripathi
        </li>
        <li>
            Vignesh Selvan
        </li>
        <li>
            Uday kiran
        </li>
    </ol>

    <script>
        $(document).ready(function(){
          $("#highlight").click(function(){
           $("#myList li:eq(0), li:eq(4)").css('background-color','red');
          })
        });
      </script>
</body>
</html>
```
**5. Create an HTML table with the ID "myTable" that has three columns: Name, Age, and Occupation. Write a jQuery function that adds a new row to the table with the name - "John", age - "30", and occupation - "Developer"**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
</head>
<body>
    <button id="add_row">Add row</button>
    <table id="myTable">
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
                <th>Occupation</th>
            </tr>
        </thead>
        <tbody>
            
        </tbody>
    </table>

    <script>
       $(document).ready(function(){  
            $("#add_row").click(function(){
                var newRow = $("<tr>");
                newRow.append("<td>John</td>");
                newRow.append("<td>30</td>");
                newRow.append("<td>Developer</td>");
                $("#myTable tbody").append(newRow);
            })
        });
    </script>
</body>
</html>
```
