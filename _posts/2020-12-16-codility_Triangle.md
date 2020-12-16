---
layout: post
title:  "코딜리티 Triangle"
date:   2020-12-16 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
  
An array A consisting of N integers is given. A triplet (P, Q, R) is triangular if 0 ≤ P < Q < R < N and:  
  
A[P] + A[Q] > A[R],  
A[Q] + A[R] > A[P],  
A[R] + A[P] > A[Q].  
For example, consider array A such that:  
  
  A[0] = 10    A[1] = 2    A[2] = 5  
  A[3] = 1     A[4] = 8    A[5] = 20  
Triplet (0, 2, 4) is triangular.  
  
Write a function:  
  
class Solution { public int solution(int[] A); }  
  
that, given an array A consisting of N integers, returns 1 if there exists a triangular triplet for this array and returns 0 otherwise.  
  
For example, given array A such that:  
  
  A[0] = 10    A[1] = 2    A[2] = 5  
  A[3] = 1     A[4] = 8    A[5] = 20  
the function should return 1, as explained above. Given array A such that:  
  
  A[0] = 10    A[1] = 50    A[2] = 5  
  A[3] = 1  
the function should return 0.  
  
Write an efficient algorithm for the following assumptions:  

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int[] A) {
        if(A.length < 3){
            return 0;
        }

        Arrays.sort(A);

        for(int i = 0 ; i < A.length - 2; i++){

            long P = A[i];
            long Q = A[i + 1];
            long R = A[i + 2];

            if(P + Q > R){
                return 1;
            }
        }

        return 0;
    }
}

```

## 결과

1. Triangle
Determine whether a triangle can be built from a given set of edges.
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

이게 쉬운문제에 속하는 편이라니.... 생각을 많이 해서 풀어야 한다. 정렬을 하고 문제를 푸는 방법을 알아내는게 중요한 문제  
정렬을 하면 A[Q] + A[R] > A[P],  A[R] + A[P] > A[Q] 는 기본적으로 만족을 하게 된다. 
그래서 A[P] + A[Q] > A[R] 이 조건식만 처리를 하면 쉽게 처리가 된다.




