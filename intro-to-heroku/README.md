# Deploy apps on Heroku

Today we will try to deploy Product School homepage on Heroku. There are several ways to deploy your app on Heroku.

The first one is over Github. Let's open Heroku.com, sign in and create a new app.

- Click on "New" on the top right of the screen and click on Create an App.
- You can name your app whatever you want.
- Click on Create App

Now you will under "Deployment method" that you can choose either Heroku Git, Github or Dropbox. We will cover Heroku Git and Github today.


## Github

- Select Github and connect the Repo you want to deploy.
- Select the branch you want to deploy (usually master)
- Enable automatic deploy or to deploy manually (depending on your preference)
- Wait a minute and that's it!

Now you can click on Open App and you should see your app up and running on Heroku's servers.


## Heroku Git

Another way to deploy applications is with Heroku commands.


### Create Your Heroku App

  1. Add a new app using the heroku toolbelt command. In the Terminal, from your project's root directory, run:
  *If you don't supply a name for your app, Heroku will create a random one for you. The name must be unique across all of Heroku and the command line interface will tell you if the name you want is already taken. It's generally a good idea to give your app a name to personalize it and reflect its purpose.*

```s
$ heroku create YOUR_APP_NAME
```

2. Let's check the status of our remote repositories:

```s
$ git remote -v
```

You should see something like this:

```s
$ heroku	https://git.heroku.com/YOUR_APP_NAME.git (fetch)
$ heroku	https://git.heroku.com/YOUR_APP_NAME.git (push)
```

### Deploy to Heroku

1. You should be all set up now, so add and commit your new changes, then push to Heroku:

```s
$ git status
$ git add .
$ git commit -m "update for initial deploy"
```

2. Push to Heroku:
```s
$ git push heroku master
```

3. Hold onto your seat, grab some popcorn, and watch the deploy sequence.

Your Terminal output should look something like this (but a little longer):

```s
Initializing repository, done.
Counting objects: 64, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (53/53), done.
Writing objects: 100% (64/64), 14.57 KiB | 0 bytes/s, done.
Total 64 (delta 5), reused 0 (delta 0)

-----> Ruby app detected
-----> Compiling Ruby/Rails
-----> Using Ruby version: ruby-2.0.0
-----> Installing dependencies using 1.5.2
        New app detected loading default bundler cache
        Running: bundle install --without development:test --path vendor/bundle --binstubs vendor/bundle/bin -j4 --deployment
        Fetching gem metadata from https://rubygems.org/..........
        Fetching additional metadata from https://rubygems.org/..
        Using i18n (0.6.9)
        .
        .
        .
        Installing sass-rails (4.0.3)
        Installing rails (4.0.4)
        Your bundle is complete!
        Gems in the groups development and test were not installed.
        It was installed into ./vendor/bundle
        Bundle completed (11.82s)
        Cleaning up the bundler cache.
-----> Writing config/database.yml to read from DATABASE_URL
-----> Preparing app for Rails asset pipeline
        Running: rake assets:precompile
        I, [2014-05-02T18:02:09.672047 #732]  INFO -- : Writing /tmp/build_625a98e6-1b9e-4e57-ba48-8f9cd7bf7d18/public/assets/application-c8d048bf2b32f85ef4807549fa44b21b.js
        I, [2014-05-02T18:02:09.694428 #732]  INFO -- : Writing /tmp/build_625a98e6-1b9e-4e57-ba48-8f9cd7bf7d18/public/assets/application-d0b54dd563966c42aad5fd85b1c1f713.css
        Asset precompilation completed (6.52s)
        Cleaning assets
        Running: rake assets:clean
-----> WARNINGS:
        Include 'rails_12factor' gem to enable all platform features
        See https://devcenter.heroku.com/articles/rails-integration-gems for more information.

-----> Compressing... done, 21.4MB
-----> Launching... done, v6
        http://thingsthingsthings.herokuapp.com/ deployed to Heroku

To git.heroku.com/YOUR_APP_NAME.git
  * [new branch]      master -> master
```

4. run `$ heroku info` to see the URL of your deployed app. Go check it out!

### Debugging

When visiting your deployed app for the first time, you may experience an error or two.
1. If this happens to you, check your Heroku logs in the terminal:

  ```s
  $ heroku logs -t
  ```

2. Scan all of the logs for error messages. If you see obvious error messages, google what they mean.
