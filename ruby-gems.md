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


## Writing a gem

You can create a gem by your own. At first, we use Bundler to create a scaffold.
Open your terminal and type:
```bash
$ bundle gem my_gem
```
This creates a new folder `my_gem` and inside of the folder you see that it also creates a bunch of other files and directories.

```bash
      create  my_gem/Gemfile
      create  my_gem/Rakefile
      create  my_gem/LICENSE.txt
      create  my_gem/README.md
      create  my_gem/.gitignore
      create  my_gem/my_gem.gemspec
      create  my_gem/lib/my_gem.rb
      create  my_gem/lib/my_gem/version.rb
Initializing git repo in /Users/janschulte/temp/my_gem
```
It also creates a new git repository for you as you can see in the last line of the output.
There is a new folder called `lib`.

```bash
~/t/my_gem (master) $ tree lib
lib
├── my_gem
│   └── version.rb
└── my_gem.rb

1 directory, 2 files
```
Under `lib` there another folder with the same name as your gem, in our case `my_gem`. Here in this folder you put all your code.
