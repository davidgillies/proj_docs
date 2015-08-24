# Functions
You can try out the commands at the ipython prompt or see the ipython notebook, functions.ipynb or see the results at the [github page](https://github.com/davidgillies/python_notebooks/blob/master/functions.ipynb).

A function in python looks like this

    def myfunc(arg0, arg1):  # takes exactly 2 arguments
        """This is a useless function""" # the optional docstring.
        thing_to_return = arg0 + arg1
        return thing_to_return # returns an object

    # Lets run it.
    myfunc(1,2) # should return 3

Functions can either return a value directly or they can fulfill some process and not return anything, in this case python will return an NoneType object by default.  Function will accept any python object as an argument.

    myfunc('hello ', 'there')
    myfunc([1,2,3], [4,5,6]) 
    myfunc([1,2,3], 'heelo')  # Oops!!  Should produce an error, these two can't be added.


Note the usual indentation after the colon.  Docstrings are for documentation.  Python treats a string immediately after the function definition line specially and it will be available under the \_\_doc\_\_ property of the function.  So

    myfunc.__doc__ # will return the docstring.

Many objects have docstrings...

    x = 3 # x is an integer object.
    x.__doc__  # should give you the integer's docstring.

###Keywords
Functions can take keyword arguments too...

    def func(x, y):
        return x, y # returns a tuple

    func(1,2) #
    func(y=1, x=2) # You will rarely see this!

It is more common to see keywords where there is a need for defaults for a function...

    def keyfunc(x, y, factor=3): #
        return x**factor + y

    keyfunc(2,1) # uses the default factor=3
    keyfunc(2, 1, factor=5) # uses 5

Note when defining functions positional arguments must come before keyword arguments.  

###Arbitrary numbers of arguments
It is possible to pass any number of arguments to function...

    def arb_args(normal_arg, *args): # args will be a tuple of any extra args passed.  
        for arg in args:
            print arg
        print normal_arg

    arb_args('done', 1,2,3,4)

The same can be done with keyword args

    def kw_args(normal_arg, **kwargs): # kwargs will be a dictionary of the key, values passed in.
        for key, value in kwargs.items():
            print "%s : %s" % (key, value)

    kw_args('', arg1='1', arg2=2)

These can be used together but must be in order with keywords last

    def all_args(normal_arg, *args, **kwargs):
        for arg in args:
            print arg
        for key, value in kwargs.items():
            print key, value
        print normal_arg

    all_args('done', 1,2,3, keyword='keyword', again='another')

###Multiple return values
Functions can return multiple values which can easily be unpacked into variables..

    def multi_return(x, y):
        return x, y

    a, b = multi_return(1, 2) # assign the values return in the tuple to these variables.

    a # test a's value
    b # test b's value

This is because a tuple has been returned but this works with any iterable so

    a, b, c = [1, 2, 3] # test the values of a, b and c.
