---
title: HackerRank Solution - Time Conversion
date: 2020-01-18 10:38:43
tags:
- HackerRank
---

<br>
<br>


<h4><a id="TimeConversion">My Solution to <a href="https://www.hackerrank.com/challenges/time-conversion/problem">Time Conversion</a></h4>


<strong><i>"Given a time in 12-hour AM/PM format, convert it to military (24-hour) time.

Note: Midnight is 12:00:00AM on a 12-hour clock, and 00:00:00 on a 24-hour clock. Noon is 12:00:00PM on a 12-hour clock, and 12:00:00 on a 24-hour clock."</i></strong>

[Continue reading...](https://www.hackerrank.com/challenges/time-conversion/problem)


<br>

```
#!/bin/python3

import os
import sys

#
# Complete the timeConversion function below.
#
def timeConversion(s):
    hh = s[0:2]
    mm = s[3:5]
    ss = s[6:8]
    M  = s[8:10]
    
    if M == "PM" and int(hh)<12:
        hh = str(int(hh) + 12)
        
    if M == "AM" and int(hh)==12 and (int(mm)>=0 or int(ss)>=0):
        hh = "00"
        
    final_time = hh + ":" + mm + ":" + ss 
    return final_time 

if __name__ == '__main__':
    f = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = timeConversion(s)

    f.write(result + '\n')

    f.close()



```


<br>
<br>

