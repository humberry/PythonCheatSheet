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
# Logical: & (AND), | (OR), ^ (XOR), ~ (COMPLEMENT), << (SHIFT LEFT), >> (SHIFT RIGHT)
```

```python
# if, elif, else
b = True
if b == True:     # short form = "if b:"
  print "Yes it's true."
else:
  print "Did you change the value of b?"
```

```python
# while
i = 2
while i > 0:
  print str(i) + " > 0"
  i -= 1          # i = i - 1
```

```python
# for
for i in range(2, 10, 2):   # range(start, stop, step)
  print str(i)              # only even values (2, 4, 6 and 8)
```
