---
layout: post
title:  "코딜리티 MinPerimeterRectangle"
date:   2020-01-05 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
    
n integer N is given, representing the area of some rectangle.

The area of a rectangle whose sides are of length A and B is A * B, and the perimeter is 2 * (A + B).

The goal is to find the minimal perimeter of any rectangle whose area equals N. The sides of this rectangle should be only integers.

For example, given integer N = 30, rectangles of area 30 are:

(1, 30), with a perimeter of 62,
(2, 15), with a perimeter of 34,
(3, 10), with a perimeter of 26,
(5, 6), with a perimeter of 22.
Write a function:

class Solution { public int solution(int N); }

that, given an integer N, returns the minimal perimeter of any rectangle whose area is exactly equal to N.

For example, given an integer N = 30, the function should return 22, as explained above.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..1,000,000,000].
  

># 입출력 예



># 문제 풀이

```
class Solution {
    public int solution(int N) {

        int sqrt = (int)Math.sqrt(N);
        int minVal = Integer.MAX_VALUE; 

        for(int i = 1; i <= sqrt; i++){
            if(N % i == 0){
                if(2 * (i + N / i) < minVal){
                    minVal = 2 * (i + N / i);
                }
            }
        }

        return minVal;
    }
}
```

## 결과

1. MinPerimeterRectangle
Find the minimal perimeter of any rectangle whose area equals N.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

이것도 역시나 brute force로 풀라고 꼬시고 있는 문제다..
그래서 첫번째로 제곱근을 구한다음 제곱근과 까지 포문을 돌리면서 값과 제곱근을 나눠주면 되는 문제다... 
그냥 공식을 알아야 쉽게 풀수 있다... esay라고 하지만 난 너무 어렵다...



