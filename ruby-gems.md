# Ruby Gems

A Gem is a Ruby library which provides a certain functionality. This can be a library for reading markdown files (e.g. Kramdown), building a basic web application (e.g. Sinatra) or helping with user input (Thor).

You find available ruby gems on [RubyGems.org](http://rubygems.org/) or also on GitHub. Most projects which are on GitHub are also on RubyGems.org. 


## Installation
You can install a Ruby gem in your Terminal with

```bash
gem install <gem name>
```
This is okay, if you just want to play around with something. But if you want to run a Rails Website for example, it gets tedious to install each required gem on this way (Rails projects often have a very long list of dependent gems they're using).

To make this easier, most projects use [Bundler](http://bundler.io/). Bundler takes care of managing your project's dependencies.

How does this work?

At first, there is a new file, called the `Gemfile`. This is a file which contains Ruby code and lists all gems which are required by your application. This file is placed in your project's root directory.
An example Gemfile looks like this:

```ruby
source 'https://rubygems.org'

gem 'sinatra'
gem 'sinatra-contrib'

gem 'json'
gem 'virtus'
gem 'mail'
gem 'curb'
gem 'addressable'

group :test do
  gem 'rspec'
  gem 'factory_girl'
end
```
If you need another library, just add a `gem '<Name of your library>'` to the `Gemfile`. To install all depedencies, run `bundle install` in your project's root folder.
Bundler then downloads and installs all dependencies.
