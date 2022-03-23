$ rails new routes_controllers_views_params -d postgresql -T
$ cd routes_controllers_views_params
Create a database: $ rails db:create
Begin the rails server: $ rails server
In a browser navigate to: http://localhost:3000


rails generate controller Main
  create  app/controllers/main_controller.rb
      invoke  erb
      create    app/views/main
      invoke  helper
      create    app/helpers/main_helper.rb


created team.html.erb
root 'main#team'

created jose.html.erb, kendra.html.erb, kat.html.erb files in views

inside team.html.erb
<h1> team members</h1>
<%= link_to 'jose', '/jose'%>
<%= link_to 'kendra', '/kendra'%>
<%= link_to 'kat', '/kat'%>


inside main_controller.rb
class MainController < ApplicationController
    def jose
         'jose.html.erb' 
    end
    def kendra
         'kendra.html.erb'
    end
    def kat
         'kat.html.erb'
    end
end


TOP 3 inside kendra.html.erb
<ul>
 <li>Final Fantasy XIV</li>
 <li>Battlestar Galactica</li>
 <li>Hot Fuzz</li>
</ul>


MAIN CONTROLLER
class MainController < ApplicationController
    def jose
         'jose.html.erb' 
    end
    def kendra
         'kendra.html.erb'
    end
    def kat
         'kat.html.erb'
    end
    def cubed 
        @result = params[:number].to_i ** 3
        'cubed.html.erb'
    end
    def evenly 
        if params[:num].to_i % params[:num1].to_i == 0
            @results = 'The first number is evenly divisible by the second number'
        else 
            @results = 'The first number is not evenly divisible by the second number'
        end
        'evenly.html.erb'
    end
    def palindrome
        if params[:string].reverse == params[:string]
            @results = 'The word you entered is a palindrome.'
        else 
            @results = 'The word you entered is not a palindrome.'
        end 
    end
end



MAIN HTML ERB file
<h1>Main Page</h1>
<br/>

<h3>Team Members</h3>
<ol>
<li><%= link_to 'Jose', '/jose'%></li>
<li><%= link_to 'Kendra', '/kendra'%></li>
<li><%= link_to 'Kat', '/kat'%> </li>
</ol>
<br/>
<br/>
<ul>
<li> <%= link_to 'Cubed', '/cubed'%></li>
<li><%= link_to 'Evenly', '/evenly'%></li>
<li><%= link_to 'Palindrome', '/palindrome'%></li>

</ul>




ROUTES.RB file
Rails.application.routes.draw do
    get '/jose' => 'main#jose'
    get '/kat' => 'main#kat'
    get '/kendra' => 'main#kendra'
    get '/cubed/:number' => 'main#cubed'
    get '/cubed/:number', to: 'main#cubed'
    get '/evenly/:num/:num1' => 'main#evenly'
    get '/palindrome/:string' => 'main#palindrome'
    root 'main#main'
end


palindrome html file
<h1> Palindrome </h1>

<%= @results %>
