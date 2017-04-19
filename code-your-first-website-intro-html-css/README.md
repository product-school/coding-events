# Code your first Website

Open Cloud9 and create a new workspace. Choose HTML5 template.

We are going to make our first website!

Remove all the files that are pre-made on Cloud9 and create a new file called `index.html`. This will be the main page of your website. You can have several pages but this one will be the one that will be displayed if you go to your website main URL.

In your `index.html` you'll need to set up few things for your webpage

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="iso-8859-7">
    <title>My first webpage</title>
  </head>
  <body>
  </body>
</html>
```

Each element in between carrots `<></>` are tags, each HTML element are in between tags. You have different tags to structure your html page. Here are a few of them:

```html
<html></html> ==> html webpage
<head></head> ==> tags to setup your page
<body></body> ==> the body of your webpage
<h1></h1> ==> Titles
<p></p> ==> Paragraphs
<title></title> ==> Title of your webpage
```
Let's try to write something. Inside your `<body></body>` insert the following code:

```html

<h1>Hello this is my first website</h1>
<p>This is great to learn how to code</p>
<p class="link"><a  href="mylinkedinURL">Connect with me on Linkedin</a></p>

```

Great! You made the skeleton of a very simple website. But it's a little boring, let's try to make it pretty

This is when CSS is taking place. Inside your `<h1>`, let's add something called a **class** as follow

```html
<h1 class="title">Hello this is my first website</h1>
```

Let's also put also a class for our `<p>`

```html
<p class="paragraph">This is great to learn how to code</p>
```

Now let's actually style our webpage. Inside your `<body></body>` insert the following tags:

```html
<style>

</style>
<h1 class="title">Hello this is my first website</h1>
<p class="paragraph">This is great to learn how to code</p>
<p class="link"><a  href="mylinkedinURL">Connect with me on Linkedin</a></p>

```

Inside `<style></style>` is where we can style our webpage. Let's try to style our body element by changing our background color

```html
<style>
  body {
    background: #4975FB;
  }
</style>
<h1 class="title">Hello this is my first website</h1>
<p class="paragraph">This is great to learn how to code</p>
<p class="link"><a  href="mylinkedinURL">Connect with me on Linkedin</a></p>
```

Great! We have a nice background but we want to have our text in the middle of our page instead of on the left. Let's do that by targeting our `<h1>` and `<p>`

```html
<style>
body {
  background: #4975FB;
}

.title{
    text-align:center;
    color:white;
}
.paragraph {
    text-align: center;
    color:white;
}

.link {

    text-align: center;

}

a {
    color:white;
    border: 1px solid white;
    text-decoration:none;
}
</style>
<h1 class="title">Hello this is my first website</h1>
<p class="paragraph">This is great to learn how to code</p>
<p class="link"><a  href="mylinkedinURL">Connect with me on Linkedin</a></p>
```


Bravo! You made your first html page and styled it!
