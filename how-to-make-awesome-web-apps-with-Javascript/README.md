# How to use JS

Go on Cloud9 and create a new workspace. Choose HTML5 as template.

We are going to make a tip calculator!

Let's first remove all the files pre-created in C9 and add an `index.html` file. Paste the following code :

```html
<!DOCTYPE html>
<html>
 <head>
    <title>JS Test</title>
 </head>
 <body
    <br/>
      <input id="meal_cost" type="number"/>
      <br/>
      <button id="add_tip">Add Tip</button>
      <br/>
      <div id="total_cost"></div>
    <script>
      // Js code will go here
    </script>
 </body>
</html>
```


Let's now add our JavaScript. First we need to declare a variable that we are going to call `add_tip`. This variable will select the button with the id of `add_tip`

it should look like this:

```js
var add_tip = document.getElementById('add_tip')
```

Now we need to make something happens when a user click on this button. This is called adding an `event listener`. The event listener will accept 2 parameters, the first will be the kind of event (on our case it will be when a user click on the button) and the second will be the **function** that will run when the event occurs.

```js
add_tip.addEventListener("click", AddTip)
```

We now need to actually code the function that will run when we click on our button. Let's first see how to write a function

```js
function functionName (param1, param2, param3, ...) {
  //your code
}
```

In our case the function will look like this

```js
function AddTip (){
  // Add code for the function
}
```

Now that we have our function, we need to write code inside it so that an action is made. We first need to ask our user how much tip he/she wants to put

```js
function AddTip (){
  var tipAmount = prompt("How much tip would you like to put")
}
```

Then we need to know the price of the meal

```js
function AddTip (){
  var tipAmount = prompt("How much tip would you like to put")
  var mealPrice = document.getElementById("meal_cost").value
}
```

We now need to make a simple math operation to know how much will be the total price

```js
function AddTip (){
  var tipAmount = prompt("How much tip would you like to put")
  var mealPrice = document.getElementById("meal_cost").value
  var totalPrice = mealPrice * (1 + tipAmount/100)
}
```
Our function has calculated the total amount of your meal! Great! We now need to display it on the screen to let the user know.

```js
function AddTip (){
  var tipAmount = prompt("How much tip would you like to put")
  var mealPrice = document.getElementById("meal_cost").value
  var totalPrice = mealPrice * (1 + tipAmount/100)

  var totalCostDiv = document.getElementById("total_cost")
  totalCostDiv.textContent = "Total: " + totalPrice
}
```

Bravo! You made your first Javascript application! 
