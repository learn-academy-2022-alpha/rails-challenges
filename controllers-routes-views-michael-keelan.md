 rails new routes_controllers_views_params -d postgresql -T

cd routes_controllers_views_params
rails db:create
rails server
In a browser navigate to: http://localhost:3000
rails generate controller Main

Routes.rb
    Added "root main#team" <- to be the main page
    
    Added Keelan and Mike pages:
        " get '/keelan' => "main#keelan' " 
        " get '/mike' => "main#mike' " 
    
    Added get "cubed/:cube_number' => cubed"


main_controller.rb
    Added a render for the main page
    
    Added mike and keelan as pages
        " 'keelan.html.erb' "
    
    changed the main page team from rendering with a message to rendering the view file team.htlm.erb

    added a def for the cubed page
        @number = params [:cube_number]_i ** 3
        'cubed.hltm.erb

    added a def for evenly page
        



View
    added a keelan and mike file in main named keelan.html.erb and mike.html.erb
    
    added a team.html.erb file this is our main page
    added links to team.html.erd to the mike and keelan files " <% link_to 'mike page', '/mike'%>

    Added a top 3 favorite things in an ul to Keelan and Mike pages example below:
        <ul>
            <li> Sam-I-Am <li>
            <li> Green Eggs <li>
            <li> Ham <li>
        </ul>

    added a page called cubed.html.erb
            <% @number %>
    
    added a page called evenly


