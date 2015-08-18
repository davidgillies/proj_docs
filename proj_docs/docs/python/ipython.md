# iPython

iPython provides not only the python prompt but a plethora of additional tools and access to shell commands etc.  It also provides browser based version where you can save notebooks of your interactions. For full documentation visit [http://ipython.org/](http://ipython.org/).

## iPython Prompt
To start ipython at a a command prompt, type

    ipython

 Lets interact with the shell, try:

    ls

This should give a file listing of your system.

    pwd

This will tell you your current directory.  Now choose a directory from your list and 

    cd <directory>

where directory is the directory name of the directory you chose.  Hint: Directory have **DIR** in their listing!  Try 

    pwd

Now you should be in the directory you choose.

You can do other things here like 

    mkdir bla # creates a directory called bla.

Note: I've added in some comments after the # here.  # is used to comment lines in python and can comment the last part of a line too.  If you do a 

    ls

you will see the new folder listed.

We will use the prompts for python in the following sections and you will see more commands in action.

## iPython Notebooks
If you look at your Start Menu on Windows and select 'All Programs', click on the Anaconda folder, then click on IPython (Py 2.7) Notebook.  This will start a command prompt screen, just ignore it, then it will start a tab in your browser with a folder and file listing.  The choice of this location is noted in the properties of the shortcut.  You can instead right click on the IPython (Py 2.7) Notebook shortcut in the menu and select properties, you can then change this location if you wish by editing the 'Start in' line.

Screenshot?

You can now click on the 'new notebook' button on the top right.  This will opena another tab with untitled as its title.  You can edit the title by clicking on it.  

You can do most things here you can do in the ipython prompt.  Instead of clicking enter to run a command you must press and hold the shift key (shift key image) and then hit enter.  So try

    ls # then press and hold shift and hit enter.

You should get the similar file listing view you saw at the ipython prompt.  

    pwd # will tell you where you are. Remember the shift key.  

You can retype over the previous commands in this interface and run them again by clicking on the box where you can rerun the same command or write a different one, by once again pressing and holding shift and enter when ready.

You may notice that each time you run a command, the number on the left is incremented by one.  This is because ipython stores a history of all your work, try

    history # remember your shift button!

This should list all the commands you've run so far.

The notebook is saved automatically so you can close the tab now and on your original notebook tab you will be able to find it by the title you gave it.  It should also have a big ready button on its line saying 'Shutdown'.  This tells you the notebook is still active.  

We will use these tools again and again as we go.

