---
layout: post
title: list comprehensions, map and reduce in python

tags: 
- Python Study
---
Study notes about the diffrence between list comprehensions, map and reduce

### List comprehensions
``` python
[expression(i) for i in old_list if filter(i)]
```

It can be used to construct lists in a very natural, easy way, like a mathematician is used to do. The following are common ways to describe lists (or sets, or tuples, or vectors) in mathematics.

```
S = {x² : x in {0 ... 9}}
V = (1, 2, 4, 8, ..., 2¹²)
M = {x | x in S and x even}
```

In Python, you can write these expression almost exactly like a mathematician would do.

```python
 S = [x**2 for x in range(10)]
 V = [2**i for i in range(13)]
 M = [x for x in S if x % 2 == 0]
```

### map

```python
map(function\_to\_apply, list\_of\_inputs)
```

which allow us to pass all the list elements to a function one-by-one and then collect the output as a new list, for instance:

```python
items = [1, 2, 3, 4, 5]
squared = []
for i in items:
    squared.append(i**2)
```
    
How "_map_" do it:

```python
items = [1, 2, 3, 4, 5]
squared = map(lambda x: x**2, items)
```
I have made mistakes at these point:

- Object of map must be iterable.
- When the input of the internal function is a list,then the map which take this function as the first parameter，should have a list of list as the second prameter. As below:

```python
def str_list(l):
    new_l = ""
    for item in l:
        new_l= new_l+str(item)
    return new_l
    # use map to rewrite str_list()

 map(str_list,[[1,2,3,4,5][2,3,4,5,6])
```

### reduce 
``` python
reduce(function\_to\_apply, list\_of\_inputs)
```

`reduce` will performing some computation on a list and returning the result. For example, compute the product of a list of integers. So the normal way you might go about doing this task in python is using a basic for loop:

```python
items = [1, 2, 3, 4, 5]
for i in items:
    s +=i
```

use `reduce` do do the same thing:

```python
s = reduce((lambda x, y: x * y), [1, 2, 3, 4])
```
when you need to use reduce, here are several requests need to be fill:

  * function\_to\_apply must return a single result( a string , or a list...)
  * type of _elements_ from list\-of\-inputs must be the same as _result_
  
  
### Different implementation of computing Manhatten distance for two vectors(v,w)
 
 * list comprehensions
 
```python
def manhatten_distance(v,w):
    return sum([abs(v_i - w_i) for v_i, w_i in zip(v, w)])
manhatten_distance((1,2,3),(2,3,4))

```
 
 * map

```python
def manhatten_distance(v,w):
    return sum(map(lambda (a, b) : abs(a-b),zip(v,w)))
manhatten_distance((1,2,3),(2,3,4))

``` 
 * reduce

```python
def manhatten_distance(v,w):
    return reduce(lambda a,b :a+b, map(lambda (a, b) : abs(a-b),zip(v,w)))
manhatten_distance((1,2,3),(2,3,4))

```  
  
 
 
