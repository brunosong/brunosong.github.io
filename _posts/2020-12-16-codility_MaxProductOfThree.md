---
layout: post
title:  "코딜리티 MaxProductOfThree"
date:   2020-12-16 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A non-empty array A consisting of N integers is given. The product of triplet (P, Q, R) equates to A[P] * A[Q] * A[R] (0 ≤ P < Q < R < N).  
  
For example, array A such that:  
  
  A[0] = -3  
  A[1] = 1  
  A[2] = 2  
  A[3] = -2  
  A[4] = 5  
  A[5] = 6  
contains the following example triplets:  
  
(0, 1, 2), product is −3 * 1 * 2 = −6  
(1, 2, 4), product is 1 * 2 * 5 = 10  
(2, 4, 5), product is 2 * 5 * 6 = 60  
Your goal is to find the maximal product of any triplet.  
  
Write a function:  
  
class Solution { public int solution(int[] A); }  
  
that, given a non-empty array A, returns the value of the maximal product of any triplet.  
  
For example, given array A such that:  
  
  A[0] = -3  
  A[1] = 1  
  A[2] = 2  
  A[3] = -2  
  A[4] = 5  
  A[5] = 6  
the function should return 60, as the product of triplet (2, 4, 5) is maximal.  
  
Write an efficient algorithm for the following assumptions:  

<br/>

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int[] A) {
        Arrays.sort(A);

        int max = A[A.length - 1] * A[A.length - 2] * A[A.length - 3];
        
        if(A[0] < 0 && A[1] < 0 && A[A.length - 1] > 0){
            
            int max2 = A[0] * A[1] * A[A.length - 1];
            
            if(max < max2) max = max2;
            
        }
        
        return max;
    }
}

```

## 결과

1. MaxProductOfThree
Maximize A[P] * A[Q] * A[R] for any triplet (P, Q, R).
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

첨에 생각을 했을때 정렬을 해서 왼쪽에 3개랑 오른쪽 3개랑 곱하면 가장 큰값이 나올꺼라고 생각했는데 그게 아니고
첫번째 두번째 값이 -이면 마지막값과 곱해주면 큰값이 나온다. 그래서 오른쪽 3개랑 첫번째 두번째가 마이너스일때 가장 큰수를 곱해주면
원하는 값이 나오게 된다.



