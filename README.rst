===========
slack_magic
===========


`slack_magic` defines an IPython magic function to send notifications to a slack app when a process completes or fails.


Description
===========

Install using `pip install slack_magic`

Load the extension within Jupyter or IPython `%load_ext slack_magic`

The first time you run `%notify` it will ask for your slack app webhook url. After that it will be stored in `~/.slack_magic`.

Use the magic as either a cell or a line magic:

.. code-block:: python

   %load_ext slack_magic
   
   # Send a confirmation that a line has run
   %notify "Nothing wrong with this code"

   # Send traceback to slack when an error is raised
   %notify 1 / 0

   # Send a confirmation that a cell has run
   %%notify
   "Nothing wrong with this code either"
   a = 10
   b = 144
   
   # Send traceback to slack when an error is raised in the cell
   %%notify
   "This won't fail"
   "But the next line will"
   1 / 0

