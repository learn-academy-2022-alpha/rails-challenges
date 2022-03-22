Terminals:
cd desktop
mkdir routes
cd routes
rails new routes_controllers -d postgresql -T
cd routes_controllers
rails db:create
code .
rails s
command + t
rails g controller Team

open controller file and make methods to handle our routes for our landing page, Dane's page and Marc's page.

Create an html.erb file for our landing page, Dane's page and Marc's page

Create our routes for our landing page, Dane's page and Marc's page

Create a route to take a param of a number

Create a method that holds the param in an instance variable to pass to our erb file

On our erb file we render the number and then show the result cubed

Create a route in our routes for to handle our route for our cubed route as well for our parameter

Do the same for the rest of the challenges expect change the number of parameters and change the logic for each case
