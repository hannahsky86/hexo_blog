---
title: HackerRank Solution - Divisible Sum Pairs
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="DivisibleSumPairs">My Solution to <a href="https://www.hackerrank.com/challenges/divisible-sum-pairs/problem">Divisible Sum Pairs</a></h4>


<strong><i>"You are given an array of n integers ar = [ar[0], ar[1],...,ar[n-1]], and a positive integer, k. Find and print the number of (i,j) pairs where i < j and ar[i] + ar[j] is divisible by k." </strong>

[Continue reading...](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem)


<br>

```
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the divisibleSumPairs function below.
def divisibleSumPairs(n, k, ar):
    
    cnt = 0
    for i in range(0,n):
        for j in range(i,n):
            if (ar[i]+ar[j])%k == 0 and i<j:
                cnt+=1
    
    return cnt




if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    nk = input().split()

    n = int(nk[0])

    k = int(nk[1])

    ar = list(map(int, input().rstrip().split()))

    result = divisibleSumPairs(n, k, ar)

    fptr.write(str(result) + '\n')

    fptr.close()


```


<br>
<br>

