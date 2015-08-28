# Objects and Classes

Object oriented programming is just a way or organising code.  Like everything it needs a little practise to get used to.  Everything you use in python is an object with the exception os the reserved keywords like if, import, etc.  So

    x = 5 # we've created a integer...  So what is it?
    type(x) # it's an int object, we've seen this before.

We've also used methods that the int object has, +, -, etc.  What happens when you use + etc. is just that the int object uses a special method called __add__

    X.__add__(2) # should give 7, equivalent of x + 2

Strings also have an __add__ method

    y = 'hello'
    y.__add__(' world') # runs a method

So everything is an object in python.  Objects have functions which when they are attached to an object it is said to be its method so we can easily differentiate between a standalone function and the method belonging to some object. 

As well as methods object can also have attribtues which we have already in the docstring

    x.__doc__ # docstring attribute for int

String, integer, list etc. are obviously built in things that we have used.  Each thing is described by a class definition which defines its methods and attributes.  

Object orientation is usually demoed using some abstract definition of a solid object so

    class Ship: # class definition names are in CamelCase
        pass # a special keyword that does nothing!


    myship = Ship() # I've created an instance of Ship...  er... hoorah?
    type(Ship) # a class object
    type(myship) # an instance

Not a great deal of use so far, lets go further.  Now, I'm giving my ship class some properties and methods.  I want to know if a ship is still active in this case, so I have an attribute active which is set to True by default and 2 methods to either activate or deactivate a ship instance.
    
    class Ship:
        ships = [] # a class variable
        def __init__(self): # special constructor function.
            self.name = '' # set instance's attributes
            self.launched = ''
            self.active = True
            Ship.ships.append(self) # append ship to the ship class

        def activate(self): # a method to change active
            self.active = True

        def deactivate(self): # a method to change active
            self.active = False

Lets use our class

    titanic = Ship() # creates an instance of a ship
    titanic.name = 'Titanic' # give in a name
    titanic.launched = '1912' # give it a launch date
    titanic.deactivate() # Titanic is not active...

    queen_mary_2 = Ship()
    queen_mary_2.name = 'Queen Mary 2'
    queen_mary_2.launched = '2003'

    for ship in Ship.ships: # use the class variable to find out what ships exist.
        if ship.active: # check if they are active.
            print "%s is active" % ship.name
        else:
            print "%s is not active" % ship.name

What just happened?  What is self?  

Classes can have attributes that are class attributes where you may set constants etc. or as above, the ships variable contains a list of all instances of the Ship class so I can just check the `Ships.ships` to find all instances of ship that have been created.  A class is essentially a description of an object but it is also an object in its own right.   

To let an instance of ship, say my titanic, above know it has to operate on itself i.e. its instance as opposed the the class that describes it, it takes a first argument called **self** for all its methods that are to be instance methods, things which are personal to the ship and not constant across a class of ships.  The notation `titanic.deactivate()` is effectively passing titanic itself as the first argument to its own deactivate method...  Similarly when we played with integers above we used `x.__add__(2)`, this method in the int class might look like `def __add__(self, number)`, i.e. it takes itself as the first number in the addition.  This then allows us to use the self variable to reference the instance in its own internal code.  Whenever we use self we are using the instance of the class, the class itself referred to by its name.

Take the function:
        def activate(self): # a method to change active
            self.active = True

The function and class need to know what it has to do, what is has to change in this case, so we have to pass something to it to let it know.  

This is probably the most complicated part of using object oriented programming to begin with.  So given it's such a pain, where is the gain?



##Inheritance








Note: It is common to have module names, function names and variable names in lowercase with underscores separating words my_stuff etc., and class names in CamelCase. 

