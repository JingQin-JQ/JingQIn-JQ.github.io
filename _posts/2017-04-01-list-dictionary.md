---
layout: post
title: Study notes about funtion return, list and dictionary
tags: 
- Python Study
---
### Return

Only when I want to quit my functions, multiple returns is acceptable.

```python 
def get_class_average(students):
    results = []
    for each in students:
        result=get_average(each)
        results.append(result)
    return average(results)
```
### Get elements from list

* list-name[Serial number]   remember serial numbers start from 0

```python
a = [1,2,3]
print a[2]
```
```python
output: 3
```
 
* the tpye of list-name[1] is the element it self.

```python
a = [1,"h",3]
print type(a[2])
```
```python
output: <type 'int'>
```

* the type of list-name [1:4] is a list

```python
a = [1,"h",3]
print type(a[2:3])
```
```python
output: <type 'list'>
```

### Get element from dictionary

* dictionary-name[key]

```python
a = {"Jing":"girl", "Zhe":"boy"}
print a["Zhe"]
```
```python
output: boy
```


**links of _Data Structures_ in the _The Python Tutorial_**
<https://docs.python.org/3/tutorial/datastructures.html>