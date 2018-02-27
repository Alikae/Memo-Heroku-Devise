source 'https://rubygems.org'
gem 'rails', '5.1.4'
gem 'devise'
gem 'puma',         '3.9.1'
gem 'sass-rails',   '5.0.6'
gem 'uglifier',     '3.2.0'
gem 'coffee-rails', '4.2.2'
gem 'jquery-rails', '4.3.1'
gem 'turbolinks',   '5.0.1'
gem 'jbuilder',     '2.7.0'
group :development, :test do
  gem 'sqlite3', '1.3.13'
  gem 'byebug',  '9.0.6', platform: :mri
end
group :development do
  gem 'web-console',           '3.5.1'
  gem 'listen',                '3.1.5'
  gem 'spring',                '2.0.2'
  gem 'spring-watcher-listen', '2.0.1'
end
group :production do
  gem 'pg', '0.20.0'
end
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]


bundle install --without production
heroku create

<h1>Devise</h1>
gem 'devise'
bundle install --without production
rails g devise:install
(<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>) par ex pour flash messages
(rails g devise:views) for customize them
rails g controller Home index (routes)
rails g devise User
rails(rake?) db:migrate

-->views/home/index.html.erb
<% if user_signed_in? %>
<%= link_to "Sign Out", destroy_user_session_path, method: :delete %>
<%= link_to "Edit Profile", edit_user_registration_path %>
<% else %>
<%= link_to "Sign In", new_user_session_path %>
<%= link_to "Sign Up", new_user_registration_path %>
<% end %>

git add/commit
git push heroku master
heroku run rails db:migrate

verify online

rails g devise:views
(rails g migration AddAddressToUsers address:string) (rails db:migrate / heroku run rails db:migrate)

(--> apps/controllers/Application
  before_action :sanitize_devise_params, if: :devise_controller?
  def sanitize_devise_params
    devise_parameter_sanitizer.permit(:sign_up, keys: [:address])
  end)




For assets:
config.assets.compile = true      in    config/environnements/production.rb
rake assets:precompile
Beaucoup de Inch'Allah
