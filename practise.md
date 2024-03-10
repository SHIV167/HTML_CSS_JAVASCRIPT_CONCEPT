##project1 filter and map odd square
```javascript
const arr = [1, 2, 3, 4, 5, 6, 7];

function square() {
  // let array = arr.filter((n) => n % 2 == 0).map((n) => n * n);
  let array = arr.flatMap((n) => (n % 2 == 0 ? n * n : []));
  console.log(array);
}
square();

```

##project2 color selector
```javascript
const buttons = document.querySelectorAll(".button");
const body = document.querySelector("body");
//console.log(button);
buttons.forEach(function (button) {
  //console.log(button);
  button.addEventListener("click", function (e) {
    //console.log(e);
    //console.log(e.target);
    if (e.target.id === "blue") {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === "green") {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === "yellow") {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === "orange") {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === "red") {
      body.style.backgroundColor = e.target.id;
    }
  });
});


```

##project3 Local storage
```javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <form action="">
        <h2>ENQUIRY FORM</h2>
        <label for="">Name:</label>
        <input type="text" name="uname" />

        <label for="">phone:</label>
        <input type="phone" name="phone" />

        <label for="">email:</label>
        <input type="email" name="email" />
        <button>SAVE</button>
    </form>

    
    <div class="main">
<!--<div class="details">
<span>&times;</span>    
<h5>NAME:</h5>
<div>SHIV</div>

<h5>PHONE:</h5>
<div>9871785859</div>

<h5>EMAIL:</h5>
<div>JHASHIV5@GMAIL.COM</div>
</div>-->

</div>    
    <script>
        // let user = [
        //     { 'username': 'shiv', 'age': '12' },
        //     { 'username': 'sonu', 'age': '13' },
        //     { 'username': 'ayush', 'age': '12' },

        // ]
        //localStorage.setItem("name","sdd")
        //localStorage.setItem("name",user)
        //localStorage.setItem("name",JSON.stringify(user))
        //console.log(JSON.parse(localStorage.getItem("name")))


        let form = document.querySelector("form");
        let main = document.querySelector(".main");

        form.addEventListener("submit", (event) => {
            let name = event.target.uname.value;
            let phone = event.target.phone.value;
            let email = event.target.email.value;
            //alert("gggg");
            //console.log(name,phone,email);
            var userData = JSON.parse(localStorage.getItem("userDetails")) ?? [];

            userData.push({ 'name': name, 'email': email, 'phone': phone, })
            localStorage.setItem("userDetails", JSON.stringify(userData))
            event.target.reset();
            displayData();
            //console.log(userData);
            event.preventDefault();
        });

        let removeData = (index) => {

            let userData = JSON.parse(localStorage.getItem("userDetails")) ?? [];

            //console.log(userData);
            userData.splice(index, 1);
            localStorage.setItem("userDetails", JSON.stringify(userData))
            displayData();
        }

        let displayData = () => {

            var userData = JSON.parse(localStorage.getItem("userDetails")) ?? [];

            //console.log(userData);
            let finalData = '';
            userData.forEach((element, i) => {
                finalData += `
<div class="details">
<span onclick='removeData(${i})'>&times;</span>    
<h5>NAME:</h5>
<div>${element.name}</div>

<h5>PHONE:</h5>
<div>${element.phone}</div>

<h5>EMAIL:</h5>
<div>${element.email}</div>
</div> `
            });
            main.innerHTML = finalData;
        }
        displayData();
    </script>
</body>

</html>

```


##project4 number addition and substaraction
```javascript


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML</title>
    <link rel="stylesheet" href="assets/css/style.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
    <script src="https://kit.fontawesome.com/bfb4213bb3.js" crossorigin="anonymous"></script>
    <link rel="stylesheet" href="https://necolas.github.io/normalize.css/8.0.1/normalize.css" type="text/css" />
    <!-- Load font awesome icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.1/css/all.min.css">


</head>
<style>
.total{border: 5px solid blue;}   
.counter{border: 5px solid blue;} 
</style>
<body style="font-size:60px;display:flex">
    <div class="counter">
    <span class="plus"><i class="fa fa-plus"></i></span>
    <span class="total" id="total"></span>
    <span class="minus"><i class="fa fa-minus"></i></span>
    </div>



    <script defer>
        let add = document.getElementsByClassName("plus");
            let sub = document.getElementsByClassName("minus");
            var total = document.getElementById("total");
            var i = 0;
            total.innerHTML = `${i}`;

            //creation of increment function

            function increment() {
                if (i < 19) {
                    i = i + 1;
                    document.getElementById("total").innerHTML = `${i}`;
                }
            }

            function decre() {
                if (i >= 1) {
                    i = i - 1;
                    document.getElementById("total").innerHTML = `${i}`;
                }
            }
            //creation of increment function

            add[0].addEventListener("click", increment);
            sub[0].addEventListener("click", decre);
    </script>
</body>

</html>








```