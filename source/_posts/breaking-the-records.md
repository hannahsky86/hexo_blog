---
title: HackerRank Solution - Breaking the Records
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

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

