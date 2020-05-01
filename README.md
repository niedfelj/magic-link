# Magic::Link
Short description and motivation.

## Usage
configure the gem
```ruby
# config/initializers/magic_link.rb
Magic::Link.configure do |config|
  config.user_class = "Customer" # Default is User
  config.email_from = "test@yourapp.com"
  config.token_expiration_hours = 6 # Default is 6
end
```

Run `rails magic_link:install:migrations`


Run `rails magic_link:move_to_multi`

Or `Magic::Link::Utility.move_to_multi`

Remove old columns `sign_in_token` and `sign_in_token_sent_at`


mount the engine
```ruby
mount Magic::Link::Engine, at: '/'
```

Now users can visit `/magic_links/new` to enter their email and have a sign in
link sent to them via email. Tokens are cleared after use and expire after the
configured number of hours

## Installation
Add this line to your application's Gemfile:

```ruby
gem 'magic-link'
```

And then execute:
```bash
$ bundle
```

Or install it yourself as:
```bash
$ gem install magic-link
```

## Contributing
Contribution directions go here.

## License
The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
