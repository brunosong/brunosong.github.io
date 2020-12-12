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
        
        Arrays.sort(A);

        for(int i = 1; i <= A.length; i++ ){
            if(A[i - 1] != i){
                return i;
            }            
        }

        return A.length + 1;
    }
}

```

## 결과

1. PermMissingElem
Find the missing element in a given permutation.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

포인트는 정확하게 맞아 떨어졌을때 (1,2,3,4) 이렇게 올때 마지막을 총 길이에 +1을 해주는것이다.



