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
  print str(i) + " > 0"     # 2 > 0 and 1 > 0
  i -= 1                    # i = i - 1
```

```python
# for, in, range()
for i in range(2, 10, 2):   # range(start, stop, step)
  print str(i)              # only even values (2, 4, 6 and 8)
```

```python
# break, continue, pass
for i in range(0, 10):      # range(start, stop, step = 1)
  if i == 1:
    pass                    # do nothing
  elif i == 2:
    continue                # don't print 2
  elif i == 5:
    break                   # loop interruption
  print str(i)              # 0, 1, 3 and 4
```
