---
layout: post
title:  "코딜리티 FrogRiverOne"
date:   2020-12-14 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A small frog wants to get to the other side of a river. The frog is initially located on one bank of the river (position 0) and wants to get to the opposite bank (position X+1). Leaves fall from a tree onto the surface of the river.

You are given an array A consisting of N integers representing the falling leaves. A[K] represents the position where one leaf falls at time K, measured in seconds.

The goal is to find the earliest time when the frog can jump to the other side of the river. The frog can cross only when leaves appear at every position across the river from 1 to X (that is, we want to find the earliest moment when all the positions from 1 to X are covered by leaves). You may assume that the speed of the current in the river is negligibly small, i.e. the leaves do not change their positions once they fall in the river.  

For example, you are given integer X = 5 and array A such that:  
  
  A[0] = 1  
  A[1] = 3  
  A[2] = 1  
  A[3] = 4  
  A[4] = 2  
  A[5] = 3  
  A[6] = 5  
  A[7] = 4  
In second 6, a leaf falls into position 5. This is the earliest time when leaves appear in every position across the river.  
  
Write a function:  
  
class Solution { public int solution(int X, int[] A); }  
  
that, given a non-empty array A consisting of N integers and integer X, returns the earliest time when the frog can jump to the other side of the river.  
  
If the frog is never able to jump to the other side of the river, the function should return −1.  
  
For example, given X = 5 and array A such that:  
  
  A[0] = 1  
  A[1] = 3  
  A[2] = 1  
  A[3] = 4  
  A[4] = 2  
  A[5] = 3  
  A[6] = 5  
  A[7] = 4  
the function should return 6, as explained above.  
  
Write an efficient algorithm for the following assumptions:  
  
N and X are integers within the range [1..100,000];  
each element of array A is an integer within the range [1..X].  
    
<br/>

># 입출력 예

># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int X, int[] A) {

        boolean[] b = new boolean[X];
        System.out.println(Arrays.toString(b));

        int cnt = 0;

        //인덱스를 리턴해라
        for(int i = 0 ; i < A.length ; i++){
            if(X >= A[i]){
                if(!b[A[i] - 1]){
                    cnt++;
                }
                b[A[i] - 1] = true;

                if(X == cnt){
                    return i;
                }
            }
        }

        return -1;
    }

    public int solution2(int X, int[] A) {

        Set<Integer> set = new HashSet<>();

        for(int i = 0 ; i < A.length ; i++){

            set.add(A[i]);

            if(X == set.size()){
                return i;
            }

        }

        return -1;
    }
}

```

## 결과

1. FrogRiverOne
Find the earliest time when a frog can jump to the other side of a river.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

문제를 이해하는데 어려웠다... set을 사용해서 분명히 풀릴것 같은 느낌이었는데 잘 안되서 일단 풀어보고 set으로 이용해서 풀어보았다.
셋에 들어가있는 최종카운트를 구하는게 포문을 한번 더 써야 하나 했지만 카운트값과 set에 들어가져 있는 가장 높은값과 같은것이었다... 생각좀 잘해보자



