---
title: HackerRank - Between Two Sets 
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>
 

<h4>My <a href="https://www.hackerrank.com/challenges/between-two-sets/problem">HackerRank</a> solution to:</h4>

<ul>
<li> <a href = "#BetweenTwoSets">Between Two Sets</a></li>
<li> <a href = "#BreakingTheRecords">Breaking the Records</a></li>
</ul>

<br>
<br>

<h4><a id="BetweenTwoSets">My Solution to <a href="https://www.hackerrank.com/challenges/between-two-sets/problem">Between Two Sets</a></h4>


<strong>Note:</strong> This code ([Python](https://www.python.org/)) passed all of the tests, but I'm pretty sure there are better ways to solve this problem. Feel free to comment and offer suggestions. Also, the HackerRank didn't allow me to import [numpy](https://numpy.org/).


<strong><i>"You will be given two arrays of integers and asked to determine all integers that satisfy the following two conditions:

The elements of the first array are all factors of the integer being considered 

The integer being considered is a factor of all elements of the second array

These numbers are referred to as being between the two arrays. You must determine how many such numbers exist."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/between-two-sets/problem)


<br>

<strong>First Solution</strong>

```

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

```

<br>

<strong> Second Solution </strong>
```
def getTotalX(a_array, b_array):

    max_a=a_array if type(a_array)==int else max(a_array)
    min_b=b_array if type(b_array)==int else max(b_array)

    items = [] 
    x=1
    while max_a*x<=min_b: 

        if type(a_array)==int:
            items.append(max_a*x) if (max_a*x)%a_array == 0 else 0  
        else:
            items.append(max_a*x) if sum([(max_a*x)%a for a in a_array]) == 0 else 0
        x+=1
        
    total = 0 
    for i in items: 
        total+=1 if sum([b%i for b in b_array]) == 0 else 0
    return total

```

<br>
<br>

<h4><a id="BreakingTheRecords">My Solution to <a href="https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem">Breaking the Records</a></h4>


<strong><i>"Maria plays college basketball and wants to go pro. Each season she maintains a record of her play. She tabulates the number of times she breaks her season record for most points and least points in a game. Points scored in the first game establish her record for the season, and she begins counting from there."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem)


<br>

```
def breakingRecords(scores):

    min_score = scores[0]
    max_score = scores[0]

    cnt_min = 0
    cnt_max = 0 

    for i in range(1, len(scores)):
        if scores[i]>max_score:
            max_score = scores[i]
            cnt_max+=1
        if scores[i]<min_score:
            min_score = scores[i]
            cnt_min+=1
            
    return cnt_max, cnt_min
```


<br>
<br>

