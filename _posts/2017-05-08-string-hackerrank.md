---
layout: post
title: String from Hackerrank

tags: 
- Python Study
---
Study notes about string

### String
##### print string with locations
* Example

Task

You are given a partial code that is used for generating the HackerRank Logo of variable thickness. 
Your task is to replace the blank (______) with rjust, ljust or center.

Input Format

A single line containing the thickness value for the logo.

Constraints

The thickness must be an odd number. 
0< thickness <50

Output Format

Output the desired logo.

```python
thickness = int(raw_input()) #This must be an odd number
c = 'H'

for i in range(thickness):
    print (c*i).rjust(thickness-1)+c+(c*i).ljust(thickness-1)

for i in range(thickness+1):
    print (c*thickness).center(thickness*2)+(c*thickness).center(thickness*6)


for i in range((thickness+1)/2):
    print (c*thickness*5).center(thickness*6)    

for i in range(thickness+1):
    print (c*thickness).center(thickness*2)+(c*thickness).center(thickness*6)    

for i in range(thickness):
    print ((c*(thickness-i-1)).rjust(thickness)+c+(c*(thickness-i-1)).ljust(thickness)).rjust(thickness*6)   
    
``` 
```python 
input:
3

output:

  H  
 HHH 
HHHHH
 HHH         HHH        
 HHH         HHH        
 HHH         HHH        
 HHH         HHH        
 HHHHHHHHHHHHHHH  
 HHHHHHHHHHHHHHH  
 HHH         HHH        
 HHH         HHH        
 HHH         HHH        
 HHH         HHH        
            HHHHH 
             HHH  
              H   
```

<https://www.hackerrank.com/challenges/text-alignment>

* Example

Given an integer,n , print the following values for each integer i from 1 to n :

Decimal
Octal
Hexadecimal (capitalized)
Binary

The four values must be printed on a single line in the order specified above for each i from 1 to n. Each value should be space-padded to match the width of the binary value of n.

Input Format

A single integer denoting n .

Constraints
1 <= n <= 99

Output Format

Print n lines where each line i (in the range 1<=i<=n ) contains the respective decimal, octal, capitalized hexadecimal, and binary values of i. Each printed value must be formatted to the width of the binary value of n.

```python
def print_formatted(number):
   
    width = len('{:b}'.format(N))

    for i in range(1, N+1):
        print str.rjust(str(i), width),str.rjust('{:o}'.format(i), width),str.rjust('{:X}'.format(i), width),str.rjust('{:b}'.format(i), width)
print_formatted(int(raw_input()))
```
```python
input:
17
output:
  1   1   1   1
  2   2   2  10
  3   3   3  11
  4   4   4 100
  5   5   5 101
  6   6   6 110
  7   7   7 111
```
<https://www.hackerrank.com/challenges/python-string-formatting>

##### string.ascii_lowercase/  string.lowercase 
* Example:

You are given an integer, N. Your task is to print an alphabet rangoli of size N. (Rangoli is a form of Indian folk art based on creation of patterns.)

The center of the rangoli has the first alphabet letter a, and the boundary has the (N)th alphabet letter (in alphabetical order).

Input Format

Only one line of input containing N , the size of the rangoli.

Constraints
0<N<27

Output Format

Print the alphabet rangoli in the format explained above.

```python
import string
def print_rangoli(size):
    # your code goes here
    order = size - 1
    for i in range(order, 0, -1):
        row = ['-'] * (2 * size - 1)
       
        for j in range(size - i):
            row[order - j] = row[order + j] = string.ascii_lowercase[j + i]
           
        print '-'.join(row)

    for i in range(0, size):
        row = ['-'] * (2 * size - 1)
        for j in range(0, size - i):
            row[order - j] = row[order + j] = string.lowercase[j + i]
        print '-'.join(row)
    
s = int(raw_input()) 
print_rangoli(s)    
```

```python

input:
3

output:

----c----
--c-b-c--
c-b-a-b-c
--c-b-c--
----c----
```
<https://www.hackerrank.com/challenges/alphabet-rangoli>
                  
     
