---
layout: post
title:  "코딜리티 MaxProfit"
date:   2020-12-30 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
    
An array A consisting of N integers is given. It contains daily prices of a stock share for a period of N consecutive days. If a single share was bought on day P and sold on day Q, where 0 ≤ P ≤ Q < N, then the profit of such transaction is equal to A[Q] − A[P], provided that A[Q] ≥ A[P]. Otherwise, the transaction brings loss of A[P] − A[Q].

For example, consider the following array A consisting of six elements such that:

  A[0] = 23171
  A[1] = 21011
  A[2] = 21123
  A[3] = 21366
  A[4] = 21013
  A[5] = 21367
If a share was bought on day 0 and sold on day 2, a loss of 2048 would occur because A[2] − A[0] = 21123 − 23171 = −2048. If a share was bought on day 4 and sold on day 5, a profit of 354 would occur because A[5] − A[4] = 21367 − 21013 = 354. Maximum possible profit was 356. It would occur if a share was bought on day 1 and sold on day 5.

Write a function,

class Solution { public int solution(int[] A); }

that, given an array A consisting of N integers containing daily prices of a stock share for a period of N consecutive days, returns the maximum possible profit from one transaction during this period. The function should return 0 if it was impossible to gain any profit.

For example, given array A consisting of six elements such that:

  A[0] = 23171
  A[1] = 21011
  A[2] = 21123
  A[3] = 21366
  A[4] = 21013
  A[5] = 21367
the function should return 356, as explained above.
  

># 입출력 예



># 문제 풀이

```
class Solution {
//66점 퍼포먼스
    public int solution1(int[] A){

        int maxVal = Integer.MIN_VALUE;
        boolean check = false;

        for(int i = 0; i < A.length - 1; i++){

            int val = A[i];

            for(int j = i + 1; j < A.length; j++){
                int minus = A[j] - val;
                if(minus > 0){
                    check = true;
                }

                if(maxVal < minus){
                    maxVal = minus;
                }
            }
        }

        if(!check){
            return 0;
        }else{
            return maxVal;
        }

    }
}

class Solution {
    public int solution2(int[] A) {
        
        if(A.length == 0 || A.length == 1) return 0;

        int minPrice = A[0];

        int minus = 0;
        int max = 0;

        for(int i = 1; i < A.length; i++){

            minus = A[i] - minPrice;
            if(A[i] < minPrice){
                minPrice = A[i];
            }

            max = Math.max(minus,max);
        }

        if(max < 0) return 0;

        return max;
    }
}
```

## 결과

1. MaxProfit
Given a log of stock prices compute the maximum possible earning.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

solution1은 딱봐도 저렇게 풀어서 함정에 걸려라 이거다... 
아 어떻게 해야 이중포문을 안쓰고 처리를 할수 있을까 검색을 하다가 이런문제를 풀어나가는 알고리즘이 존재했다...



