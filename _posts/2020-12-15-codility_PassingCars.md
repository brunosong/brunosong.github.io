---
layout: post
title:  "코딜리티 PassingCars"
date:   2020-12-15 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A non-empty array A consisting of N integers is given. The consecutive elements of array A represent consecutive cars on a road.  
  
Array A contains only 0s and/or 1s:  
  
0 represents a car traveling east,  
1 represents a car traveling west.  
The goal is to count passing cars. We say that a pair of cars (P, Q), where 0 ≤ P < Q < N, is passing when P is traveling to the east and Q is traveling to the west.  
  
For example, consider array A such that:  
  
  A[0] = 0  
  A[1] = 1  
  A[2] = 0  
  A[3] = 1  
  A[4] = 1  
We have five pairs of passing cars: (0, 1), (0, 3), (0, 4), (2, 3), (2, 4).  
  
Write a function:  
  
class Solution { public int solution(int[] A); }  
  
that, given a non-empty array A of N integers, returns the number of pairs of passing cars.  
  
The function should return −1 if the number of pairs of passing cars exceeds 1,000,000,000.  
  
For example, given:  
  
  A[0] = 0  
  A[1] = 1  
  A[2] = 0  
  A[3] = 1  
  A[4] = 1  
the function should return 5, as explained above.  
  

<br/>

># 입출력 예



># 문제 풀이

```
class Solution {
    public int solution(int[] A) {

        int cnt = 0;

        int totalOne = 0;

        for(int a : A){
            totalOne += a;
        }

        for(int i = 0; i < A.length ; i++){

            if(A[i] == 0){
                cnt += totalOne;
                if(cnt > 1000000000){
                    return -1;
                }
            }else{
                totalOne--;
            }

        }

        return cnt;


    }
}

```

## 결과

1. PassingCars
Count the number of passing cars on the road.
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

그냥 포문으로 돌리면 큰일난다... 이중포문... 



