# Data Structures

For full documentation visit [https://docs.python.org/2/tutorial/datastructures.html](https://docs.python.org/2/tutorial/datastructures.html).

## Sequences


You can try out the commands at the ipython prompt or see the ipython notebook, lists.ipynb or see the results at the [github page](https://github.com/davidgillies/python_notebooks/blob/master/lists.ipynb).

### Lists
The same indexing rules for strings above apply to Python Lists.  A list is simply an ordered list of objects.  Any type of object including other lists can be added to lists, including other lists.  Lets try it


    l = [] # square brackets denote a list.
    l = list() # is equivalent 

  Lets have a fiddle...

    l = [1,2,3] # list of integers.
    l.append(4)  # add an new item to the list.
    l # just to see what's in our list.
    l.insert(1,10) # stick a 10 at index 1, the second item, remember indexes start at 0.
    l[1] # will now be 10.
    l[1:3] # Using the same index rules as strings, what will this return?  
    l[-1] # the last item in the list.
    l[:3] # from the start of the list to the 4th character.
    l[3:] # from the 4th character to the end including the 4th.
    l.sort() # sorts the list in ascending order but returns nothing... so have a look
    l # should see the list reordered.
    l.pop() # returns the last item from the list and removes it from the list!
    l # check the item is removed.
    l.reverse() # returns nothing but will reorder the list in reverse of it's current state.
    l # check it worked
    len(l) # returns the length of l.
    l = l + [1,1,1] # add 2 lists
    l.count(1) # count the number of times 1 is in the list.

You will have noticed that some operations return a result and show it and other act on the list but return no actual result.  [List operations](https://docs.python.org/2/tutorial/datastructures.html) are many and varied.

Ok, now for some weird stuff about lists

    l1 = [1,2,3]
    l2 = l1 
    l2.append(5) # now what is l1?
    l1 # l1 is exactly the same as l2 and has the appended item!
    l2[1] = 10 # check out l1
    l1 # should have the 10.

What's going on?  Effectively l1 and l2 are exactly the same, l2 is constructed with references to the items in l1 and they share references.  If you want an entirely separate list use

    l3 = l1[:] # l3 will be a copy which doesn't reference the original.
    l3[2] = 100 #
    l3 # shows l3 with the new item
    l1 # is unaffected this time.
    l3[2] = 3 # make l3 the same as l1

Now lets have a look at equality and identity

    l1 == l2 # double equals sign is the equality operator and will return true if the objects have the same value.
    l1 == l3 # So this is also true.
    l1 is l2 # 'is' tells us if the objects are actually the same.
    l1 is l3 # should be false! 

Finally, list can hold any objects...

    l4 = ['hello', 1, ['another list', 4]]


Note: you need to login with Raven to view Videos.

<iframe width="640" height="360" src="//upload.sms.cam.ac.uk/media/2049841/embed" frameborder="0" scrolling="no" allowfullscreen></iframe>

<!--div style="width:70%">
 <div style="position:relative; width:100%; padding-bottom:56.25%;">
   <iframe style="position:absolute; top:0; bottom:0; width:100%; height:100%;" src="//upload.sms.cam.ac.uk/media/2049841/embed" frameborder="0" scrolling="no" allowfullscreen></iframe>
 </div>
</div-->

### Dictionaries
You can try out the commands at the ipython prompt or see the ipython notebook, data_structures.ipynb or see the results at the [github page](https://github.com/davidgillies/python_notebooks/blob/master/data_structures.ipynb).

Dictionaries are effectively just key: value pairs.  They have keys with associated values.

    a = {} # this creates a dictionary
    a = dict() # so does this
    a = {'my_key': 'my_value'} # you can put stuff straight in on creation.
    a['new_key'] = 'a second value' # we can add key,values easily.
    a['my_key'] # accessing them is easy to.
    del a['new_key'] # bin a key
    a.keys() # check out what keys are there.
    a.values() # returns values.
    a.items() # returns a list of tuples.
    'my_key' in a # check a key exists.
    a.get('my_key') # returns value for that key.
    a.get('some_key', 'no key') # gives a default return if the key doesn't exist.
    a[2] = 'stuff' # add number key
    a.pop(2)  # pop returns the value and reamoves the key, value pair from the dictionary.


 Dictionary values can be any type of object

    a['my_list'] = [1, 'hello', 3] 

Keys must be immutable.  Mainly they will be strings or numbers but you could use other immutable things.

Note: Mutable just means 'liable to change'.  Strings are immutable.  We've already seen they have methods for a string, s, like s.replace('bla', 'debla') but these methods didn't change the string itself but returned another value.  We had to reassign the value, s = s.replace('bla', 'debla') to change the value of s.  For mutables like list methods change them without having to do a reassignment, so for a list, l, l.sort() changes l without any need for reassignment.

### Tuples
Tuples are similar to lists but are immutable so can't be directly changed after creation.

    t = (1, 2) # create a tuple.
    s = 1 ,2 # these are equivalent
    s == t  # 
Best to use the parenthesis but you will sometimes see them without.  

    x = (3) # this isn't a tuple!
    type(x) # it's an integer!
    x = (3,) # this is a tuple
    type(x) 
    t.count(2) # counts the number of 2's
    t.index(2) # gives index of 2

Tuples have very few methods due to their immutable nature unlike lists.
### Sets
Sets are unordered collections of unique immutable objects.  

    s = set()
    s = {1,2,3} # also creates a set...
    d = {} # this is an emtpy dictionary!!
    s = set([1,2,3,3,4,1]) # converts the list to a set. 

The main usage for sets is to remove duplicates from a list.

Sets have all your favourite mathematical functions

    s1 = {1,2,3,4}
    s2 = {3,4,5,6}
    s1.union(s2) # unique of elements in both sets.
    s1.intersection(s2) # elements in both sets.
    s1.difference(s2) # what's in s1 but not s2
    s1 - s2 # gives the same result.
    s1.symmetric_difference(s2) # in s1 or s2 but not both.

    s1 = {1,2,3}
    s2 = {1,2,3,4}
    s1.issubset(s2) # check for a subset.
    s1 <= s2 # same result.
    s2.issuperset(s1) 

There are more set methods available -> [https://docs.python.org/2/tutorial/datastructures.html#sets](https://docs.python.org/2/tutorial/datastructures.html#sets) but they are not used in any of the projects.




