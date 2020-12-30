---
layout: post
title:  "코딜리티 Brackets"
date:   2020-12-22 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
  
You are given two non-empty arrays A and B consisting of N integers. Arrays A and B represent N voracious fish in a river, ordered downstream along the flow of the river.

The fish are numbered from 0 to N − 1. If P and Q are two fish and P < Q, then fish P is initially upstream of fish Q. Initially, each fish has a unique position.

Fish number P is represented by A[P] and B[P]. Array A contains the sizes of the fish. All its elements are unique. Array B contains the directions of the fish. It contains only 0s and/or 1s, where:

0 represents a fish flowing upstream,
1 represents a fish flowing downstream.
If two fish move in opposite directions and there are no other (living) fish between them, they will eventually meet each other. Then only one fish can stay alive − the larger fish eats the smaller one. More precisely, we say that two fish P and Q meet each other when P < Q, B[P] = 1 and B[Q] = 0, and there are no living fish between them. After they meet:

If A[P] > A[Q] then P eats Q, and P will still be flowing downstream,
If A[Q] > A[P] then Q eats P, and Q will still be flowing upstream.
We assume that all the fish are flowing at the same speed. That is, fish moving in the same direction never meet. The goal is to calculate the number of fish that will stay alive.

For example, consider arrays A and B such that:

  A[0] = 4    B[0] = 0
  A[1] = 3    B[1] = 1
  A[2] = 2    B[2] = 0
  A[3] = 1    B[3] = 0
  A[4] = 5    B[4] = 0
Initially all the fish are alive and all except fish number 1 are moving upstream. Fish number 1 meets fish number 2 and eats it, then it meets fish number 3 and eats it too. Finally, it meets fish number 4 and is eaten by it. The remaining two fish, number 0 and 4, never meet and therefore stay alive.

Write a function:

class Solution { public int solution(int[] A, int[] B); }

that, given two non-empty arrays A and B consisting of N integers, returns the number of fish that will stay alive.

For example, given the arrays shown above, the function should return 2, as explained above.

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int[] A, int[] B) {
        Stack<Integer> down = new Stack<>();

        int cnt = 0;

        for(int i = 0 ; i < A.length ; i++){

            if(B[i] == 1){
                down.push(A[i]);
            }else{

                while (down.size() > 0){
                    if(down.peek() < A[i]){
                        down.pop();
                    }else{
                        break;
                    }
                }

                if(down.isEmpty()){
                    cnt++;
                }
            }
        }

        return cnt + down.size();
    }
}
```

## 결과

1. Fish
N voracious fish are moving along a river. Calculate how many fish are alive.
Task Score
100%
Correctness
100%
Performance


## 정답해설

문제 이해가 너무 힘들었다... 힌트만 살짝 보고 풀었다... 1이면 스텍에 담아야 한다는 힌트였다.  
저 문제로만 봤을때는 스텍에 while을 안돌려도 처리가 가능하지만 1이 여러개면 스택에 while을 꼭 돌려줘야 한다.


