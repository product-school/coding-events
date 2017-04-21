# Intro to CSS

- Open Cloud9 and create a new workspace.
- Select the HTML5 template.
- Remove all pre-created files
- Create a `index.html`

- Copy and paste the following html code.

```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>

    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p>We can do a lot of things with CSS</p>
        <a href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```

Before the opening `<body>` tag, let's add `<style></style>`. We will be able to add our first stylings in between those tags. This is called embedded styling.

- Let's first change our background color. We are going to target our `body` tag.
- Let's also change the color of our font.


```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p>We can do a lot of things with CSS</p>
        <a href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```

As you can see our `<a>` element hasn't changed color. Let's change this.

- First we are going to target it using a class
- Let's add a `link` class to our `<a>`
- Now let's add our styling to our `<a>`

```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
      }

      .link {
        text-decoration: none;
        color: white;
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p>We can do a lot of things with CSS</p>
        <a class="link" href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```
We can't see now that our `<a>` element is clickable.

- Let's add borders so that it looks more like a button


```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
      }

      .link {
        text-decoration: none;
        color: white;
        border: 1px solid white;
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p>We can do a lot of things with CSS</p>
        <a class="link" href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```

Now our borders are a little too close from the text.

- Let's add padding to our `<a>` element


```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
      }

      .link {
        text-decoration: none;
        color: white;
        border: 1px solid white;
        padding:5px;
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p>We can do a lot of things with CSS</p>
        <a class="link" href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```

Now we would like our text to be centered

- Let's add a property to center our text.


```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
        text-align: center;
      }

      .link {
        text-decoration: none;
        color: white;
        border: 1px solid white;
        padding:5px;
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p>We can do a lot of things with CSS</p>
        <a class="link" href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```

Now our `<p>` element is a little small.

- Let's target it using an `id`


```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
        text-align: center;
      }

      .link {
        text-decoration: none;
        color: white;
        border: 1px solid white;
        padding:5px;
      }

      #paragraph {
        font-size:15px;
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p id="paragraph">We can do a lot of things with CSS</p>
        <a class="link" href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```

Finally we want texts around `#paragraph` to be further away.

- We are going to use a margin property.

```html
<!DOCTYPE html>

<html>
    <head>
        <title>Intro to CSS</title>
        <meta charset="utf-8">
    </head>
    <style>
      body{
        background-color:#EF4836;
        color:white;  
        text-align: center;
      }

      .link {
        text-decoration: none;
        color: white;
        border: 1px solid white;
        padding:5px;
      }

      #paragraph {
        font-size:15px;
        margin-top:50px;
        margin-bottom: 40px;
      }
    </style>
    <body>
        <h1>Hello World!</h1>
        <h2>It's great to learn how to code</h2>
        <p id="paragraph">We can do a lot of things with CSS</p>
        <a class="link" href="https://developer.mozilla.org">Check out here to learn more</a>
    </body>

</html>
```


Those are basic functionalities of CSS! You can play around with those to style your first webpages. 
