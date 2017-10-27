# README

# Where, Find and Find_by 

look in to :      app/controllers/profiles_controller.rb

and read the follwing instruction to find the difference beteween 'where','find' and 'find_by'

```
# @profile = Profile.where(user_id: current_user.id).first
    @profile = Profile.find_by(user_id: current_user.id)
    # these above two lines work in same
    
    # there is difference between .where and .find_by and .find methodes
    # .where return an array. to be able to read this array we need to a loop (eg. each loop) or .first .last or [0] methodes
    # .find_by return the first object found.
    # . find  return the object the object we are looking for

    # example:
    # Person table
    #  id| name
    #   1|  luke
    #   2|  Mathew
    #   3|  Ali
    #   4|  luke
    #   5| Ali
    #   6| Ali

    # person.find (id:1)  return luke
    # Person.find_by (first_name:"ALi") returen ALi just for id: 3
    # person.where(first_name:"ali") return [Ali,ALi,ALi]

    # more information :
    # http://guides.rubyonrails.org/active_record_querying.html

```

Tables are :Authentication, user profile, Pictures and comments.

made by gem 'devise', gem 'simple_form' and gem 'carrierwave'

to be able to see JUST current user posts

Applying database Query
http://guides.rubyonrails.org/active_record_querying.html

some other useful information like:

```

<td><%= link_to 'Show', profile_path(@profile.id) %></td>

 <!-- (@profile.id) is showing how to show :id mentioned in routes in oue link path -->

```
```
# to be able to see JUST current user posts
    # current_user is not nil if they've signed in with devise
    # puts "current_user is: #{current_user}"
    @posts = Post.all ## TURN THIS CODE ACTIVE AND OTHER CODES INACTIVE TO SEE ALL POSTS. ALSO IN VIEWS>POSTS>INDEX CHANGE THE @CURRENT_USER_POSTS TO @posts.
    #Applying database Query here in Post controller
    # http://guides.rubyonrails.org/active_record_querying.html
    # @current_user_posts = Post.where(user_id: current_user.id)
    # puts "@current_user_posts is: #{@current_user_posts.inspect}"

```

