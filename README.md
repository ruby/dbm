# DBM

The DBM class provides a wrapper to a Unix-style [dbm](http://en.wikipedia.org/wiki/Dbm) or Database Manager library.

Dbm databases do not have tables or columns; they are simple key-value data stores, like a Ruby Hash except not resident in RAM. Keys and values must be strings.

The exact library used depends on how Ruby was compiled. It could be any of the following:

* The original ndbm library is released in 4.3BSD. It is based on dbm library in Unix Version 7 but has different API to support multiple databases in a process.
* [Berkeley DB](http://en.wikipedia.org/wiki/Berkeley_DB) versions 1 thru 5, also known as BDB and Sleepycat DB, now owned by Oracle Corporation.
* Berkeley DB 1.x, still found in 4.4BSD derivatives (FreeBSD, OpenBSD, etc).
* [gdbm](http://www.gnu.org/software/gdbm/), the GNU implementation of dbm.
* [qdbm](http://fallabs.com/qdbm/index.html), another open source reimplementation of dbm.

All of these dbm implementations have their own Ruby interfaces available, which provide richer (but varying) APIs.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'dbm'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install dbm

## Usage

```ruby
require 'dbm'
db = DBM.open('rfcs', 0666, DBM::WRCREAT)
db['822'] = 'Standard for the Format of ARPA Internet Text Messages'
db['1123'] = 'Requirements for Internet Hosts - Application and Support'
db['3068'] = 'An Anycast Prefix for 6to4 Relay Routers'
puts db['822']
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/ruby/dbm.

## License

The gem is available as open source under the terms of the [2-Clause BSD License](https://opensource.org/licenses/BSD-2-Clause).
