# Software architecture

To make development and enhancement easier developers try to structure their software in a certain way. 
Functionalities get divided into specific parts and they define how functionalities from one part can talk to another
one from a different part.

## Ruby gem
A short recap:
> We have a `lib` folder which contains all stuff which belongs to the app. There is also a `bin` folder which contains the executable (to use your app from command line). 

The executable in `bin` ties together certain parts of your application. For example ataru:
There is a class for Markdown traversing, there is a class for executing the code examples and there is also some code which reads a file. 
All those parts don’t know each other. Only the executable does. The functionalities in `lib` do not know that there is an executable.


-----------------------------------------
| 							bin/ataru 							|
-----------------------------------------
| 							lib	   		 							|
-----------------------------------------

It looks like this, here you have two layers:
- `bin/ataru`
- `lib`

It is good design when classes only “can look down” which means, `bin` sees `lib` but `lib` does not see `bin`. 
If there would be another layer below `lib`, `bin` and `lib` would see it but not vice versa.


## Single responsibility

In general, when you write a new class, the class itself shouldn't know anything about the outside world. What does this mean?

See this example:

```ruby
username = "John"

class Greeter
  def greet(name)
    puts "HELLO #{name}"
  end
end
```
Here you have a `Greeter` class. Its purpose is to greet people. You create a new instance of `Greeter` with `my_greeter = Greeter.new`. And then you can greet people by calling the greet method `my_greeter.greet(username)`. 
The important part here is, the greet method accepts a parameter `name` and it greets somebody with this name. The `Greeter` class doesn't care from where this name comes. Its only *responsibility* is to greet somebody. The name could come from a database, a file or direct user input from command line. Getting the name is other code's *responsibility*. So you can reuse the `Greeter` class in many ways.

Further reading: [Wikipedia - Single responsibility principle](http://en.wikipedia.org/wiki/Single_responsibility_principle) (thanks Dirk for the pointer :)
