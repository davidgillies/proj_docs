#Working with Files

Files are easy to use in Python.

    f = open('some.log') # opens file returns file object
    text = f.read() # puts all the text into a variable
    f = open('some.log') # 
    lines = f.readlines() # reads lines into a list
    for line in lines:  
        if 'Apache' in line:
            print line
    f.close() # close file

Opening in the write mode with 'w' means any time you use the write() method you will overwrite the any existing content in the file. 

    f = open('stuff.txt')
    f.read()
    f.close()

    f = open('stuff.txt', 'w') # will overwrite everything
    f.write('All gone!')
    f.close()
    print open('stuff.txt').read()

    f =  open('stuff.txt', 'a') # will append to the file  
    f.write('Add this!')
    f.close()
    print open('stuff.txt').read()

When things go wrong when using files and you get errors, the writing side of things can go wrong.  Using the **with** command ensures the file will be properly closed.

    with open('some.log') as f:
        f.write('') # 
