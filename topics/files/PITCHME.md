## Files
+++
Working with files in python is very simple. the built-in function `open` opens and returns a file handle that can be used to read or write to a file. For example, the code
```
f = open('test.txt','r')
```
opens a file in read mode and assigns the file to the variable f. By this point, we have not actually loaded the file into memory, we've only just opened it and gotten a handler we can use to work with the file. Instead of 'r' as the mode, we can also use 'w' for writing and 'a' for appending.
+++
Text files are easy to work with in python as we can use a for loop to iterate through lines
```
f = open('test.txt','r')
for line in f:
    print line
f.close()
```
Reading one line at a time has the nice quality that not all the file needs to fit in memory at one time so it makes working with large files easy.
+++
The file object also has many other methods on it such as f.readlines() which is used to read the whole file into memory at once and return the contents as a list of its lines. The f.read() method reads the whole file into memory as a single string. 
