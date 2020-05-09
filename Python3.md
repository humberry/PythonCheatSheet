Python 3.x Cheat Sheet
======================
<br>

```python
# The default encoding for Python source code is UTF-8
```

[Unicode HOWTO](https://docs.python.org/3/howto/unicode.html)<br>
[Strings, Unicode and bytes](https://medium.com/@andreacolangelo/strings-unicode-and-bytes-in-python-3-everything-you-always-wanted-to-know-27dc02ff2686)<br>

| H | e | l | l | o |   | w | o | r | l | d | ! | DIRECTION |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | from left |
| -12 | -11 | -10 | -9 | -8 | -7 | -6 | -5 | -4 | -3 | -2 | -1 | from right |

```python
# string[], len()
first_string = "Hello world!"
print(first_string)            # Hello world!
print(len(first_string))       # 12 (amount of characters => 0-11)
print(first_string[:5])        # Hello (characters 0-4)
print(first_string[6:11])      # world (characters 6-10)
print(first_string[11:])       # ! (character 11)
```

```python
# string.format(), string.count()

print("format a float value to limit the decimal places = {0:.2f}".format(12.3456789))  #12.34
print("No Newline at the end!", end='')
print('string1', 'string2', 'string3', sep='/')  # string1/string2/string3

first_string = "Hello world!"
if "l" in first_string:
  b = first_string.count("l")
  print("amount of character 'l' = {0}".format(b))  # {0} => 0 is not necessary, because there is only one variable (b) and we don't want to change the print order...
# amount of character 'l' = 3
```

```python
# string.find() => find all "is" strings in s 
s = "This is my test string which is much longer than this other string."
i = 0                   # start position
l = []                  # empty list
while i != -1:
  i = s.find("is", i)   # i = position or -1
  if i != -1:
    l.append(i)
    i += 1
print(l)                # [2, 5, 29, 51]
```

```python
# f strings
name = 'my name'
message = f'{name} is a secret!'
print(message)      # my name is a secret!

amount = 5
print(f'{amount * 5}')  # 25

value = 0xFF
print(f'{value}')     # 255
print(f'{value:b}')   # 11111111
print(f'{value:c}')   # like chr(c)
print(f'{value:e}')   # 2.550000e+02
print(f'{value:f}')   # 255.000000
print(f'{value:o}')   # 377
print(f'{value:x}')   # ff
```

```python
# important built-in types: None, bool (True/False), int, long, float, str, unicode, list, dict, tuple (and some others)
n = 30.5
print(n)             # 30.5
print(int(n))        # 30
print(bool(n))       # True

h = 0xFF
print(h)             # 255
print(chr(65))       # A
print(ord("A"))      # 65
print(hex(255))      # 0xff
```

```python
# Compare: ==, <, >, <=, >=, !=
# Bitwise: & (AND), | (OR), ^ (XOR), ~ (COMPLEMENT), << (SHIFT LEFT), >> (SHIFT RIGHT)
# Logical: and, or, not
# Escape Sequence: \\ (\), \r (CR), \n (LF), \' ('), \" ("), \t (TAB), \x41 (A), \u0000 (16bit Unicode), \U00000000 (32bit Unicode)
```

```python
# if, elif, else
b = True
if b == True:     # short form => "if b:"
  print("Yes, it's {}".format(b))
else:
  print("Did you change the value of b?")
# Yes, it's True.
```

```python
# while
i = 2
while i > 0:
  print("{}  > 0".format(i))
  i -= 1                    # i = i - 1
# 2 > 0 and 1 > 0
```

```python
# for, in, range()
for i in range(2, 10, 2):   # range(start = 2, stop = 10, step = 2)
  print(i)
# 2, 4, 6 and 8
```

```python
# break, continue, pass
for i in range(0, 10):      # range(start = 0, stop = 10, step = 1)
  if i == 1:
    pass                    # do nothing
  elif i == 2:
    continue                # don't print 2
  elif i == 5:
    break                   # loop interruption
  print(i)
# 0, 1, 3 and 4
```

```python
try:
    print(4/1)
    print(4/0)
    print(4/2)
#except ZeroDivisionError:
    #print('division by 0 => not possible')
except Exception as e:
    print(e)
finally:
    #e.g. close file, ...
    print('bye')
# 4.0
# division by zero
# bye
```

```python
# list, type()
l = ["This", "is", "my", "list", 1, 2, True, 30.5]
for item in l:
  print(str(item) + " [" + type(item).__name__ + "]", end='')
print()
print(l[0:-4])
# This [str] is [str] my [str] list [str] 1 [int] 2 [int] True [bool] 30.5 [float]
# ['This', 'is', 'my', 'list']
```

```python
# list.remove(), .insert(), .append(), .extend(), .sort(), .reverse(), del
la = ["This", "is"]
lb = ["my", "list"]
la.extend(lb)         # la = ["This", "is", "my", "list"]         ### la = la + lb ###
print(la)
la.remove("list")     # la = ["This", "is", "my"]                 ### del la[3] ###
print(la)
la.insert(3, "new")   # la = ["This", "is", "my", "new"]          
print(la)
la.append("list")     # la = ["This", "is", "my", "new", "list"]
print(la)
la.sort()             # la = ["This", "is", "list", "my", "new"]
print(la)
la.reverse()          # la = ["new", "my", "list", "is", "This"]
print(la)
```

```python
l1 = [1,2,3]
print(f'l1 = {l1}')
l2 = [l1,'one','two','three']
print(f"l2 = [l1,'one','two','three'] = {l2}")
print()
del l1[2]
print('> del l1[2]')
l3 = l2
print('> l3 = l2')
l4 = l2.copy()
print('> l4 = l2.copy()')
l2[0] = 5
print('> l2[0] = 5')
print()
print(f'l1 = {l1}')
print(f'l2 = {l2}')
print(f'l3 = {l3}')
print(f'l4 = {l4}')

#l1 = [1, 2, 3]
#l2 = [l1,'one','two','three'] = [[1, 2, 3], 'one', 'two', 'three']

#> del l1[2]
#> l3 = l2
#> l4 = l2.copy()
#> l2[0] = 5

#l1 = [1, 2]
#l2 = [5, 'one', 'two', 'three']
#l3 = [5, 'one', 'two', 'three']
#l4 = [[1, 2], 'one', 'two', 'three']
```

```python
# immutable tuple
t = ("This", "is", "a", "tuple")
del t[0]            # TypeError: 'tuple' object doesn't support item deletion
```

```python
# dict
d = { "car" : 100,                      # key : value
      "ship" : 70,
      "plane" : 50}
print(f'Length of d = {str(len(d))}')   # Length of d = 3
for key in d.keys():
  print(key)                            # car, ship, plane
for value in d.values():
  print(value)                          # 100, 70, 50
for item in d.items():
  if item[1] == 70:                     # item = tuple = ('key', value)
    print(f'Found {item[0]}')           # Found ship
value = d.get("ship")                   # value = 70 or None if key is missing
print(f'value of ship = {value}')       # value of ship = 70
```

```python
# Regular Expressions
#
# raw_string = r"\"   vs. plain_string = "\\"
# . (any char), [^a] (not a), [A-Z] (A-Z), [A-Za-z] (A-Z and a-z), [0-9] == \d (only digits)
# \s (whitespace chars), [A-Za-z0-9_] == \w
# ? (left char once or never), + (left char once or several times), * (left char not, once or several times)
# {2} (left char have to exist twice), {1,} (left char once or several times), {1,2} (left char have to exist once or twice)
#
import re

s = "This \r\nis \ta -special- string!"
l = re.split(r"[^\w]+", s)              # or re.split(r"[^A-Za-z]+", s)
print(l)                                # ['This',  'is',  'a', 'special', 'string', '']
l = re.split(r"\s+", s)
print(l)                                # ['This', 'is', 'a', '-special-', 'string!']
l = re.findall(r"i[a-z]", s)
print(l)                                # ['is', 'is', 'ia', 'in']
#re.compile(pattern, flags) => flags e.g. re.IGNORECASE
#re.split(";") => e.g. to split semicolon separated data
#re.sub("is", "at", s) => That at a ...
```

```python
# read/write textfile
# see also .readline(), .readlines(), .writelines()
filename = "data.txt"
file = open(filename, 'a')          # append/create file
file.write("A new line in data.\n")
file.close()

file = open(filename, 'r')          # read file
print(file.read())                  # A new line in data.\n (every time you start the script a new line is added)
file.close()
```

```python
# read/write binaryfile
# see also .seek(), .tell()
filename = "data.dat"
file = open(filename, 'wb')           # write/create binary file
l = [0,1,2,128,255]
b = bytearray(l)
file.write(b)
file.close()

file = open(filename, 'rb')           # read binary file
s = file.read()
for item in s:
  print(f'{item} = 0x{item:x}')       # 0 = 0x0 ... 255 = 0xff
file.close()
```

```python
# read/write csvfile
import csv

filename = "data.csv"
file = open(filename, 'w')                                  # write/create binary file
la = ['column1', 'column2', 'column3', 'column4']
lb = ['text with spaces', '1/1/2016', 4567.12, '12:00:00']
csvwriter = csv.writer(file, delimiter=';')                 # delimiter=',' is default
csvwriter.writerow(la)
csvwriter.writerow(lb)
file.close()

file = open(filename, 'r')                                  # read binary file
csvreader = csv.reader(file, delimiter=';')                 # delimiter=',' is default
for l in csvreader:
  print(l)                                                  
  # ['column1', 'column2', 'column3', 'column4']
  # ['text with spaces', '1/1/2016', '4567.12', '12:00:00']
  # data.csv:
  # column1;column2;column3;column4
  # text with spaces;1/1/2016;4567.12;12:00:00
file.close()
```

```python
# os.getcwd(), .path.expanduser('~'), ...
# see also .uname() and .environ for information about your os
import os

print(os.getcwd())                   # current working directory
print(os.path.expanduser('~'))       # user's HOME directory
print(os.listdir('/'))               # show root directory (r'C:\' should work for Windows)
print(os.path.exists(path))          # True/False if file/directory exists or not (see also os.access())
print(os.path.split(path))           # tuple with directory-path and filename
print(os.path.getsize(path))         # file size in bytes
```

```python
# sys.version , .path, .exit()
import sys

print(sys.version)                   # Python version
print(sys.path)                      # show PYTHONPATH
sys.path.append(path)                # add an additional path
sys.exit()                           # exit the python script (doesn't make sense at the end)
```

```python
# SQLite 3
import sqlite3

sqlcon = sqlite3.connect("test.db")     # sqlite.connect(":memory:") won't be stored
sqlcur = sqlcon.cursor()
sqlcur.execute("CREATE TABLE table1 (id INTEGER PRIMARY KEY, name TEXT, birthday TEXT)")
sqlcur.execute("INSERT INTO table1 (id, name, birthday) VALUES (NULL, 'myname', '2016-01-01')")
sqlcon.commit()
sqlcon.close()

sqlcon = sqlite3.connect("test.db")
sqlcur = sqlcon.cursor()
sqlcur.execute("SELECT * FROM table1")
sqldata = sqlcur.fetchone()             # .fetchone() => get the first record or use .fetchall()
print(sqldata)                          # (1, 'myname', '2016-01-01')
sqlcon.close()

# data types: NULL, INTEGER, REAL, TEXT and BLOB

# Delete all records in table1:
# sqlcur.execute("DELETE FROM table1")
# sqlcon.commit()

# Delete a particular record in table1:
# sqlcur.execute("DELETE FROM table1 WHERE id=0")
# sqlcon.commit()

# Delete whole table1:
# sqlcur.execute("DROP TABLE IF EXISTS table1")
# sqlcon.commit()

# Change data in a particular record in table1:
# sqlcur.execute("UPDATE table1 SET name=? WHERE id=?", (name, id))
# sqlcon.commit()

# Adding a column to a table
# sqlcur.execute("ALTER TABLE table1 ADD COLUMN 'hobby' TEXT")
# sqlcon.commit()

# Working with Variables:
# sqlcur.execute("INSERT INTO table1 VALUES (?, ?, ?)", (var1, var2, var3))
# sqlcur.execute("SELECT name, birthday FROM table1 WHERE id = (?)", (id,))
# sqlcon.commit()

# Find all tables in current database:
# sqlcur.execute("SELECT name FROM sqlite_master WHERE type='table')
# sqldata = sqlcur.fetchall()

# SELECT COUNT(*) FROM table1                                   # how many records are in table1?
# SELECT * FROM table1 JOIN table2 ON table1.id = table2.t1id WHERE name='myname' ORDER BY birthday;
# ORDER BY DESC birthday;                                       # (default:ASC) / DESC (larger values first)
# SELECT name AS nickname, birthday AS bd FROM table1;          # AS define an ALIAS
# SELECT t1.name, t1.birthday FROM table1 as t1;                # ALIAS for table1
# SELECT t1.name, COUNT(*) AS samename FROM table1 as t1 GROUP BY t1.name; # how many users have the same name?
# search for a picture "SQL JOINS" with your favorite search engine
```

```python
if __name__ == '__main__':
    #this code will be ignored if you import the script as module
```

```python
import module            #module.class() or module.methode()
import package.module    #package.module.class() or package.module.methode()
from module import *                    #class() or methode()
from module import methode1, methode2    #methode1() or methode2()

help('modules')         # show all installed modules
```


External links disclaimer:<br>
I'm not responsible for the content of external websites.<br>
