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
if "l" in first_string:
  b = first_string.count("l")
  print("amount of character 'l' = {0}".format(b))
# position of 'w' in first_string
# a = 6
# amount of character 'l' = 3
```
