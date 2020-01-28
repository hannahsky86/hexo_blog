---
title: HackerRank Solution - Kangaroo
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="Kangaroo">My Solution to <a href="https://www.hackerrank.com/challenges/kangaroo/problem">Kangaroo</a></h4>


<strong><i>"You are choreographing a circus show with various animals. For one act, you are given two kangaroos on a number line ready to jump in the positive direction (i.e, toward positive infinity). The first kangaroo starts at location x1 and moves at a rate of v1 meters per jump.
The second kangaroo starts at location x2 and moves at a rate of v2 meters per jump.
You have to figure out a way to get both kangaroos at the same location at the same time as part of the show. If it is possible, return YES, otherwise return NO."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/kangaroo/problem)


<br>

```
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the kangaroo function below.
def kangaroo(x1, v1, x2, v2):
    if 0<=x1<=x2<10000 and 1<=v1<10000 and 1<=v2<10000:

        if v1==v2:
            return "NO"

        if  (x1 - x2) % (v2 - v1) == 0 and v1>v2 :
            return "YES"
        else: 
            return "NO"

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    x1V1X2V2 = input().split()

    x1 = int(x1V1X2V2[0])

    v1 = int(x1V1X2V2[1])

    x2 = int(x1V1X2V2[2])

    v2 = int(x1V1X2V2[3])

    result = kangaroo(x1, v1, x2, v2)

    fptr.write(result + '\n')

    fptr.close()

```


<br>
<br>

