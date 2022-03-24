## Errors.

These are some of the errors that I had while developing this web application.

### Error 1. Invalid route.

This is the error that I got running the app:
C:/Ruby30-x64/lib/ruby/gems/3.0.0/gems/actionpack-6.1.5/lib/action_dispatch/routing/route_set.rb:584:in `add_route': Invalid route name: 'user_facebook,_omniauth_authorize' (ArgumentError)

Solution:
Go to user.rb and change this:

* `:omniauth_providers => [:facebook, :google_oauth2]`

### Error 2. Invalid provider attribute.

Once I deployed the app to heroku, there was an attribute unrecognized.

Solution:

Delete all the users and type the next command:

* `heroku restart`

### Error 3. Undefiend method [] nil.

I saved my credentials using a Hash, so I had to change it.

Solution:

I had to change the hash param of my credentials like this:

* `config.omniauth :facebook, Rails.application.credentials.facebook_app_id, Rails.application.credentials.facebook_secret_key`