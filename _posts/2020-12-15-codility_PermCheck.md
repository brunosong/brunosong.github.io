---
layout: post
title:  "코딜리티 PermCheck"
date:   2020-12-15 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A non-empty array A consisting of N integers is given.

A permutation is a sequence containing each element from 1 to N once, and only once.

For example, array A such that:

    A[0] = 4
    A[1] = 1
    A[2] = 3
    A[3] = 2
is a permutation, but array A such that:

    A[0] = 4
    A[1] = 1
    A[2] = 3
is not a permutation, because value 2 is missing.

The goal is to check whether array A is a permutation.

Write a function:

class Solution { public int solution(int[] A); }

that, given an array A, returns 1 if array A is a permutation and 0 if it is not.

For example, given array A such that:

    A[0] = 4
    A[1] = 1
    A[2] = 3
    A[3] = 2
the function should return 1.

Given array A such that:

    A[0] = 4
    A[1] = 1
    A[2] = 3
the function should return 0.

Write an efficient algorithm for the following assumptions:
      
<br/>

># 입출력 예



># 문제 풀이

```
class Solution {
    public int solution(int[] A) {
        
        Arrays.sort(A);
        int cnt = 1;

        for(int i = 0 ; i < A.length; i++ ){
            if(A[i] != cnt){
                return 0;
            }
            cnt++;
        }

        return 1;



    }
}

```

## 결과

1. PermCheck
Check whether array A is a permutation.
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

음... 지금이야 쉽다고 느꼈지만 첨에는 이게 왜이렇게 어려웠을까... 음... 



