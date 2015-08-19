## Sequences

### Lists
The same indexing rules for strings above apply to Python Lists.  A list is simply an ordered list of objects.  Any type of object including other lists can be added to lists, including other lists.  Lets try it


    l = [] # square brackets denote a list.
    l = list() # is equivalent 

  Lets have a fiddle...

    l = [1,2,3] # list of integers.
    l.append(4)  # add an new item to the list.
    l # just to see what's in our list.
    l.insert(1,10) 
    l[1] # will now be 10.
    l[1:3] # Using the same index rules as strings, what will this return?  
    l[-1] # the last item in the list.
    l.sort() # sorts the list in ascending order but returns nothing... so have a look
    l # should see the list reordered.
    l.pop() # returns the last item from the list and removes it from the list!
    l # check the item is removed.
    l.reverse() # returns nothing but will reorder the list in reverse of it's current state.
    l # check it worked
    l = l + [1,1,1] # add 2 lists
    l.count(1) # count the number of times 1 is in the list.

You will have noticed that some operations return a result and show it and other act on the list but return no actual result.  [List operations](https://docs.python.org/2/tutorial/datastructures.html) are many and varied.

Ok, now for some weird stuff about lists

    l1 = [1,2,3]
    l2 = l1 
    l2.append(5) # now what is l1?
    l1 # l1 is exactly the same as l2 and has the appended item!
    12[1] = 10 # check out l1
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

### Tuples

### Sets