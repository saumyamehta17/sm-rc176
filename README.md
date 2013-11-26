Railscast sm-rc415 and sm-rc176
===============================

Upgrading from rails 3 to rails 4
```
Sometimes we need to upgrade to higher version
```
Go to gem file
```
change the versions of gem, for example
1. gem 'rails-3.2' =>  gemgem 'rails', '4.0.0.rc1'
2. gem 'sass-rails',   '~> 4.0.0.rc1'
3. remove asset do block etc
```
Production environment will not generate any asset by default and will use static precompiled assets
```
To precompile the assets , run following line
precompling is needed as it reduce number of requests as it compress javascript.
RAILS_ENV=Production bundle exec rake assets:precompile
```
Application.rb
```
add "Bundler.require(:default, Rails.env)"
remove
# if defined?(Bundler)
#   # If you precompile assets before deploying to production, use this line
#   Bundler.require(*Rails.groups(:assets => %w(development test)))
#   # If you want your assets lazily compiled in production, use this line
#   # Bundler.require(:default, :assets, Rails.env)
# end
```
To install new version
```
bundle update
```
See unexpected behaviour
```
bundle outdated
```
Railscast sm-rc176
===================
Search Logic
```
That give us bunch of named scope, and we can chain them together which is very efficient
```
Gemfile
```
gem install searchlogic
```
Depreceted
```
search logic is pretty outdated.
If you are using Rails 3.0 you should check out MetaSearch

If you are using Rails 3.1+ you should check out Ransack
```
