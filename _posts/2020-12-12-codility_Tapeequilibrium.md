---
layout: post
title:  "코딜리티 PermMissingElem"
date:   2020-12-12 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A non-empty array A consisting of N integers is given. Array A represents numbers on a tape.  

Any integer P, such that 0 < P < N, splits this tape into two non-empty parts: A[0], A[1], ..., A[P − 1] and A[P], A[P + 1], ..., A[N − 1].  

The difference between the two parts is the value of: |(A[0] + A[1] + ... + A[P − 1]) − (A[P] + A[P + 1] + ... + A[N − 1])|  

In other words, it is the absolute difference between the sum of the first part and the sum of the second part.  

For example, consider array A such that:  
  
  A[0] = 3  
  A[1] = 1  
  A[2] = 2  
  A[3] = 4  
  A[4] = 3  
We can split this tape in four places:  
  
P = 1, difference = |3 − 10| = 7  
P = 2, difference = |4 − 9| = 5  
P = 3, difference = |6 − 7| = 1  
P = 4, difference = |10 − 3| = 7  
Write a function:  
  
class Solution { public int solution(int[] A); }  
  
that, given a non-empty array A of N integers, returns the minimal difference that can be achieved.  
  
For example, given:  
  
  A[0] = 3  
  A[1] = 1  
  A[2] = 2  
  A[3] = 4  
  A[4] = 3  
the function should return 1, as explained above.  
  
Write an efficient algorithm for the following assumptions:  
      
<br/>

># 입출력 예



># 문제 풀이

```
class Solution {
    public int solution(int[] A) {
         int left = 0;
        int right = 0;

        int totalSum = 0;

        for(int num : A){
            totalSum += num;
        }

        int min = Integer.MAX_VALUE;

        for(int i = 1 ; i < A.length; i++){
            left += A[i-1];
            right = totalSum - left;

            int minus = Math.abs(left - right);

            if(minus < min){
                min = minus;
            }

        }

        return min;

    }
}

```

## 결과

1. TapeEquilibrium
Minimize the value |(A[0] + ... + A[P-1]) - (A[P] + ... + A[N-1])|.
Task Score
100%
Correctness
100%
Performance
100%1

## 정답해설

문제를 이해하면 참 쉽다.. 하지만 문제를 이해하기가 힘들고 for문이 마지맊까지 돌면 안된다는것을 명심하자



