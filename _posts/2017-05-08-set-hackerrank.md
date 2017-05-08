---
layout: post
title: Set from Hackerrank

tags: 
- Python Study
---
Study notes about set

### Set
Unordered collections of unique elements.

###  Built a set
``` python
s = set(array)
```
```python
heights = map(int, raw_input().split())
heights = set(heights)
```
### Operations in set
##### Difference
l1=(set1.difference(set2)) *is diffrent than*   l2=(set2.difference(set1)) 

 * Example:
 
Task 
Given  sets of integers, M and N, print their symmetric difference in ascending order. The term symmetric difference indicates those values that exist in either M or N but do not exist in both.

Input Format

The first line of input contains an integer,M . 
The second line contains M space-separated integers. 
The third line contains an integer,N . 
The fourth line contains N space-separated integers.

Output Format

Output the symmetric difference integers in ascending order, one per line.

``` python
M=int(raw_input())
list1=map(int,raw_input().strip().split(" "))
N=int(raw_input())
list2=map(int,raw_input().strip().split(" "))
set1=set(list1)
set2=set(list2)
l1=(set1.difference(set2))
l2=(set2.difference(set1))
l3=sorted(l1.union(l2))
for i in l3:
    print i    
```

```
input:
4
2 4 5 9
4
2 4 11 12
output:
5
9
11
12
```
<https://www.hackerrank.com/challenges/symmetric-difference>

##### pop remove discard
 * Example:

 Task
You have a non-empty set s, and you have to execute N commands given in N lines.

The commands will be pop, remove and discard.

Input Format

The first line contains integer n, the number of elements in the set s. 
The second line contains n space separated elements of set s . All of the elements are non-negative integers, less than or equal to 9. 
The third line contains integer N , the number of commands.
The next N lines contains either pop, remove and/or discard commands followed by their associated value.

Constraints

0<n<20

0<N<20
 
Output Format

Print the sum of the elements of set  on a single line.

``` python
def perform(s, cmd):
    if cmd[0] == 'pop':
        s.pop()
    elif cmd[0] == 'remove':
        s.remove(int(cmd[1]))
    elif cmd[0] == 'discard':
        s.discard(int(cmd[1]))
   
    return s

n = input()
s = set(map(int, raw_input().split())) 
m = input()
for __ in range(m):
        cmd = raw_input().split()
        perform(s, cmd)

print sum(s)


def perform(s, cmd):
    if cmd[0] == 'pop':
        s.pop()
    elif cmd[0] == 'remove':
        s.remove(int(cmd[1]))
    elif cmd[0] == 'discard':
        s.discard(int(cmd[1]))
   
    return s
```
``` 
input:
9
1 2 3 4 5 6 7 8 9 
3
pop
remove 8
discard 8

output:
set([2, 3, 4, 5, 6, 7, 9])
```    
<https://www.hackerrank.com/challenges/py-set-discard-remove-pop>

##### intersection_update, difference_update and symmetric_difference_update

s.intersection_update(t)	       s &= t	
return set s keeping only elements also found in t

s.difference_update(t)           	s -= t
return set s after removing elements found in t

s.symmetric_difference_update(t) 	s ^= t
return set s with elements from s or t but not both

* Example
TASK
You are given a set A and N number of other sets. These N number of sets have to perform some specific mutation operations on set A .

Your task is to execute those operations and print the sum of elements from set A .

Input Format

The first line contains the number of elements in set A .
The second line contains the space separated list of elements in set A.
The third line contains N integer , the number of other sets.
The next 2*N lines are divided into N parts containing two lines each.
The first line of each part contains the space separated entries of the operation name and the length of the other set.
The second line of each part contains space separated list of elements in the other set.

0<len(set(A)) <1000 

0<len(otherSets) <100 

0<N<100
 
Output Format

Output the sum of elements in set .

``` python
length = int(raw_input())
A = set(map(int, raw_input().split()))
N = int(raw_input())

for i in range(N):
    (operation_name, other_set_length) = raw_input().split()
    other_set = set(map(int, raw_input().split()))

    if operation_name == 'intersection_update':
        A.intersection_update(other_set)
        print 'intersection_update',A
    elif operation_name == 'update':
        A.update(other_set)
        print 'update', A
    elif operation_name == 'symmetric_difference_update':
        A.symmetric_difference_update(other_set)
        print  'symmetric_difference_update', A
    elif operation_name == 'difference_update':
        A.difference_update(other_set)
        print 'difference_update', A
```
```
input:
2 
33 55
4
intersection_update 2
34 55

output:
intersection_update set([55])

input:
update 2
23 45

output:
update set([23, 45, 55])

input:
symmetric_difference_update 2
45 67

output:
symmetric_difference_update set([67, 23, 55])

input:
difference_update 2
23 78

output:
difference_update set([67, 55])
```
<https://www.hackerrank.com/challenges/py-set-mutations>

    
