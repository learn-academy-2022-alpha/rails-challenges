Challenges
Routes, Views, Controllers

As a user, I can visit a custom landing page at localhost:3000.
As a user, I can see the names of my team members as hyperlinks on the landing page.
As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)
Params

As a user, I can visit a page called cubed that takes a number as a param and displays that number cubed.
As a user, I can visit a page called evenly that takes two numbers as params and displays whether or not the first number is evenly divisible by the second.
As a user, I can visit a page called palindrome that takes a string as a param and displays whether it is a palindrome (the same word forward and backward).
As a user, I can visit a page called madlib that takes params of a noun, verb, adjective, adverb, and displays a short silly story.


rails new routes_controllers_views_params -d postgresql -T
$ cd routes_controllers_views_params
$ rails db:create
Begin the rails server: $ rails server
Browsed to http://localhost:3000

made team folder under controllers
made app/controllers/team/team_controller.rb

class TeamController < ApplicationController
    def home
      'team.html.erb'
    end
    def jennice
      @videogames_jennice = ["Final Fantasy XIV", "Elden Ring", "Animal Crossing"]
     'jennice.html.erb'
    end
  end
    def arnold
     @videogames_arnold = ["Pokemon", "Valorant", "Halo Series"]
     'arnold.html.erb'
    end
  end

  edited config/routes.rb

  Rails.application.routes.draw do
  root 'team#home'
  get '/jennice' => 'team#jennice'
  get '/arnold' => 'team#arnold'
end

made home.html.erb under app/views

edited home.html.erb

<p>Hello?</p>

run the server localhost:3000

got error

uninitialized constant TeamController
Rails.root: /Users/learnacademy/Desktop/LEARN/routes-controllers-views-jennice-arnold/routes_controllers_views_params

made a "team" folder under app/views

deleted team controller folder and team folder under app/views

generated controller with $ rails generate controller Main

changed controller name to main in routes.rb

edited home.html.erb

<h3>List of Team Members & their favorite videogames</h3>
<%= link_to 'Jennice', '/jennice' %>
</br>
<%= link_to 'Arnold', '/arnold' %>

created jennice.html.erb
created arnold.html.erb

edited both html.erb files

example:

<h3>Arnold's favorite videogames</h3>
<ul>
<% @videogames_arnold.each do |value| %>
<li><%= value %></li>
<% end %>
</ul>
