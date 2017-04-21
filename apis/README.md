# Create an API

We are going to show one of the easiest API to use when you are using form in your webpage.

Have you ever wanted to receive information a user submitted over a form without the hassle of having a whole server side language and code to write to set it up? This is what Formspree.io does.

Open Cloud9 and remove all the pre-created files. Add an `index.html` where we are going to add our form.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Formspree forms</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/css/bootstrap.min.css" integrity="sha384-rwoIResjU2yc3z8GV/NPeZWAv56rSmLldC3R/AZzGRnGxQQKnKkoFVhFQhNUwEyJ" crossorigin="anonymous">
    <script src="https://code.jquery.com/jquery-3.1.1.slim.min.js" integrity="sha384-A7FZj7v+d/sdmMqp/nOQwliLvUsJfDHW+k9Omg/a/EheAdgtzNs3hpfag6Ed950n" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tether/1.4.0/js/tether.min.js" integrity="sha384-DztdAPBWPRXSA/3eYEEUWrWCy7G5KFbe8fFjk5JAIxUYHKkDx6Qin1DkWx51bBrb" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/js/bootstrap.min.js" integrity="sha384-vBWWzlZJ8ea9aCX4pEW3rVHjgjt7zpkNpZk+02D9phzyeVkE+jo0ieGizqPLForn" crossorigin="anonymous"></script>
    <link rel="stylesheet" href="style.css">
  </head>
  <body class="full-header">
    <header class="full-header">
        <div class="main-nav container p-2">
           <ul class="nav">
            <li class="name"><a href="index.html">Product School</a></li>
          </ul>
        </div>
        <div class="center-content">
          <div class="d-flex flex-column align-items-center">
            <h1 class="mt-5 mb-2">Hey write me something nice!</h1>
            <h2 class="mb-5 sous-titre">Let's try what Formspree can do form me!</h2>
            <form action="" method="post">
                <div>
                  <label for=nom>Name</label>
                  <input type="text" name="nom_etudiant">
                </div>
                <div>
                  <label>Email</label>
                  <input type="email" name="email_etudiant">
                </div>
                <div>
                  <label>Message</label>
                  <textarea name="message_etudiant"></textarea>
                </div>
            <div class="button d-flex justify-content-center">
              <input type="hidden" name="_next" value="thanksEtudiant.html" />
              <input type="submit" value="Submit">
            </div>
            </form>
          </div>
        </div>
      </header>
  </body>
  </html>
```


Let's make that form a little nicer with CSS. Add a `style.css` with the following code

```css
* {
    background:#2D96FF;
    color:white;
}

a {
    color:white;
}


form {
    /* Pour le centrer dans la page */
    width: 600px;
    /* Pour voir les limites du formulaire */
    padding: 1em;
}

form div + div {
    margin-top: 2em;
}

label {
    /* Afin de s'assurer que toutes les étiquettes aient la même dimension et soient alignées correctement */
    display: inline-block;
    width: 90px;
    text-align: right;
    font-size:1.3em;
    margin-right: 5px;
}

input, textarea {
    /* Afin de s'assurer que tous les champs textuels utilisent la même police
       Par défaut, textarea utilise une police à espacement constant */
    font: 1em sans-serif;

    /* Pour donner la même dimension à tous les champs textuels */
    width: 400px;
    height:1.7em;
    border-radius:10px;
    -moz-box-sizing: border-box;
    box-sizing: border-box;

    /* Pour harmoniser l'apparence des bordures des champs textuels */
    border: 1px solid #fff;
}

input:focus, textarea:focus {
    /* Afin de rehausser les éléments actifs */
    border-color: #fff;
}

textarea {
    /* Pour aligner correctement les champs multilignes et leurs étiquettes */
    vertical-align: top;

    /* Pour donner assez d'espace pour entrer du texte */
    height: 6em;

    /* Pour permettre aux utilisateurs de redimensionner un champ textuel horizontalement
       Cela ne marche pas avec tous les navigateurs  */
    resize: vertical;
}



input[type="submit"]{
  cursor:pointer;
  margin-top: 10px;
  font-size:1.5em;
  background:rgba(255, 255, 255, 0);
  border:2px solid white;
  color:white;
  width: 200px;
}
```

Now that we have a form. Let's add a little piece of code to add formspree functionality to our website.

- Add `https://formspree.io/your@email.com` in the `action` attribute.
- Make sure that every `input` `textarea` etc. have a `name` attribute.
- Now you just need to submit the form once to confirm your email
- All set ! You connected your first API to your web application.
