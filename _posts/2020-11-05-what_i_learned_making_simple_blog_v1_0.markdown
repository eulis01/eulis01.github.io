---
layout: post
title:      "What I Learned Making Simple Blog V1.0!"
date:       2020-11-06 03:46:36 +0000
permalink:  what_i_learned_making_simple_blog_v1_0
---


 So, I Completed my Flatiron Sinatra Project WebApp For Module # 2.  and I got to said this was a interesting and Fun Experience.  So I started to plan out My Project structure and Idea by making a diagram where a  `User has_many :post & has_secured_password`  and a `Post belongs_to :user`.


During the Learn Lesson we are Introduced to this awesome gem **[Corneal](https://github.com/thebrianemory/corneal)** Made by a Flatiron Alumni. This Awesome gem allow us to run `$ corneal new app_name` on the terminal. and this will generate a complete Project structure with the controller,models, views and many more files to  get us started quicker. Also we use the gem called [Shotgun](https://github.com/rtomayko/shotgun) to start up the server and run the app running `$ shotgun`. For some reason i had and issue where the flash message of the gem rack-flash would not show up or load i made a blog post about this issue [HERE!!](https://eulis01.github.io/stuck_debbugging_shotgun). To get around it i just run the thin server manually  with `$ bundle exec thin start --debug` here we are executing the thin web server with the —debug optional params so we get errors to show up on the terminal. Server is up and my Flash and the views are working . 

## Protecting the users data?

There are a few Requirement that need to be meet a few below:

- User must have an Account, and are able to Login, Logout & Signup.✅
- Once logged in, a user must have the ability to create, read, update and destroy the resource that belongs_to the user Currently logged in.✅
- Users can only edit resources that belong to him not any other users.✅
- Validate user input so bad data cannot be persisted to the database.✅
- Bonus: Display errors to user I used Sinatra-flash gem. ✅

### User signup and login route  authentication

—This is the /login route for the users

`get "/login" do`

`erb :"/users/login"`

`end`

—This is the Post Route for the User Login, first we find the user by email and assign the user to the instance variable of `@user` and if this user password authenticate to be the same as the hash stored password in the db the user would be logged in and and the cookies sessions id would be set the same as the @[`user.id`](http://user.id)  and a flash message would welcome the user to the profile page.

`post "/login" do`

`@user = User.find_by(email: params[:email])`

`if @user && @user.authenticate(params[:password])`

`session[:user_id] = @user.id`

*`# Alert user that Login has been Accepted.`*

`flash[:message] = "!!Welcome Login Accepted!!"`

`redirect to "/users/#{ @user.id }"`

`else`

If any error logging in flash would say the message and redirect_if_not_logged_in is a helper method i have in my controller that redirect to the /login route.

`flash[:error] = "Invalid Email or Password."`

`redirect_if_not_logged_in`

`end`

`end`

There is a Lot more code i can go over with about how to secure a post data and all that which is similar  to This but let Talk about a  few ruby worlds.

- **MVC** **⇒** Model, View & Controller this how the project files are organized or structured.

- **The Models** **⇒** This is where we find some of the Logic of the App and set the session and Routes all written in Ruby with Sinatra and ActiveRecord.

- **The Views** **⇒** this is where the data from the user  and the app connect together, basically we write html code embed into ruby logic or the other way around. We can also write css. this Files are Called ERB ⇒ Embedded Ruby.

- **The Controllers** ⇒ Pretty much all the Logic and hidden magic. Written in ruby and we can make many routes and set up how we receive a user input and validate that data and store it to the database. in other words than a user request and get the view file or ERB file for that specific view the user want and show that to the user to see.

-** Rest ⇒** Representational state transfer (REST) is a software architectural style that defines a set of constraints to be used for creating Web services.
- Params ⇒ Takes user Input from hash [:] and create a new objects from the app controllers files using an HTTP request.

There Are Many More Methods we Learned and Lot more User Logic i can go over but that would be too much If you would like to check out my project click [🌞](https://github.com/eulis01/simple_blog_1) the sun to check out my GitHub Repository for this project, if you Received some value from this or this helped you in any way shape or form don't hesitate to shoot me a tweet.  Twitter should be Linked on the Footer of the page as well to  My Github profile If you would like to follow me or contact me thanks for reading this far. 🙌 You're Awesome Much love From EB.
