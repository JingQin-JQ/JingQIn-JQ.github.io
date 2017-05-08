---
layout: post
title: Buildinsfrom Hackerrank

tags: 
- Python Study
---
Study notes about Buildins

### Zip
zip([iterable, ...])

This function returns a list of tuples. The (i)th tuple contains the (i)th element from each of the argument sequences or iterables.

If the argument sequences are of unequal lengths, then the returned list is truncated to the length of the shortest argument sequence.
 
* Example:

Task

The National University conducts an examination of  N students in X subjects. 
Your task is to compute the average scores of each student.

Average score = (sum of scores obtained in all subjects by a student)/ (Total number of subjects)

The format for the general mark sheet is:

Student ID | 1 2 3 4 5               
Subject  1 |  89     90      78     93     80

Subject 2   |  90     91      85     88    86  
Subject 3   |  91     92      83      89    90.5
            
Average    |  90    91    82    90    85.5 

Input Format

The first line contains N and X separated by a space. 
The next X  lines contains the space separated marks obtained by students in a particular subject.

Constraints

0 < N <= 100

0 < X <= 100
 

Output Format

Print the averages of all students on separate lines.

The averages must be correct up to 1 decimal place.

```python
N, X = map(int, raw_input().split())

subjects = list()

for i in range(0, X):
    subjects.append(list(map(float, raw_input().split())))

students = zip(*subjects)

for i in range(0, N):
    marks = 0.0
    for j in range(0, X):
        marks += students[i][j]
    print marks / X
```
```
input:
5 3
89 90 78 93 80
90 91 85 88 86 
91 92 83 89 90.5
output:
90.0
91.0
82.0
90.0
85.5
```
<https://www.hackerrank.com/challenges/zipped>

### eval
The eval() expression is a very powerful built-in function of Python. It helps in evaluating an expression. The expression can be a Python statement, or a code object.

For example:

```
>>> eval("9 + 5")
14
>>> x = 2
>>> eval("x + 3")
5
```
Here, eval() can also be used to work with Python keywords or defined functions and variables. These would normally be stored as strings.

For example:

```
>>> type(eval("len"))
<type 'builtin_function_or_method'>

Without eval()

>>> type("len")
<type 'str'>    
```
Task 
You are given an expression in a line. Read that line as a string variable, such as var, and print the result using eval(var).

NOTE: Python2 users, please import from _ _future__ import print_function.

Constraint 
Input string is less than 100 characters.

* Code:

```python
from __future__ import print_function
x = str(raw_input())
eval(x)
```
```
input:
print (2+4)
output:
6
```
<https://www.hackerrank.com/challenges/python-eval>

### reduce
* Example:
You are given a string S. 
S contains alphanumeric characters only. 
Your task is to sort the string S in the following manner:

All sorted lowercase letters are ahead of uppercase letters.
All sorted uppercase letters are ahead of digits.
All sorted odd digits are ahead of sorted even digits.
Input Format

A single line of input contains the string S.

Constraints

0<len(S) < 1000

Output Format

Output the sorted string S. 

```python
from string import ascii_lowercase, ascii_uppercase

order = ascii_lowercase + ascii_uppercase + "1357902468"


print (reduce(lambda x,y: x+y, sorted(raw_input(), key=order.index)))
```
```
input:
Sorting1234
output:
ginortS1324
```
<https://www.hackerrank.com/challenges/ginorts>