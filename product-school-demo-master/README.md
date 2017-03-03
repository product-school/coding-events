### Create a new project

We will create a project for blogs by scaffolding a quick app. Scaffolding an app allows us to rapidly build out much of the logic so that we can test out new technologies/ideas.

1.  Create a new project in Cloud9 and title it `rails-auth-demo`. Set it to a Rails environment.
2.  Open your Cloud9 terminal (shortcut `ctl ~`)
3.  Scaffold your application for a post by running `rails g scaffold Post title:string content:text`. This will build all of the routing, modeling, and controller logic for posts in the application.
4.  Migrate your database using the command `rake db:migrate`.

### Add a useful gem
1. Execute the command `gem install gemrat` in the terminal. This gem allows us to update our gemfile from the command line and run bundler all in one go.

### Add devise for Users

1.  Run `gemrat devise` in the terminal.
2.  Run `rails g devise:install` in the terminal. This will install all of the needed components for authentication.
3.  Run `rails g devise User` in the terminal. This will generate a User model.
4.  Add the line `has_many :posts` in your `user.rb` file.
5.  Add the line `belongs_to :user` in your `post.rb` file. Adding these two lines will associate your models for later use.
6.  Run `rails g migration add_user_id_to_posts` and add the line `add_column :posts, :user_id, :integer` to the file that is generated. This will add a foreign key between the two models and associate a post to the user that created it.
7.  Finally, run `rake db:migrate` in the terminal to migrate your database changes into the application.

### Additional set up

1. Set root path to `posts#index` in your `routes.rb` file.
2. In `application.html.erb` add this block of code:
```rb
   <% if user_signed_in? %>
     Logged in as <strong><%= current_user.email %></strong>.
     <%= link_to "Logout", destroy_user_session_path, method: :delete %>
   <% else %>
     <%= link_to "Sign up", new_user_registration_path %> |
     <%= link_to "Login", new_user_session_path  %>
   <% end %>
```
This block of code will allow you to fully navigate throughout the website.

3. Finally, in `app/controllers/application_controller.rb` add the line `before_action :authenticate_user!`

At this point you should have all the pieces you need before adding authorization to the application. Your users should be able to CRUD posts but can also do the same to other users posts!  We're about to change all of that.

### Adding cancancan

1. Run 'gemrat cancancan' in the terminal.
2. Add this to your application controller:
```rb
  class ApplicationController < ActionController::Base
    include CanCan::ControllerAdditions
  end
```
This line will load the functionality of CanCanCan into your application. This functionality comes with some key words that help you define which users CAN (get it) do things and which ones cannot.

 3.  Now define abilities by running the command 'rails g cancan:ability' in the terminal. This will create an 'ability.rb' file that you will use to help set the authorization of the users in the application.

 4.  In your 'ability.rb' file add this block of code:
 ```rb
 class Ability
  include CanCan::Ability

  def initialize(user)
    user ||= User.new # guest user (not logged in)
    can :read, Post

    can [:create, :update, :destroy], Post do |post|
      post.user == user
    end
  end
end
```
This code allows all users to read all posts.  However, the user can only create, update, and destroy posts if the user.id of the post matches their id.

5. At the top of the `posts_controller.rb` add this line before your definitions of your method: `load_and_authorize_resource only: [:edit, :update, :destroy]`
and also comment out `before_action :set_post, only: [:show, :edit, :update, :destroy]`

```rb
class PostsController < ApplicationController
  # before_action :set_post, only: [:show, :edit, :update, :destroy]
  load_and_authorize_resource  only: [:edit, :update, :destroy]
```

6. In the `posts_controller.rb` for your CRUD actions you will need to set the instance of a user to the current user like so:
```rb
 # GET /posts/new
  def new
    @user = current_user
    @post = Post.new
  end
```
This will ensure that the user that creates or edits posts is the user and helps to check the authorization.

7. In the `posts_controller.rb` modify the instance of a post in your create method to look like this:
```rb
  def create
    @user = current_user
    @post = @user.posts.build(post_params)

    if @post.save
      redirect_to @post
    else
      render 'new'
    end
  end
```
This will finally ensure that the post is associated with the user creating it.

8. In the `posts_controller.rb` modify the instance of a post in your show method to look like this:
```rb
 # GET /posts/1
 # GET /posts/1.json
 def show
   @user = current_user
   @post = Post.find(params[:id])
 end
```
This will ensure that you will have access to the correct post on that page

9. You will want to have a flash message to let the user know that have tried to access a page they are not authorized to do so:
```rb
# application_controller.rb

  rescue_from CanCan::AccessDenied do |exception|
    flash[:notice] = "Access denied!"
    flash.keep(:notice)
    redirect_to root_url
  end
  ```

At this point you should be able to create different users and make posts for those users. When an unauthorized user tries to modify or delete a posts they will not be able to and be met with an error saying so.

### Bonus: Adding Styles

1. Go to `application.html.erb` in `app > views > layouts` and add this line into the `<head>` tag section:
  ` <link href="https://fonts.googleapis.com/css?family=Shrikhand" rel="stylesheet">`

2. Open `scaffolds.scss` in `app > assets > stylesheets` and inside of the `body` rule replace the current `font-family` with:
  `font-family: 'Shrikhand', cursive;`
