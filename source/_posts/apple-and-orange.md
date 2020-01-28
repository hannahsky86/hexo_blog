---
title: HackerRank Solution - Apple and Orange
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="MigratoryBirds">My Solution to <a href="https://www.hackerrank.com/challenges/apple-and-orange/problem">Apple and Orange</a></h4>


<strong><i>"Sam's house has an apple tree and an orange tree that yield an abundance of fruit. In the diagram below, the red region denotes his house, where s is the start point, and t is the endpoint. The apple tree is to the left of his house, and the orange tree is to its right. You can assume the trees are located on a single point, where the apple tree is at point a, and the orange tree is at point b."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/apple-and-orange/problem)


<br>

```
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the countApplesAndOranges function below.
def countApplesAndOranges(s, t, a, b, apples, oranges):

        cnt_apples = 0
        cnt_oranges = 0
        for apple in apples: 

            if a+apple >= s and a+apple <= t: 
                cnt_apples +=1
        
        for orange in oranges: 

            if b+orange >= s and b+orange <= t: 
                cnt_oranges +=1
        
        print(cnt_apples)
        print(cnt_oranges)

if __name__ == '__main__':
    st = input().split()

    s = int(st[0])

    t = int(st[1])

    ab = input().split()

    a = int(ab[0])

    b = int(ab[1])

    mn = input().split()

    m = int(mn[0])

    n = int(mn[1])

    apples = list(map(int, input().rstrip().split()))

    oranges = list(map(int, input().rstrip().split()))
    
    countApplesAndOranges(s, t, a, b, apples, oranges)

```


<br>
<br>

