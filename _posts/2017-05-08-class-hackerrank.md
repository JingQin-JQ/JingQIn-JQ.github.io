---
layout: post
title: Class from Hackerrank

tags: 
- Python Study
---
Study notes about class
### Class

Python classes provide all the standard features of Object Oriented Programming: the class inheritance mechanism allows multiple base classes, a derived class can override any methods of its base class or classes, and a method can call the method of a base class with the same name. Objects can contain arbitrary amounts and kinds of data.

Always start with a def "init"part.

####Example:
Classes: Dealing with Complex Numbers

For this challenge, you are given two complex numbers, and you have to print the result of their addition, subtraction, multiplication, division and modulus operations.

The real and imaginary precision part should be correct up to two decimal places.

Input Format

One line of input: The real and imaginary part of a number separated by a space.

Output Format

For two complex numbers  and , the output should be in the following sequence on separate lines:

* C+D
* C-D
* C*D
* C/D
* mod(C)
* mod(D)
 
For complex numbers with non-zero real (A)and complex part(B), the output should be in the following format: 
A+Bi
Replace the plus symbol (+) with a minus symbol  (-)when B<0.

For complex numbers with a zero complex part i.e. real numbers, the output should be: 
A+0.00i

For complex numbers where the real part is zero and the complex part(B) is non-zero, the output should be:
0.00+Bi

Sample Input

2 1
5 6
Sample Output

7.00+7.00i
-3.00-5.00i
4.00+17.00i
0.26-0.11i
2.24+0.00i
7.81+0.00i
Concept

Python is a fully object-oriented language like C++, Java, etc. For reading about classes, refer here. 

Methods with a double underscore before and after their name are considered as built-in methods. They are used by interpreters and are generally used in the implementation of overloaded operators or other built-in functionality. 

__add__-> Can be overloaded for + operation

__sub__ -> Can be overloaded for - operation

__mul__ -> Can be overloaded for * operation

#####Code:

``` python
import math

class Complex(object):
    def __init__(self, real, imaginary):
        self.real = real
        self.imaginary = imaginary

    def __add__(self, no):
        real = self.real + no.real
        imaginary = self.imaginary + no.imaginary
        return Complex(real, imaginary)

    def __sub__(self, no):
        real = self.real - no.real
        imaginary = self.imaginary - no.imaginary
        return Complex(real, imaginary)

    def __mul__(self, no):
        real = self.real * no.real - self.imaginary * no.imaginary
        imaginary = self.real * no.imaginary + self.imaginary * no.real
        return Complex(real, imaginary)

    def __div__(self, no):
        x = float(no.real ** 2 + no.imaginary ** 2)
        y = self * Complex(no.real, -no.imaginary)
        real = y.real / x
        imaginary = y.imaginary / x
        return Complex(real, imaginary)

    def mod(self):
        real = math.sqrt(self.real ** 2 + self.imaginary ** 2)
        return Complex(real, 0)

    def __str__(self):
        if self.imaginary == 0:
            result = "%.2f+0.00i" % (self.real)
            
        elif self.real == 0 and self.imaginary >= 0:
            result = "0.00+%.2fi" % (self.imaginary)
        elif self.real == 0 and self.imaginary < 0:
            result = "0.00%.2fi" % (self.imaginary)   
        elif self.imaginary > 0:
            result = "%.2f+%.2fi" % (self.real, self.imaginary)
            
        else:
            result = "%.2f-%.2fi" % (self.real, abs(self.imaginary))
        return result


C = map(float, raw_input().split())
D = map(float, raw_input().split())
x = Complex(C[0],C[1])
y = Complex(D[0],D[1])

print str(x+y)
print str(x-y)
print str(x*y)
print str(x/y)
print str(x.mod())
print str(y.mod())
```
##### results:

``` python
input:
42 -42
84 -84

output:
126.00-126.00i
-42.00+42.00i
0.00-7056.00i
0.50+0.00i
59.40+0.00i
118.79+0.00i
```
<https://www.hackerrank.com/challenges/class-1-dealing-with-complex-numbers>