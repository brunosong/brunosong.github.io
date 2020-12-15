---
layout: post
title:  "코딜리티 CountDiv"
date:   2020-12-15 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

that, given three integers A, B and K, returns the number of integers within the range [A..B] that are divisible by K, i.e.:

{ i : A ≤ i ≤ B, i mod K = 0 }

For example, for A = 6, B = 11 and K = 2, your function should return 3, because there are three numbers divisible by 2 within the range [6..11], namely 6, 8 and 10.

Write an efficient algorithm for the following assumptions:

A and B are integers within the range [0..2,000,000,000];
K is an integer within the range [1..2,000,000,000];
A ≤ B.
      
<br/>

># 입출력 예



># 문제 풀이

```
class Solution {
    public int solution(int A, int B, int K) {
        
        if(A == 0){
            return B / K + 1;
        }else{
            return B / K - (A - 1) / K;
        }

    }
}

```

## 결과

1. CountDiv
Compute number of integers divisible by k in range [a..b].
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

잘생각해서 풀어야 한다 생각나는데로 풀면 포문돌려서 풀게 된다.. 그렇게 되면 퍼포먼스에서 0점을 맞게 된다.



