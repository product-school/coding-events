# Responsive Design With Bootstrap

Open your [cloud9](c9.io) and create a new workspace. Select HTML5 as template.

Create a file called `index.html`

Copy/paste the following code to set up your webpage to be able to recognize Bootstrap

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>PS Boostrap Workshop</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/css/bootstrap.min.css" integrity="sha384-rwoIResjU2yc3z8GV/NPeZWAv56rSmLldC3R/AZzGRnGxQQKnKkoFVhFQhNUwEyJ" crossorigin="anonymous">
    <script src="https://code.jquery.com/jquery-3.1.1.slim.min.js" integrity="sha384-A7FZj7v+d/sdmMqp/nOQwliLvUsJfDHW+k9Omg/a/EheAdgtzNs3hpfag6Ed950n" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tether/1.4.0/js/tether.min.js" integrity="sha384-DztdAPBWPRXSA/3eYEEUWrWCy7G5KFbe8fFjk5JAIxUYHKkDx6Qin1DkWx51bBrb" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/js/bootstrap.min.js" integrity="sha384-vBWWzlZJ8ea9aCX4pEW3rVHjgjt7zpkNpZk+02D9phzyeVkE+jo0ieGizqPLForn" crossorigin="anonymous"></script>
    <link rel="stylesheet" href="CSS/style.css">
    <link rel="stylesheet" href="CSS/normalize.css">
  </head>
  <body>
  </body>
</html>
```


A startup that builds an AI for entrepreneurs hired us to make a very simple landing page. Let's build it using bootstrap.

let's first copy the html below between our `<body></body>`

```html
<header>
  <div class="main-nav">
    <img class="logo" src="img/Emilie Logo Blanc.png" alt="logo">
  </div>

  <div class="banner">
    <h1 class="catch_phrase">Start your business with confidence</h1>
    <h2 class="catch_explanation">Emilie is the entrepreneur's assistant that will give you a market size, a target audience and a competition overview of your business idea</h2>
    <form class="form" method="post" action="">
      <div class="email">
        <input value="Enter your email" type="email" name="user-email">
      </div>
      <div class="submit-button">
        <input value="Get Early Access" type="submit" name="submit">
      </div>

      </form>

    <div class="under-email-message">
      <p>Don't worry we don't like to spam people</p>
    </div>

    <div class="footer-header">
      <p>We are recruiting, contact us <a href='#'>here</a></p>
      <p>© 2016 TestYourIdea Corporation</p>
      <img class="logo-full" src="img/Emilie Logo Full Blanc.png" alt="logo">
    </div>
  </div>
</header>
```

We need also to set up our CSS. Create a file called `style.css` and paste the following code:

```css
/********** BASIC STYLE ***********/


a{
  text-decoration: none;
  color:white;
}

a:hover{
  color:lightgrey;
}

header{
  color:white;
  background: #4F59D0;
  background-size:cover;
  height:100vh;
}

.wrapper{
  margin: auto;
  width: 90%;
  color:grey;
}

.logo {
  width:40px;
  height:40px;
}

.logo-full {
  height:75px;
  width:228px;
  transform:scale(0.7);
}

/********** MAIN NAV ***********/

.main-nav{
  width: 90%;
  color:white;
  font-size:1.3em;
}


.sign-in:hover{
  background:rgba(255,255,255,0.9);
  border-radius: 10px;
  color:grey;
}

.catch_phrase{
  font-size: 3em;
}

.catch_explanation{
  font-size:1.5em;
}

.form{
  width: 350px;
}

.email input{
  color:grey;
  background:rgba(255, 255, 255, 0.9);
  box-shadow:  0 .5px 1px  rgba(0, 0, 0, 0.9);
  border:2px solid white;
  border-top-left-radius:5px;
  border-bottom-left-radius: 5px;
  font-size: 1.4em;
  height:40px;
  width:230px;
}

.submit-button input{
  background: #83DE75;
  box-shadow: 1px 0.5px 2px rgba(0, 0, 0, 0.9);
  font-size: 1em;
  color:white;
  border: none;
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
  height:40px;
  width:100%;
  transition:background-color 0.3s;
}


.email input:focus{
  outline:none;
  border:2px solid black;
  background: rgba(0, 0, 0, 0.3);
  color:white;
}

.submit-button input:hover{
  outline:none;
  color:white;
  background-color:rgba(255, 255, 255, 0.3);
}

.submit-button input:active {
  background-color: lightblue;
}

.under-email-message {
  color:lightgrey;
}

.footer-header{
  font-size: .7em;
}
```

Finally the company provided us with their logo. Create a folder called `img` and put it inside the images you will [here](assets)


Your page looks a little weird because the layouts are not done. Let's use bootstrap to see how quick this is to fix! Let's do the following:

- In the `div` with the class `main-nav` add the following classes `d-flex justify-content-center p-2 m-0`

- In the `div` with the class `banner` add the following classes `d-flex flex-column justify-content-center m-5`

- in the `h1` with the class `catch_phrase` add the following classes `m-5`

- in the `h2` with the class `catch_explanation` add the following classes `ml-5 mt-2`

- in the `form` with the class `form` add the following classes `m-5 d-flex flex-row`

- In the `div` with the class `under-email-message` add the following classes ` ml-5 mt-0 mb-5`

- In the `div` with the class `footer-header` add the following classes `d-flex flex-row-reverse align-items-end justify-content-between m-5`


BRAVO! You made a great landing page, the startup is super happy with your work!
