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
