---
title: HackerRank Solution - Birthday Chocolate
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="BirthdayChocolate">My Solution to <a href="https://www.hackerrank.com/challenges/the-birthday-bar/problem">Birthday Chocolate</a></h4>


<strong><i>"Lily has a chocolate bar that she wants to share it with Ron for his birthday. Each of the squares has an integer on it. She decides to share a contiguous segment of the bar selected such that the length of the segment matches Ron's birth month and the sum of the integers on the squares is equal to his birth day. You must determine how many ways she can divide the chocolate."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/the-birthday-bar/problem)


<br>

```
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the birthday function below.
def birthday(s, d, m):
    
    cnt = 0 

    if type(s) == int: 
        if d == s: 
            cnt = 1
    else: 
        for i in range(0,len(s)-1):
            total = sum(s[i:(i+m)])
            if total == d: 
                cnt+=1
    return cnt
    
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input().strip())

    s = list(map(int, input().rstrip().split()))

    dm = input().rstrip().split()

    d = int(dm[0])

    m = int(dm[1])

    result = birthday(s, d, m)

    fptr.write(str(result) + '\n')

    fptr.close()

```


<br>
<br>

