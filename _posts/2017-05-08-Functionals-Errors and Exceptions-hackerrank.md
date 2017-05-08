---
layout: post
title: Functionals-Errors and Exceptions from Hackerrank

tags: 
- Python Study
---
Study notes about Functionals-Errors and Exceptions

### Map and Lambda Function

The map() function applies a function to every member of an iterable and returns the result. It takes two parameters: first, the function that is to be applied and secondly, the iterables. 
Let's say you are given a list of names, and you have to print a list that contains the length of each name.

```
print (list(map(len, ['Tina', 'Raj', 'Tom'])))  
[4, 3, 3]  
```
Lambda is a single expression anonymous function often used as an inline function. In simple words, it is a function that has only one line in its body. It proves very handy in functional and GUI programming.

```
sum = lambda a, b, c: a + b + c
sum(1, 2, 3)
6
```

* Examples

Lambda functions cannot use the return statement and can only have a single expression. Unlike def, which creates a function and assigns it a name, lambda creates a function and returns the function itself. Lambda can be used inside lists and dictionaries.

Input Format

One line of input: an integer N.

Constraints
0<=N<=15

Output Format

A list on a single line containing the cubes of the first N fibonacci numbers.

```python
cube = lambda x: x**3# complete the lambda function 

def fibonacci(N):
    # return a list of fibonacci numbers
    if N == 0:
        fibs = []
    elif N == 1:
        fibs = [0]
    else:
        fibs = [0, 1]

    if N > len(fibs):
        for i in range(2,N):
             fibs.append(fibs[i-1] + fibs[i-2])
    return fibs

N = int(raw_input())
fibs = fibonacci(N)
print map(cube, fibs)
```
```python
input:
5
output:
[0, 1, 1, 8, 27]
```
<https://www.hackerrank.com/challenges/map-and-lambda-expression>

### regular expression in lambda and filter
* Example:

You are given an integer N followed by N  email addresses. Your task is to print a list containing only valid email addresses in lexicographical order.


Valid email addresses must follow these rules:

It must have the username@websitename.extension format type.
The username can only contain letters, digits, dashes and underscores.
The website name can only have letters and digits.
The maximum length of the extension is 3. 

Input Format

The first line of input is the integer N, the number of email addresses. 
N lines follow, each containing a string.

Constraints

Each line is a non-empty string.

Output Format

Output a list containing the valid email addresses in lexicographical order. If the list is empty, just output an empty list, [].

```python
import re

email_regex = re.compile(r'^[a-z0-9_-]+@[a-z0-9]+\.[a-z]{1,3}$')
emails = [raw_input() for email in range(int(raw_input()))]
print sorted(filter(lambda email: re.match(email_regex, email), emails))
```
```
input:
2
ymn@ds.fd
gei@sf.jyh

output:

['gei@sf.jyh', 'ymn@ds.fd']
```
<https://www.hackerrank.com/challenges/validate-list-of-email-address-with-filter>

### Errors and Exceptions

* Exceptions

Errors detected during execution are called exceptions.

** ZeroDivisionError 
This error is raised when the second argument of a division or modulo operation is zero.

```
>>> a = '1'
>>> b = '0'
>>> print int(a) / int(b)
>>> ZeroDivisionError: integer division or modulo by zero
ValueError 
```
** This error is raised when a built-in operation or function receives an argument that has the right type but an inappropriate value.

```
>>> a = '1'
>>> b = '#'
>>> print int(a) / int(b)
>>> ValueError: invalid literal for int() with base 10: '#'
```

Handling Exceptions

The statements try and except can be used to handle selected exceptions. A try statement may have more than one except clause to specify handlers for different exceptions.

```python
try:
    print 1/0
except ZeroDivisionError as e:
    print "Error Code:",e
```
```
Output

Error Code: integer division or modulo by zero
```
* Example:

Task

You are given two values a and b. 
Perform integer division and print a/b.

Input Format

The first line contains T, the number of test cases. 
The next T lines each contain the space separated values of a and b.

Constraints

0<T<10

Output Format

Print the value of a/b. 
In the case of ZeroDivisionError or ValueError, print the error code.

```python
n = int(raw_input())
for _ in range(0, n):
    try:
        a, b = map(int,raw_input().strip().split(' '))
        print(a/b)
    except (ZeroDivisionError, ValueError) as e:
        print("Error Code:",e)
```
```
input:
2
4 2
output:
2
input:
5 0
output:
('Error Code:', ZeroDivisionError('integer division or modulo by zero',))
```
<https://www.hackerrank.com/challenges/exceptions>
    