# Fog::Scaleway

Fog provider gem to support [Scaleway](https://www.scaleway.com/).

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'fog-scaleway', git: 'https://github.com/kaorimatz/fog-scaleway.git'
```

And then execute:

    $ bundle

## Usage

Put your credentials to the fog configuration file:

```yaml
default:
  scaleway_organization: <YOUR_ORGANIZATION_UUID>
  scaleway_token: <YOUR_TOKEN>
```

Create a connection to the service:

```ruby
compute = Fog::Compute[:scaleway]
```

Manage servers and resources using the connection:

```ruby
server = compute.servers.bootstrap

server.ssh('uname').first.stdout # => "Linux\r\n"

server.terminate
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test:integration` to run the integration tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/kaorimatz/fog-scaleway.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).