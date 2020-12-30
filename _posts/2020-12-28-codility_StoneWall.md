---
layout: post
title:  "코딜리티 StoneWall"
date:   2020-12-28 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
    
You are going to build a stone wall. The wall should be straight and N meters long, and its thickness should be constant; however, it should have different heights in different places. The height of the wall is specified by an array H of N positive integers. H[I] is the height of the wall from I to I+1 meters to the right of its left end. In particular, H[0] is the height of the wall's left end and H[N−1] is the height of the wall's right end.  
  
The wall should be built of cuboid stone blocks (that is, all sides of such blocks are rectangular). Your task is to compute the minimum number of blocks needed to build the wall.  
  
Write a function:  
  
class Solution { public int solution(int[] H); }  
  
that, given an array H of N positive integers specifying the height of the wall, returns the minimum number of blocks needed to build it.  
  
For example, given array H containing N = 9 integers:  
  
  H[0] = 8    H[1] = 8    H[2] = 5  
  H[3] = 7    H[4] = 9    H[5] = 8  
  H[6] = 7    H[7] = 4    H[8] = 8  
the function should return 7. The figure shows one possible arrangement of seven blocks.  
  
  
  
Write an efficient algorithm for the following assumptions:  

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(int[] H) {
        int resultCnt = 0;

        Stack<Integer> stack = new Stack<>();

        for(int i = 0; i < H.length; i++){

            while (true){
                if(stack.isEmpty()) {
                    stack.push(H[i]);
                    break;
                }

                if(stack.peek() > H[i]) {
                    stack.pop();
                    resultCnt++;
                }else if(stack.peek() < H[i]){
                    stack.push(H[i]);
                    break;
                }else if(stack.peek() == H[i]){
                    break;
                }
            }
        }

        return resultCnt + stack.size();
    }
}
```

## 결과

1. StoneWall
Cover "Manhattan skyline" using the minimum number of rectangles.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

이 문제는 아직도 이해를 못하겠다... 하지만 힌트를 얻어서 문제를 풀어냈다.. 그림을 아직도 이해를 못하겠다.


