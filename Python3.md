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
```
