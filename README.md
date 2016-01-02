PythonCheatSheet
================

Python 2.7

```python
# coding: utf-8
```

```python
# important built-in types: None, bool (True/False), int, long, float, str, unicode, list, dict, tuple (and some others)
n = 30.5
print str(n)        # 30.5
print str(int(n))   # 30
print str(bool(n))  # True

h = 0xFF
print str(h)        # 255
```

```python
# Compare: ==, <, >, <=, >=, !=
# Bitwise: & (AND), | (OR), ^ (XOR), ~ (COMPLEMENT), << (SHIFT LEFT), >> (SHIFT RIGHT)
# Logical: and, or, not
```

```python
# if, elif, else
b = True
if b == True:     # short form => "if b:"
  print "Yes, it's true."
else:
  print "Did you change the value of b?"
# Yes, it's true.
```

```python
# while
i = 2
while i > 0:
  print str(i) + " > 0"
  i -= 1                    # i = i - 1
# 2 > 0 and 1 > 0
```

```python
# for, in, range()
for i in range(2, 10, 2):   # range(start = 2, stop = 10, step = 2)
  print str(i)
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
  print str(i)
# 0, 1, 3 and 4
```

```python
# string[], len()
first_string = "Hello world!"
print first_string            # Hello world!
print str(len(first_string))  # 12 (amount of characters => 0-11)
print first_string[:5]        # Hello (characters 0-4)
print first_string[6:11]      # world (characters 6-10)
print first_string[11:]       # ! (character 11)
```
| H | e | l | l | o |   | w | o | r | l | d | ! | DIRECTION |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | from left |
| -12 | -11 | -10 | -9 | -8 | -7 | -6 | -5 | -4 | -3 | -2 | -1 | from right |

```python
# string.index(), string.count()
first_string = "Hello world!"
if "w" in first_string:
  a = first_string.index("w")
  print "index of 'w' in first_string"
  print "a  = " + str(a)
if "l" in first_string:
  b = first_string.count("l")
  print "amount of character 'l' = " + str(b)
# index of 'w' in first_string
# a = 6
# amount of character 'l' = 3
```

```python
# list, type()
l = ["This", "is", "my", "list", 1, 2, True, 30.5]
for item in l:
  print str(item) + " [" + type(item).__name__ + "]"
print l[0:-4]
# This [str], is [str], my [str], list [str], 1 [int], 2 [int], True [bool] and 30.5 [float]
# ['This', 'is', 'my', 'list']
```
