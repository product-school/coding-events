# How to use Media Queries

A startup has a landing page coded but unfortunately. It isn't responsive at all. They hired us to finish the job.

Open cloud9 and create a new workspace. Select HTML 5 as template and remove all the pre-created files.

Add `index.html` and paste the following code:


```HTML
<!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8">
      <title>Test Your Idea</title>
      <link rel="stylesheet" href="style.css">
      <meta name="viewport" content="width=device-width, initial-scale=1">
    </head>
    <body>
      <header>
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

          <div class="under-email-message">
            <p>Don't worry we don't like to spam people</p>
          </div>

        </form>

          <div class="footer-header">
            <p>We are recruiting, contact us <a href='#'>here</a></p>
            <p>© 2016 TestYourIdea Corporation</p>
          </div>
        </div>
      </header>
  </html>


```


Create a CSS file called `style.css` and add the following code :

```css
/********** BASIC STYLE ***********/

*{
  margin:0;
  box-sizing: border-box;
}

a{
  text-decoration: none;
  color:white;
}

a:hover{
  color:lightgrey;
}

header{
  color:white;
  text-align: left;
  background: #0099FF;
  height:100vh;
}

.wrapper{
  margin: auto;
  text-align: center;
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
  margin: auto;
  display:flex;
  align-items: center;
  justify-content: center;
}

.logo, .sign-in, .jobs{
  margin-top: 10px;
}

.sign-in:hover{
  background:rgba(255,255,255,0.9);
  border-radius: 10px;
  padding:5px;
  color:grey;
}


/********** BANNER ***********/

.banner{
  width: 100%;
  height:90%;
  display:flex;
  flex-direction:column;
  text-align: center;
}

.catch_phrase, .catch_explanation, .email{
  align-self: center;
}

.catch_phrase{
  margin-top:100px;
  margin-bottom: 0;
  font-size: 3em;
}

.catch_explanation{
  font-size:1.5em;
  margin-bottom: 0;
}

.form{
  display:flex;
  flex-wrap: wrap;
  margin:auto;
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
  background: #53D769;
  box-shadow: 1px 0.5px 2px rgba(0, 0, 0, 0.9);
  font-size: 1em;
  color:white;
  text-align: center;
  border: none;
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
  height:40px;
  width:120px;
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
  display:flex;
  flex-direction: row-reverse;
  justify-content: space-between;
}

.footer-header p, .footer-header img {
  margin:auto 0;
}


/********** MEDIA QUERIES ***********/
```

If you open the page, on a laptop it looks nice but what if you shrink your browser window?

Our employer told us that almost all their clients are checking their page using Iphone 6. Let's make our page nice looking for this device. In your `<head></head>` add the following code

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

This will let your mobile browser know your site is optimized for mobile.

First let's see how it looks when we put our phone as landscape. Let's now add the following media queries

```css
@media (max-width: 667px) and (min-width: 376px){
  .catch_phrase{
    font-size: 2rem;
    margin-top: 50px;
  }

  .catch_explanation {
    font-size: 1.2rem;
    margin:auto;
  }

  .submit-button input {
    width: 140px;
  }

  .form {
    width: 380px;
  }

  .footer-header {
    margin-right:10px;
    margin-left:10px;
  }
}

```

This looks better now for iphones 6! Unless if we view it in portrait mode. Let's now add that code

```css
@media (max-width:375px) {
  .catch_explanation {
    margin:auto;
  }

  .email input {
    font-size:1rem;
  }

  .submit-button input {
    font-size:12px;
  }

  .under-email-message {
    font-size:12px;
  }

  .footer-header {
    margin-left: 15px;
    margin-right: 15px;
  }
}
```

Way better right? This is the power of media queries and CSS.
