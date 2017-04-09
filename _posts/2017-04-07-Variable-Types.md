---
layout: post
title: Variable Types
tags: 
- Python Study
---
Study notes about Python Variable Types and  What can be done on the variable.

### Built-in Data types

- Boolean: the type of the built-in values True and False. 
  * Boolean Operations — and, or, not
- #### Numeric types:

  * int: Integers
  * long: Long integers of non-limited lengthfloat: 
  * float
  
  
##### operations

|Operation	|Meaning	|
--- | --- | 
x + y|	sum of x and y	
x - y	|difference of x and y	 
x * y	|product of x and y	 
x / y	|quotient of x and y	
x // y	|(floored) quotient of x and y	
x % y	|remainder of x / y	(4)
-x	|x negated	 
+x	|x unchanged	 
abs(x)	|absolute value or magnitude of x	
int(x)	|x converted to integer	
long(x)	|x converted to long integer	
float(x)	|x converted to floating point	
x ** y	|x to the power y	


  
#### Sequences:

  * str: String
  * list
  * tuple

##### operations

|Operation	|Result|
--- | --- | 
x in s	|True if an item of s is equal to x, else False	
x not in s	|False if an item of s is equal to x, else True	(1)
s + t	|the concatenation of s and t	(6)
s * n, n * s	|equivalent to adding s to itself n times	
s[i]	| item of s, origin 0	(3)
s[i:j]	|slice of s from i to j	(3)(4)
s[i:j:k]	|slice of s from i to j with step k	(3)(5)
len(s)|	length of s	 
min(s)|	smallest item of s	 
max(s)	|largest item of s	 
s.index(x)	|index of the first occurrence of x in s	 
s.count(x)	|total number of occurrences of x in s

#### Sets:

  * set: an unordered collection of unique objects; 
  * frozen set: like set, but immutable (Only mutable objects support methods that change the object in place); 
  
  
##### Instances of Set and ImmutableSet both provide the following operations:
     
|Operation	|Equivalent	|Result
--- | --- | --- |
len(s)	| 	|number of elements in set s (cardinality)
x in s	|	|test x for membership in s
x not in s|	| 	test x for non-membership in s
s.issubset(t)	|s <= t|	test whether every element in s is in t
s.issuperset(t)	|s >= t|	test whether every element in t is in s
s.union(t)	| s l t | new set with elements from both s and t
s.intersection(t)	|s & t|	new set with elements common to s and t
s.difference(t)	|s - t	|new set with elements in s but not in t
s.symmetric_difference(t)	|s ^ t|	new set with elements in either s or t but not both
s.copy()	 	| | new set with a shallow copy of s
   
   
##### The following table lists operations available in Set but not found in ImmutableSet:
   
   
|Operation	|Equivalent	|Result
--- | --- | --- |
s.update(t)	|s l= t|	return set s with elements added from t
s.intersection_update(t)	|s &= t|	return set s keeping only elements also found in t
s.difference_update(t)	|s -= t|	return set s after removing elements found in t
s.symmetric_difference_update(t)	|s ^= t|	return set s with elements from s or t but not both
s.add(x)	 | |	add element x to set s
s.remove(x)	| | 	remove x from set s; raises KeyError if not present
s.discard(x)	| | 	removes x from set s if present
s.pop()	| | 	remove and return an arbitrary element from s; raises KeyError if empty
s.clear()	 | |	remove all elements from set s
  
#### Mappings: 
   * dict: Python dictionaries,which means that an element of the list is associated with a definition, 

##### operations
|Operation	|Result|
--- | --- |
len(d)| Return the number of items in the dictionary d.
d[key]|Return the item of d with key key. Raises a KeyError if key is not in the map.  
d[key] = value| Set d[key] to value.
del d[key]|Remove d[key] from d. Raises a KeyError if key is not in the map.
key in d|Return True if d has a key key, else False.
key not in d|Equivalent to not key in d.
iter(d)|Return an iterator over the keys of the dictionary. This is a shortcut for iterkeys().
clear()|Remove all items from the dictionary.
copy()|Return a shallow copy of the dictionary.
fromkeys(seq[, value])|Create a new dictionary with keys from seq and values set to value.
get(key[, default])|Return the value for key if key is in the dictionary, else default. If default is not given, it defaults to None, so that this method never raises a KeyError.
has_key(key)|Test for the presence of key in the dictionary. has_key() is deprecated in favor of key in d.
items()|Return a copy of the dictionary’s list of (key, value) pairs.
iteritems()|Return an iterator over the dictionary’s (key, value) pairs. See the note for dict.items().
iterkeys()|Return an iterator over the dictionary’s keys. See the note for dict.items().
itervalues()|Return an iterator over the dictionary’s values. See the note for dict.items().
keys()|Return a copy of the dictionary’s list of keys. See the note for dict.items().
pop(key[, default])|If key is in the dictionary, remove it and return its value, else return default. If default is not given and key is not in the dictionary, a KeyError is raised.
popitem()|Remove and return an arbitrary (key, value) pair from the dictionary.
setdefault(key[, default])|If key is in the dictionary, return its value. If not, insert key with a value of default and return default. default defaults to None.
update([other])|Update the dictionary with the key/value pairs from other, overwriting existing keys. Return None.
values()|Return a copy of the dictionary’s list of values. See the note for dict.items().
viewitems()|Return a new view of the dictionary’s items ((key, value) pairs). See below for documentation of view objects.
viewkeys()|Return a new view of the dictionary’s keys. See below for documentation of view objects.
viewvalues()|Return a new view of the dictionary’s values. See below for documentation of view objects.

 

### Comparison operations are supported by all objects.

|Operation	|Meaning	|
--- | --- | 
<	|strictly less than	 
<=	|less than or equal	 
>	|strictly greater than	 
>=	|greater than or equal	 
==	|equal	 
!=	|not equal	
is	|object identity	 
is not	|negated object identity	  
  
   
   