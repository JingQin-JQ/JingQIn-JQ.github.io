---
layout: post
title: Basic Data Types Challenges from Hackerrank

tags: 
- Python Study
---
Study notes about list comprehensions, map, lambda and sort

### list comprehensions 

List comprehensions are an elegant way to build a list without having to use different for loops to append values one by one. 

``` python

ListOfThreeMultiples = [x for x in range(10) if x % 3 == 0] 
# Multiples of 3 below 10
>> ListOfThreeMultiples
[0, 3, 6, 9]
```

##### Sample of using list comprehensions
Question:
<https://www.hackerrank.com/challenges/list-comprehensions>

Code:

```python

if __name__ == '__main__':
    x = int(raw_input())+1
    y = int(raw_input())+1
    z = int(raw_input())+1
    n = int(raw_input())
    lst = [[i,j,k] for i in range(x) for j in range(y) for k in range(z) if i+j+k != n]
    print lst
```

### map
The map() function applies a function to every member of an iterable and returns the result. Typically, one would use an anonymous inline function as defined by lambda, but it is possible to use any function. 

As: map(function, list-1) returns a list-2

Every element in list-1 was operated by function, and the results were put into list-2 as its elements.


``` python
def square(x):
    return x**2
squares = map(square, range(10))
print squares

[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```


##### Sample of using map
Question:
<https://www.hackerrank.com/challenges/python-tuples>

Code:

```python

if __name__ == '__main__':
    n = int(raw_input())
    integer_list = map(int, raw_input().split())
    print integer_list
    print hash(tuple(integer_list))
```
### lambda
Lambda is a simple (no statements allowed internally) anonymous inline function.

As: lambda x: x**2  returns the square of its argument.

lambda forms can be used as the required function argument to the map() function. For example, the example for map can be written as

```python
squares = map(lambda x: x**2, range(10))
print squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81
```

### sort and sorted
##### Differents

list.sort() is only defined for lists. It modifies the list in-place (and returns None to avoid confusion).

sorted()returns a new sorted list,and accepts any iterable.

##### key parameter
Both list.sort() and sorted() can use a key parameter to specify a function to be called on each list element prior to making comparisons.The value of the key parameter should be a function that takes a single argument and returns a key to use for sorting purposes.

list.sort(list, key=function())

sorted(list,key=function())

```python
sorted("This is a test string from Andrew".split(), key=str.lower)

['a', 'Andrew', 'from', 'is', 'string', 'test', 'This']
```

##### Sample of using lambda in sorted
Question:<https://www.hackerrank.com/challenges/nested-list>

Code:

```python

students = []
sec_name = []
second_low = 0
n = int(raw_input())
for _ in range(n):
    name = raw_input()
    score = float(raw_input())
    students.append([name,score])
print students
order =sorted(students, key = lambda x: int(x[1]))
print order
for i in range(n):
    if order[i][1] != order[0][1]:
        second_low = order[i][1]
        break
   
    
print second_low

sec_name = [x[0] for x in order if x[1] == second_low]
sec_name.sort()

for name in sec_name:
    print name  
```