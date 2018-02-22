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
+++
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
+++
the os.path module is where working with files gets much easier
- os.path.abspath(path) - Return a normalized absolutized version of the pathname path.
```
import os
print os.path.abspath('pythonClass')
/Users/austin/Things/MoreThings/pythonClass
```
+++
- os.path.basename(path) - Return the base name of pathname path.
```
import os
print os.path.basename('/Users/austin/Things/MoreThings/pythonClass')
pythonClass
```
- os.path.dirname(path) - Return the directory name of pathname path.
```
import os
print os.path.dirname('/Users/austin/Things/MoreThings/pythonClass')
/Users/austin/Things/MoreThings
```
+++
- os.path.exists(path) - Return True if path refers to an existing path
- os.path.isfile(path) - Return True if path is an existing regular file.
- os.path.isdir(path) - Return True if path is an existing directory
+++
- os.path.join(path, paths) - Join one or more path components intelligently. The return value is the concatenation of path and any members of paths
```
import os
print os.path.join('/home/austin','my-project')
>>> /home/austin/my-project
print os.path.join('/home/austin','my-project','a-folder')
>>> /home/austin/my-project/a-folder
```
+++
### Logging
Python has a fairly simple logging package.
```
import logging
logging.basicConfig(filename='example.log',level=logging.DEBUG)
logging.debug('This message should go to the log file')
logging.info('So should this')
logging.warning('And this, too')
```
@[2](You can define a log level so python will only log when the log was logged with that level and above)
@[2](Setting the level to debug will print all debug, info, and warning statements)
@[2](For this logger, we are logging out to the file example.log)
+++
```
import logging
logging.basicConfig(format='%(levelname)s:%(message)s', level=logging.DEBUG)
logging.debug('This message should appear on the console')
```
@[2](We can also change the format of the logged message using special parameters)
@[2](In this example since we are not specifying a log file, it will just log to standard out)
+++
You can have multiple loggers in a program. Lets say for a big application, all of the packages that make up that application define their own logger. This gives the programmer more granular control over logging.
+++
```
import logging
logger = logging.getLogger('simple_example')
logger.setLevel(logging.DEBUG)

ch = logging.StreamHandler()
ch.setLevel(logging.DEBUG)

formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
ch.setFormatter(formatter)
logger.addHandler(ch)

logger.debug('debug message')
logger.info('info message')
logger.warn('warn message')
logger.error('error message')
logger.critical('critical message')
```
@[2](Create the logger)
@[3](Set the log level)
@[5](Create a new handler that prints to the console)
@[6](Set this log handler to a debug log level)
@[8](Create a custom log format)
@[9](Add the formatter to the stream handler)
@[10](Add this handler to our logger)
@[12](Print a debug message)
@[14](Print a warning statement)

+++
### Argparse
The argparse module is the recommended module for creating command line application. It is fairly log level but there are many 3rd party packages that wrap it and make it easier to use
```
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("list",help="List stuff")
parser.add_argument("--debug",action='store_true', help="Run with Debug")
args = parser.parse_args()
if args.debug:
    'Im in debug mode!'
if args.list:
    print 'Listing!!!'
```
@[2](Create the parser)
@[3](Add a positional argument)
@[4](Add a optional argument)
@[4](This argument will be stored as True when set)
@[5](Parse the arguments)
@[6](If --debug was set)
+++
### Datetime
The datetime package is the module python uses for working with dates and times.
```
import re
```
