## Standard Library
Python has a very robust Standard Library (often abbreviated stdlib). We will be going over some of my favorite packages
+++
### os
The os module makes working with misc os interfaces easier. Common operations you will see done in the os module are:
- os.environ - a dictionary of environment variables available to the python process
```
import os
print os.environ.get('HOME')
>>> /home/austin
```
- os.getcwd() - gets the current directory the user is in
+++
- os.listdir(path) - Return a list containing the names of the entries in the directory given by path
- os.mkdir(path[, mode]) - Create a directory named path with numeric mode mode. The default mode is 0777. If the directory already exists, OSError is raised.
- os.makedirs(path[, mode]) - Recursive directory creation function. Like mkdir(), but makes all intermediate-level directories needed to contain the leaf directory. Raises an error exception if the leaf directory already exists or cannot be created. The default mode is 0777
+++
- os.remove(path) - remove the file
- os.removedirs(path) - Remove directories recursively.
- os.walk - Generate the file names in a directory tree by walking the tree either top-down or bottom-up. For each directory in the tree rooted at directory top (including top itself), it yields a 3-tuple (dirpath, dirnames, filenames).
```
import os
from os.path import join, getsize
for root, dirs, files in os.walk('python/Lib/email'):
    print root, "consumes",
    print sum(getsize(join(root, name)) for name in files),
    print "bytes in", len(files), "non-directory files"
    if 'CVS' in dirs:
        dirs.remove('CVS')  # don't visit CVS directories
```
