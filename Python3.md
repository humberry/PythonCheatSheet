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
# string.find(), string.format(), string.count()
first_string = "Hello world!"
if "w" in first_string:
  a = first_string.find("w")
  print("position of 'w' in first_string")
  print("a  = {}".format(a))
#print("format a float value to limit the decimal places = {0:.2f}".format(12.3456789))  #12.34
#print("No Newline at the end!", end='')
#print('string1', 'string2', 'string3', sep='/')  # string1/string2/string3
if "l" in first_string:
  b = first_string.count("l")
  print("amount of character 'l' = {0}".format(b))  # {0} => 0 is not necessary, because there is only one variable (b) and we don't want to change the print order...
# position of 'w' in first_string
# a = 6
# amount of character 'l' = 3
```

```python
# f strings
name = 'my name'
message = f'{name} is a secret!'
print(message)      # my name is a secret!

amount = 5
print(f'{amount * 5}')  # 25

hex = 0xFF
print(f'{hex}')     # 255
print(f'{hex:b}')   # 11111111
print(f'{hex:c}')   # like chr(c)
print(f'{hex:e}')   # 2.550000e+02
print(f'{hex:f}')   # 255.000000
print(f'{hex:o}')   # 377
print(f'{hex:x}')   # ff
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
