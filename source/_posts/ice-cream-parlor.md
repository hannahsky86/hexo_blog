---
title: HackerRank Solution - Ice Cream Parlor
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="IceCreamParlor">My Solution to <a href="https://www.hackerrank.com/challenges/icecream-parlor/problem">Ice Cream Parlor</a></h4>


<strong><i>"Sunny and Johnny like to pool their money and go to the ice cream parlor. Johnny never buys the same flavor that Sunny does. The only other rule they have is that they spend all of their money.

Given a list of prices for the flavors of ice cream, select the two that will cost all of the money they have.

For example, they have  to spend and there are flavors costing . The two flavors costing  and  meet the criteria. Using -based indexing, they are at indices  and ."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/icecream-parlor/problem)


<br>

```
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the icecreamParlor function below.
def icecreamParlor(m, arr):

    for i in range(0,len(arr)): 
        for j in range(i,len(arr)): 
            if arr[i]+arr[j] == m and i!=j:
                return (i+1,j+1)


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    t = int(input())

    for t_itr in range(t):
        m = int(input())

        n = int(input())

        arr = list(map(int, input().rstrip().split()))

        result = icecreamParlor(m, arr)

        fptr.write(' '.join(map(str, result)))
        fptr.write('\n')

    fptr.close()

```


<br>
<br>

