---
layout: post
title:  "코딜리티 Binary Gap"
date:   2020-12-11 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명

A binary gap within a positive integer N is any maximal sequence of consecutive zeros that is surrounded by ones at both ends in the binary representation of N.

For example, number 9 has binary representation 1001 and contains a binary gap of length 2. The number 529 has binary representation 1000010001 and contains two binary gaps: one of length 4 and one of length 3. The number 20 has binary representation 10100 and contains one binary gap of length 1. The number 15 has binary representation 1111 and has no binary gaps. The number 32 has binary representation 100000 and has no binary gaps.

Write a function:

class Solution { public int solution(int N); }

that, given a positive integer N, returns the length of its longest binary gap. The function should return 0 if N doesn't contain a binary gap.

For example, given N = 1041 the function should return 5, because N has binary representation 10000010001 and so its longest binary gap is of length 5. Given N = 32 the function should return 0, because N has binary representation '100000' and thus no binary gaps.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..2,147,483,647]. 

<br/>

># 입출력 예

N = 1041 , return 5  
N = 32 , return 0


># 문제 풀이

```
class Solution {
    public int solution(int N) {
        
        String binary = Integer.toBinaryString(N);

        int maxCnt = 0;
        int cnt = 0;

        for(int i = 0 ; i < binary.length(); i++ ){
            
            String num = binary.substring(i,i+1);

            if(num.equals("1")){
                if(maxCnt < cnt){
                    maxCnt = cnt;
                }
                cnt = 0;
            }else{
                cnt++;
            }

        }

        return maxCnt;

    }
}

```

## 결과

1. BinaryGap
Find longest sequence of zeros in binary representation of an integer.
Task Score
100%
Correctness
100%
Performance
Not assessed


## 정답해설

2진수로 변환을 한다음 .... 음 설명보다는 코드를 보면 금방 이해가 갈것이다.

오랜만에 다시 풀어보니깐 새롭다 ... 그동안 열심히 하고는 있었지만 역시 시간이 지나고 다시 풀어봐야 
내가 잘하고 있는지 실력이 늘었는지 알수 있다. 조금은 실력이 좋아진것 같다.



