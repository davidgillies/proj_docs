# Modules and Packages
Modules are simply python files, which are basically code saved in a file with a .py extension.  

Lets make a file then, open your fave IDE (your editor!).  Type in the following

    def is_prime(number): # function to tell if a number is prime
        if number < 2: 
            return False
        else:
            for a in range(2, number): # remember indexing, range creates a list from 2 to number -1, [2,..,number-1]
                if number % a == 0: # if any number divides our number without remainder it's not prime.
                    return False
        return True # it's got this far, so must be true.

Save the file as mystuff.py to some location.  If you want to use your ipython notebooks, save the file to the same location as your notebooks.  If you are going to use ipython command prompt you should start the propmt from the same location as the file.  This is because Python looks for modules on certain paths including your current location.  For ipython notebooks, they will import from anywhere on the python path including the place you've set up to save your notebooks.

If you can't be bothered...  I've already added the file to the git repo, so if you downloaded that, you'll can import it from your notebooks.

Whichever choice you have made!  Either create a notebook, open an ipython prompt or use the notebook from the repo and do this...

    import mystuff # imports and executes the module, note no .py at the end.
    mystuff.is_prime(5) # call a function from the module...

Lets add another function to our file

    def do_something():
        print "Doing something..."
        print "." * 30
        print "Still doing it"
        print "." * 30
        print "done"
        return "Need a break now"

    do_something() # run the function...

Ok, save that and back to the prompt or notebook and...

    mystuff.do_something() # oh dear!

When you do an import with Python won't reload the same one again, this is good as many files can import multiple things and often they can be the same so you don't want them being loaded up loads of times.  When developing with notebooks or the ipython prompt you can get round this by starting with the following

    %load_ext autoreload # % denotes a special ipython command
    %autoreload 2 # option 2 reloads every imported module on use.

After this, any saved module changes will work immediately.  You can check out the options **[here](https://ipython.org/ipython-doc/dev/config/extensions/autoreload.html)**

Alternatively

    reload(mystuff) # manually reload the module.

Note the reload runs the do_something() function as we intended.  Also note the return string doesn't show.  If we run the function

    mystuff.do_something() 

We see all the prints but the returned statement is returned as standard output, it is not printed so

    mystring = mystuff.do_something() 

will print out all the print statements but the return string is assigned to the variable, mystring.

### Run from command line

You can also runs script from the command line, so open a command prompt (not the ipython or python prompt)and cd to the location of your file.

    python mystuff.py # will run the do_something function.

Generally you might want a script to behave differently when imported to run directly from the command line.  In your new_stuff.py file remove the do_something() at the end and replace with

    if __name__ == '__main__': # Do something will only run when called from command line, but not when imported.
        do_something()

When the file is run at the command line it gets the name "\_\_main\_\_" but when imported it gets the module name without the py, so do_something() isn't run anymore.

###Importing Stuff

Create another file called new_stuff.py in the same location as your first.  

    import mystuff # import our first file

    def number_info(number):
        """Assumes an integer and returns some info"""
        info = []
        if number % 2 == 0: # test it's even
            info.append('even')
        else:
            info.append('odd')
        if mystuff.is_prime(number): # use the other module function
            info.append('prime')
        else:
            info.append('not prime')
        return "number is %s and %s" % (info)

Now go back into your notebook or prompt

    import new_stuff # note the do_something printouts as we imported mystuff it is executed.
    new_stuff.number_info(5) 
    new_stuff.number_info(10)

### Namespaces
When working in a module, your module has its own namespace.  All the variables and functions you create exist within that namespace.  When you import another module you bring it into your namespace and to access functions in its namespace you prepend the function call with the module name as we have seen `mystuff.do_something()`

You can however import things directly into your modules namespace 

    from mystuff import do_something
    do_something() # I can now use the function without prepending the module name.

You can also import everything from the module

    from mystuff import *
    is_prime(23) 

This is not a good idea as it can cause conflicts.

You can also rename module namespaces when importing, so I say I had two modules with the same names I wanted to import.  This can happen when you are working across applications which share the same structure and file names.
    
    >> from daves import mystuff as daves_stuff
    >> from berts import mystuff as berts_stuff
    >> import johns.mystuff as johns_stuff

###Packages
A Package in python is a folder that contains a special file, \_\_init\_\_.py  This file can be and often is empty or it can be used to initialise code for the module when imported.  Any files inside the package can be imported.  Lets try it out.

Create a folder called mypackage where your notebooks are or in the location you run the ipython prompt.  In the folder create a file called __init__.py and another called my mymodule.py

    # __init__.py
    print "This is great, init!" # sorry

    # mymodule.py 
    print 'this is in mymodule' 

Save and return to the notebook or prompt and 

    import mypackage
    from mypackage import mymodule

We will look at some of the modules and packages available for use later. 








