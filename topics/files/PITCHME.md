## Files
+++
Working with files in python is very simple. the built-in function `open` opens and returns a file handle that can be used to read or write to a file. For example, the code
```
f = open('test.txt','r')
```
opens a file in read mode and assigns the file to the variable f. By this point, we have not actually loaded the file into memory, we've only just opened it and gotten a handler we can use to work with the file. Instead of 'r' as the mode, we can also use 'w' for writing and 'a' for appending. Also, we can open a file using the 'r+' mode which can handle both read and writes. Lastly, we can use the mode 'w+' to create a new file if it does not exist yet.
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
The file object also has many other methods on it such as f.readlines() which is used to read the whole file into memory at once and return the contents as a list of its lines. The f.read() method reads the whole file into memory as a single string. Another handy method is f.readline() which can be used to read the file line by line. This method can also be used to read a particular line by specifying the line number like f.readline(3).
+++
Writing to a file is just as easy as reading from it. the f.write(string) method will add a new line where the contents are a given string.
```
f = open('test.txt','w')
f.write('Hello World!')
f.close()
```
+++
As we briefly touched on before, you can use the `with` statement to open the file in a context manager which will handle closing the file for you:
```
with open('test.txt','r') as f:
    for line in f:
        print line
```
+++
### Working with yaml, json and CSV files.
Python has json, yaml and csv parser packages provided in the standard library to make working with these formats easier.
+++
```
import json
json_file = open('test.json','r')
data = json.load(json_file)
json_file.close()
```
```
import json
data = {'myKey':"This is the value","thing1":[1,2,3,4]}
f = open('test.json','w')
json.dump(data,f)
f.close()
```
