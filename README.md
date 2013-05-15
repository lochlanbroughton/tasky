DESCRIPTION
===========

This is a desktop client for Google Tasks that runs in the command line. It
provides a fast way to interface with all task lists of a user and make 
changes and updates very quickly. This program has been designed to make as
few API calls as possible in order to optimize performance.
 
DEPENDENCIES
===========

Requires Python 2.7, the GNU Readline library (`sudo easy_install readline`), 
and the [Google API client for Python](http://code.google.com/p/google-api-python-client/).

**NOTE**: In order to allow your instance of Tasky to successfully make Tasks API calls, you must first
register your project with Google. The details of this process are outlined on this [page](https://developers.google.com/google-apps/tasks/firstapp).

USAGE
=====
  
Quick Mode
----------

This mode is primarily to make very quick changes to the task list in a non-interactive fashion.

### Common Operations ###

#### Adding a task (`a`):

    $ python tasky.py a --title "Title of task" --date "5/14/11" --note "This is a note."
     --parent "Parent task name"

OR

    $ python tasky.py a -t "Title of task" -d "5/14/11" -n "This is a note." -p "Parent task name"
            
All of the above fields are optional except for the title and can appear in any order.

#### Removing a task and its children (`r`):

    $ python tasky.py r --title "Title of task"

OR

    $ python tasky.py r -t "Title of task"
            
#### Toggling a task and its children (`t`):

    $ python tasky.py t --title "Title of task"

OR

    $ python tasky.py t -t "Title of task"

#### Listing all tasks (`l`):

    $ python tasky.py l

**Note:** The task list can be printed after the execution of the operation by 
adding a (`--list`) or (`-l`) flag to the command.
    
Normal Mode
-----------

This mode is intended for making interactive changes to the task list (less to remember too!).

Invoke Tasky by just doing:

    $ python tasky.py
    
Then follow the on-screen instructions to interact with the list in some way.     

### Tab Completion ###

Tab-completion is supported, so you can type the beginning of an existing task name. For example:

     Name of task: Lea<TAB>

If there is more than one match, all matches will be listed on the second tab:

     Name of task: Lea<TAB><TAB>
     Learn Java  Learn C++

Otherwise, the task name will be filled in.

### Partial String Searching ###

In addition, Tasky also support partial string searching, so you 
can type just any consecutive portion of any task name when searching for it. 
All of the matched results will be displayed and you can specify the number
for the result you desire.
