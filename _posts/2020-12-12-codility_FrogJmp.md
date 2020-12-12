---
layout: post
title:  "코딜리티 FrogJmp"
date:   2020-12-12 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A small frog wants to get to the other side of the road. The frog is currently located at position X and wants to get to a position greater than or equal to Y. The small frog always jumps a fixed distance, D.  

Count the minimal number of jumps that the small frog must perform to reach its target.  
  
Write a function:  
  
class Solution { public int solution(int X, int Y, int D); }  
  
that, given three integers X, Y and D, returns the minimal number of jumps from position X to a position equal to or greater than Y.  
  
For example, given:  
  
  X = 10  
  Y = 85  
  D = 30  
the function should return 3, because the frog will be positioned as follows:  
  
after the first jump, at position 10 + 30 = 40  
after the second jump, at position 10 + 30 + 30 = 70  
after the third jump, at position 10 + 30 + 30 + 30 = 100  
Write an efficient algorithm for the following assumptions:  
  
X, Y and D are integers within the range [1..1,000,000,000];  
X ≤ Y.  
    
<br/>

># 입출력 예



># 문제 풀이

```
class Solution {
    public int solution(int X, int Y, int D) {
        
        int range = Y - X;

        if(range % D == 0){
            return range / D;
        }else{
            return range / D + 1;
        }
    }
}
```

## 결과

1. FrogJmp
Count minimal number of jumps from position X to Y.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

나머지에 대해서 조금만 생각을 해보아도 풀수 있는 문제다.



