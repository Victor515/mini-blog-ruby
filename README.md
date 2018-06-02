# mini-blog

This is a simple blog system written in Ruby on Rails, following the guide on the [official website](http://guides.rubyonrails.org/getting_started.html). Based on that, Bootstrap framework is used to decorate the website.

Click me for [demo](https://hidden-bastion-64624.herokuapp.com/)  
User Authentication:
* Username: dhh
* Password: secret


## Version
* Ruby v2.3.3
* Rails v.5.1.6  

## Configuravtion
For Heroku deployment, underlying database server is changed from default sqlite3 to postgresql. If you want to run this project with sqlite3, you will need to edit `Gemfile` and change this line:
```
gem 'pg'
```
to:
```
gem 'sqlite3'
```
Also remember to reinstall dependencies:
```
bundle install
```
Also, the `config/databse.yml` file need to be changed to use the sqlite3 adapter. Comment out the postgresql adapter setting at the bottom and uncomment the top part in the file. Your file should be like:
```
# SQLite version 3.x
#   gem install sqlite3
#
#   Ensure the SQLite 3 gem is defined in your Gemfile
#   gem 'sqlite3'
#
default: &default
  adapter: sqlite3
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  timeout: 5000

development:
  <<: *default
  database: db/development.sqlite3

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test:
  <<: *default
  database: db/test.sqlite3

production:
  <<: *default
  database: db/production.sqlite3
```
Before running the server, remember to initialize the database, as described below.



## Database initialization
Run:
```bash
ruby bin/rails db:migrate
```

## Deployment instructions
Follow this [link](https://devcenter.heroku.com/articles/getting-started-with-rails5) on Heroku official website
