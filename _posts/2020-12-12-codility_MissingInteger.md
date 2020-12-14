---
layout: post
title:  "코딜리티 MissingInteger"
date:   2020-12-14 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

that, given an array A of N integers, returns the smallest positive integer (greater than 0) that does not occur in A.

For example, given A = [1, 3, 6, 4, 1, 2], the function should return 5.

Given A = [1, 2, 3], the function should return 4.

Given A = [−1, −3], the function should return 1.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..100,000];
each element of array A is an integer within the range [−1,000,000..1,000,000].
    
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
        
        for(int i = 1; i <= 1000000 ; i++){
            
            if(!set.contains(i)){
                return i;
            }
        }

        return -1;

    }
}
```

## 결과

1. MissingInteger
Find the smallest positive integer that does not occur in a given sequence.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

Set의 사용법을 잘 알면 충분히 쉽게 풀수 있다. 이런문제는 어떻게 풀것인가가 중요한 문제이다


