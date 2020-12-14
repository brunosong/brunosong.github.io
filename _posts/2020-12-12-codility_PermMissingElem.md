---
layout: post
title:  "코딜리티 PermMissingElem"
date:   2020-12-12 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

An array A consisting of N different integers is given. The array contains integers in the range [1..(N + 1)], which means that exactly one element is missing.  
  
Your goal is to find that missing element.  
  
Write a function:  
  
class Solution { public int solution(int[] A); }  
  
that, given an array A, returns the value of the missing element.  
  
For example, given array A such that:  
  
  A[0] = 2  
  A[1] = 3  
  A[2] = 1  
  A[3] = 5  
the function should return 4, as it is the missing element.  
  
Write an efficient algorithm for the following assumptions:  
  
N is an integer within the range [0..100,000];  
the elements of A are all distinct;  
each element of array A is an integer within the range [1..(N + 1)].  
    
<br/>

># 입출력 예




># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int[] A) {
        
        Set<Integer> set = new HashSet<>();

        for(int num : A){
            if(set.contains(num)){
                set.remove(num);
            }else{
                set.add(num);
            }
        }

        return set.iterator().next();
    }
}
```

## 결과

1. OddOccurrencesInArray
Find value that occurs in odd number of elements.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

Set에 대한 사용법을 좀더 익혀야 할것 같다 .. 스택도 조금은 더 알아야 할것 같다




