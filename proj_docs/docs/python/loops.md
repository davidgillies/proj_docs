# Loops and Control Structures
You can try out the commands at the ipython prompt or see the ipython notebook, lists.ipynb or see the results at the [github page](https://github.com/davidgillies/python_notebooks/blob/master/loops.ipynb).

## If
The basic syntax of the if statetment looks like:

    if <condition>:
        <statements>
    elif:
        <statements>
    else:
        <statements>

Notice the colons ending the lines and the indent that follows on the next lines.  When Python sees a colon it expects indetned code on the next line.  As long as we continue with the indents we are executing statements controlled by the if condition.

**Note on indents: ** It's best practise to use 4 spaces for indents in Python though scripts will still work as long as indents and colons are consistently matched.  Developers often will set up their IDE to change tabs into 4 characters to avoid potential conflicts that can arise between the tab character and spaces when they are mixed.

A basic example of an if being:

    x = 100
    if x > 99:
        print "cool"
        print "worked"
    else:
        print "rubbish"


    x = 10
    if x > 99:
      print "cool"
      print "worked"
    else:
      print "rubbish"

Note: Here I used only 2 space indents but it will work as python only expects a consistent indent.  It is recommended to use 4 spaces in scripts but you can get away with less if working at a command prompt...

In python when you test values for truth, certain things will return False such as 0, '' (empty string), None (the NoneType object) or any other empty object.  So

    y = 0
    if y: # should be False
        print 'y is True'
    else:
        print 'y is False'
    y = None # special keyword creates a NoneType object.
    type(y) # 
    if y:  # False again
        print 'y is True'
    else:
        print 'y is False'
    y=''    
    if y:  # and False again.
        print 'y is True'
    else:
        print 'y is False'

Any positive value will return True:

    y=167   
    if y:  # True
        print 'y is True'
    else:
        print 'y is False'
    y='this better be true' 
    if y:  # and True again.
        print 'y is True'
    else:
        print 'y is False'

None is a common object used in programming.  You have already seen methods that changed a list but returned the NoneType object.  Remember lists...

    l = [1,2,1,3,5,2]
    whats_this = l.sort() # sort sorts the list, l, ut returns a NoneType object.
    type(whats_this) 

To test for None...

    if whats_this is None:  # don't use == to test for None.  It can have strange results.
        print "It's None"
    if whats_this is not None:
        print "It's not None"

##Loops

### While Loops
While loops continue to do something as long as a condition is True.

    x = 1
    while x < 10:
        print x
        x = x + 1

Again notice the colons and following indented code.

###For Loops
For loops are much more common as they are easier to read generally.

    mylist = [1,2,3,7,8,9,3] # a list of integers
    for thing in mylist: # iterate over the list putting each list item into the thing variable and test the value.
        if thing > 5 and thing < 9:
            print "%s is >5 and <9" % thing
        elif thing <=5:
            print "%s is <=5" % thing 
        elif thing >=9:
            print "%s is >=9" % thing
    else:
        print 'done' # the else executes after the for loop.  But is seldom used.  While statements can also have else.

For cases where you don't want to do anything when looping, you use *continue* and when you need to stop a loop you use *break*...

        for thing in mylist:
        if thing > 5 and thing < 9:
            continue # do nothing go to next iteration
        elif thing <=5:
            print "%s is <=5" % thing # print something
        elif thing >=9:
            print 'done'
            break # loop will stop

It is a common thing to loop over a set number of iterations.  For this we can use range() which creates a list of numbers...

    list_of_nums = range(10)
    list_of_nums # output list

You can then loop over the range.  If you need to loop over a large list of numbers use xrange(), it is a more efficient way as it doesn't return the full list at once like range() does.  range() and xrange() don't need to be consecutive numbers but can have different start, end points and step size.  More details here -> [https://docs.python.org/2/library/functions.html#xrange](https://docs.python.org/2/library/functions.html#xrange)

##List Comprehensions
Creating a new list from another list a common feature in python and so there is a quick way called a list comprehension...

    l1 = [1,2,3,4,5,6,7,8,9]
    list_comp = [x for x in l1 if x%2 == 0] # get the even numbers from l1.
    list_comp # see the result

