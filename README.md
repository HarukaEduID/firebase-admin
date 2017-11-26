# FirebaseAdmin

Ruby SDK for utilizing Firebase Admin features, using ExecJS to take advantage of the NodeJS SDK.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'firebase_admin'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install firebase_admin

## Usage

The Firebase Admin SDK allows you to integrate your own servers with Firebase Authentication and this gem allows you to access the functionalities with Ruby. The admin user management API provides programmatic access to those same users. It even allows you to do things the Firebase console cannot, such as retrieving a user's full data and changing a user's password, email address or phone number.

Initialize the client then access the methods:
```ruby
client = FirebaseAdmin::Client.new()

## GETTER METHODS ##
# To get the user using firebase uid
client.find_user('user_firebase_uid')

# To get the user by email address
client.find_user_by_email('email_address@provider.com')

# To get the user by phone number
client.find_user_by_phone_number('0811XXXXXX')

## Create and Update User ##
user_attributes = {
  email: "user@example.com",
  emailVerified: false,
  phoneNumber: "+11234567890",
  password: "secretPassword",
  displayName: "John Doe",
  photoURL: "http://www.example.com/12345678/photo.png",
  disabled: false
}

client.create_user(user_attributes)
client.update_user(user_firebase_uid, user_attributes)

## Delete User (no need to authenticate as the user) ##
client.delete_user(user_firebase_uid)
```


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rspec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/firebase_admin.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
