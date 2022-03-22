Challenges
Routes, Views, Controllers

As a user, I can visit a custom landing page at localhost:3000.

Rails.application.routes.draw do
  get '/carlos' => 'classmate#carlos'
  get '/athen' => 'classmate#athen'
  root 'classmate#home'
end

As a user, I can see the names of my team members as hyperlinks on the landing page.

<h1> Classmates </h1>

<ul>
  <li> <%= link_to 'Carlos', '/carlos' %> </li>
  <li> <%= link_to 'Athen', '/athen' %> </li>
</ul>

As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)

class ClassmateController < ApplicationController
  def carlos
    @top_three_foods = ["Pizza", "Burgers", "Vodka"]
    @top_three_movies = ["Top Gun", "Naked Gun", "Die Hard"]
    'carlos.html.erb'
  end
  def athen
    @top_three_foods = ["Pho", "Pizza", "Korean BBQ"]
    @top_three_movies = ["The Dark Knight", "Prisoners", "I Saw the Devil"]
    'athen.html.erb'
  end
end

Params

As a user, I can visit a page called cubed that takes a number as a param and displays that number cubed.

def cubed
  @number = params[:user_number]
  integer = params[:user_number].to_i
  @number = integer**3
  'cubed.html.erb'
end

<h1> <%= params[:user_number] %> to the power of 3 is equal to <%= @number %> </h1>


As a user, I can visit a page called evenly that takes two numbers as params and displays whether or not the first number is evenly divisible by the second.

def evenly
  if params[:user_number1].to_i % params[:user_number2].to_i == 0
    @result_string = "The first number is evenly divisible by the second number."
  else
    @result_string = "The first number is not evenly divisible by the second number."
  end

end

<h1> <%= @result_string %> </h1>

As a user, I can visit a page called palindrome that takes a string as a param and displays whether it is a palindrome (the same word forward and backward).

def palindrome
  if params[:user_string].downcase.reverse == params[:user_string]
    @result_string = "That is a palindrome."
  else
    @result_string = "That is not a palindrome."
  end

end

<h1> <%= @result_string %> </h1>

As a user, I can visit a page called madlib that takes params of a noun, verb, adjective, adverb, and displays a short silly story.

def madlib
  @story = "#{params[:user_noun]} is one of my favorite things. There is no other thing I enjoy more than  #{params[:user_verb]}ing with. There is something about its #{params[:user_adjective]} nature that makes it absolutely #{params[:user_adverb]}."

end

<p> <%= @story %> </p>
