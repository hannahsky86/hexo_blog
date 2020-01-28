---
title: HackerRank Solution - Migratory Birds
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="MigratoryBirds">My Solution to <a href="https://www.hackerrank.com/challenges/migratory-birds/problem">Migratory Birds</a></h4>


<strong><i>"You have been asked to help study the population of birds migrating across the continent. Each type of bird you are interested in will be identified by an integer value. Each time a particular kind of bird is spotted, its id number will be added to your array of sightings. You would like to be able to find out which type of bird is most common given a list of sightings. Your task is to print the type number of that bird and if two or more types of birds are equally common, choose the type with the smallest ID number."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/migratory-birds/problem)


<br>

```
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the migratoryBirds function below.
def migratoryBirds(arr):
    if len(arr)<200000:

        bird_dict = {} 
        for k in arr: 
            if (k in bird_dict): 
                bird_dict[k] += 1
            else: 
                bird_dict[k] = 1

        v_list = []
        for v in bird_dict.values(): 
            v_list.append(v)    
        max_val = max(v_list)

        max_keys = []
        for k,v in bird_dict.items(): 
            if v==max_val:
                max_keys.append(k)
        
        return min(max_keys)
        

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    arr_count = int(input().strip())

    arr = list(map(int, input().rstrip().split()))

    result = migratoryBirds(arr)

    fptr.write(str(result) + '\n')

    fptr.close()


```


<br>
<br>

