---
layout: post
title:  "코딜리티 Distinct"
date:   2020-12-16 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

that, given an array A consisting of N integers, returns the number of distinct values in array A.  
  
For example, given array A consisting of six elements such that:  
  
A[0] = 2    A[1] = 1    A[2] = 1  
A[3] = 2    A[4] = 3    A[5] = 1  
  
the function should return 3, because there are 3 distinct values appearing in array A, namely 1, 2 and 3.  
<br/>

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int[] A) {
        Set<Integer> set = new HashSet<>();
        
        for(int a : A){
            set.add(a);
        }
        return set.size();
    }
}

```

## 결과

1. Distinct
Compute number of distinct values in an array.
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

여태까지 해왔으니 이정도는 쉽게 풀수 있다.



