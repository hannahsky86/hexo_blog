---
title: HackerRank - Between Two Sets 
tags:
- HackerRank
---

<br>
<br>
 
<h4><a id="HackerRank">Code Practice with 
<a href="https://www.hackerrank.com/dashboard">HackerRank</a></h4>


My solution to <strong>[Between Two Sets](https://www.hackerrank.com/challenges/between-two-sets/problem)</strong>

Note: This code ([Python](https://www.python.org/)) passed all of the tests, but I'm pretty sure there are better ways to solve this problem. Feel free to comment and offer suggestions. Also, the HackerRank didn't allow me to import [numpy](https://numpy.org/).

<blockquote cite="https://www.hackerrank.com/challenges/between-two-sets/problem">
<p>You will be given two arrays of integers and asked to determine all integers that satisfy the following two conditions:

The elements of the first array are all factors of the integer being considered
The integer being considered is a factor of all elements of the second array
These numbers are referred to as being between the two arrays. You must determine how many such numbers exist.
[...](https://www.hackerrank.com/challenges/between-two-sets/problem)</p>
</blockquote>

"You will be given two arrays of integers and asked to determine all integers that satisfy the following two conditions:

The elements of the first array are all factors of the integer being considered
The integer being considered is a factor of all elements of the second array
These numbers are referred to as being between the two arrays. You must determine how many such numbers exist."
[...](https://www.hackerrank.com/challenges/between-two-sets/problem)

<br>

```
import math
import os
import random
import re
import sys

#
# Complete the 'getTotalX' function below.
#
# The function is expected to return an INTEGER.
# The function accepts following parameters:
#  1. INTEGER_ARRAY a
#  2. INTEGER_ARRAY b
#

def getTotalX(a_array, b_array):

    max_a=max(a_array)
    if type(a_array)==int: 
        max_a=a_array
     
    min_b=min(b_array)
    
    items = [] 
    x=1
    while max_a*x<=min_b: 
        
        if type(a_array)==int:
            if (max_a*x)%a_array==0:
                items.append(max_a*x)
        else:
            cnt = 0
            for a in a_array: 
                if (max_a*x)%a==0:
                    cnt+=1
                if cnt==len(a_array):
                    items.append(max_a*x)
                    break
        x+=1
    total = 0 
    for i in items: 
        cnt = 0 
        for b in b_array: 
            if b%i == 0:
                cnt+=1
            if cnt==len(b_array):
                total+=1
                break

    return total

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    first_multiple_input = input().rstrip().split()

    n = int(first_multiple_input[0])

    m = int(first_multiple_input[1])

    arr = list(map(int, input().rstrip().split()))

    brr = list(map(int, input().rstrip().split()))

    total = getTotalX(arr, brr)

    fptr.write(str(total) + '\n')

    fptr.close()

```
 
<br>
<br>