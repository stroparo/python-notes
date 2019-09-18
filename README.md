# Python notes

## Strings

```python
s.lower()
s.upper()
s.index(substr) # ValueError raised if s does not contain substr
s.find(search_string) # -1 if not found
'0123'.isdigit() # True
'-1'.isdigit() # False
"hi, name".replace("name", "Bob")
'1 1 1'.replace('1', '2')
'\n hi \n'.strip() # hi
'\n hi \n'.lstrip() # 'hi \n'
'\n hi \n'.rstrip() # '\n hi'
'www.a.com'.lstrip('w.') # '.a.com'
```

---

## More string methods

```python
'1 2 3'.split() # ['1', '2', '3']
'1, 2, 3'.split() # ['1', '2', '3']
'1,,1,2'.split() # ['1', '', '1', '2']
s.startswith(tested_prefix)
```

---

## Sequences

```python
(list|tuple).count(some_string)
list.append(new_element)
```

### Join two lists

```python
list.extend(sequence) # same list
list1 + list2 # new list
```

### Adding & removing elements

```python
list.insert(index, new_element)
list.remove(element) # ValueError if does not exist
```

Do this to prevent ValueError while removing:

```python
if e in list:
    list.remove(e)
```

These will change the sequence:

```python
list.pop() # removes the last element
x.sort()
x.reverse()
x.clear()
```

---

## Dict's

```python
len(d) # number of keys
d[non_existent] # KeyError
d[x] == d.get(x) # get does not raise a KeyError, returns None
d.get(key, default_value)
d.pop(key) # returns value and removes the key, KeyError if does not exist
d.pop(key, default_value) # does not raise
d.setdefault(key, val) # if key exists does nothing and returns its value
d1.update(d2) # cascades d2's keys and values into d1
```

---

## Objects

```python
id(var) # ident code of the object
x is y # bool: x and y point to the same object?
```

### Mutable Objects

* Lists
* Dictionaries

IMPORTANT:

Beware of mutable object-ref as a default value, as this would work in the same fashion as a static variable.

A pattern to prevent this in an example of an empty array for the default value:

```python
def func(a=None):
    if a is None:
        a = []
```

### Immutable objects

* Integers
* Strings
* None
* Tuples

### Singletons

* Literals: Integers, Strings, True, False, None ...
  - x = 1
  - y = 1
  - x is y # True

---

## Truthiness

Empty sequences are false:

* []
* ()
* ''

So are:

* None
* 0
* 0.0

---

## Iteration tips

Both break and continue are usable both in for and while loops.

Practical tips:

```python
for key in dct: print(key)
range(n)
range(start, n)
range(start, n, step)

for index, elem in enumerate(some_sequence):
    ...
```

---

## Input function

```python
s = input('Type text: ')
```

---

## Keyword Arguments

```python
called(*args) # sequence unpacking
called(**args) # dict unpacking

sum(sequence_value) # builtin tip: function that sums the values of a sequence

kwargs.values() # kwargs is a dict

print(*args, sep='_', end='\n') # sep could also be any string
```

---

## Exceptions

The commonly seen KeyboardInterrupt exception is raised by ctrl+c.

```python
try:
    commands
except:
    commands
finally:
    commands # if no except given, finally's commands
             # execute before halting the function
             # ie before raising the exception
```

---
