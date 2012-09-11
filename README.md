# Csvash

Csvash automates your CSV extraction by mapping its headers with the columns contents and turning them into hashes that can be easily converted into ruby models.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'csvash'
```

And then execute:

```
$ bundle
```

Or install it yourself as:

```
$ gem install csvash
```

## Usage

First of all you have to require it in your file:

```ruby
require 'csvash'
```

To get a collection of hashes containing the csv data you can call:

```ruby
Csvash.hashify '/path/of/your/file.csv'
```

Modelify method allows to import or export csv files.

To import, if you prefer a collection of already filled objects from a specific class you can pass the csv path and the class:

```ruby
Csvash.modelify_and_import '/path/of/your/file.csv', User
```

However, to export, you can pass the desired path with the filename and a collection of objects  (an ORM based objects, as you wish) from a specific class:

```ruby
Csvash.modelify_and_export '/path/of/your/file.csv', collection
```
_* The desired path and its subdirectories are  created automatically._

##Options

There are some behavior options that can be changed with its initializer. To create it just type:

```
$ rails generate initializer csvash
```

These are the avaiable options

```ruby
# If set to true it will only retain fields that matches the class to be filled. Default is false.
# Csvash.mass_assignment_safe = true
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request