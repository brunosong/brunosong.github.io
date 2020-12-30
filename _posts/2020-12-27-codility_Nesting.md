---
layout: post
title:  "코딜리티 Nesting"
date:   2020-12-27 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
    
A string S consisting of N characters is called properly nested if:  
  
S is empty;  
S has the form "(U)" where U is a properly nested string;  
S has the form "VW" where V and W are properly nested strings.  
For example, string "(()(())())" is properly nested but string "())" isn't.  
  
Write a function:  
  
class Solution { public int solution(String S); }  
   
that, given a string S consisting of N characters, returns 1 if string S is properly nested and 0 otherwise.  
  
For example, given S = "(()(())())", the function should return 1 and given S = "())", the function should return 0, as explained above.  
  
Write an efficient algorithm for the following assumptions:  
  
N is an integer within the range [0..1,000,000];  
string S consists only of the characters "(" and/or ")".  

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(String S) {

        char[] chars = S.toCharArray();

        Stack<Character> stack = new Stack<>();
        
        for (char c : chars){
            
            if(c == '('){
                stack.push(c);
            }else{
                if(stack.isEmpty()){
                    return 0;
                }else{
                    if(stack.peek() == ')'){
                        return 0;
                    }    
                }
                stack.pop();
            }
        }
        
        if(stack.isEmpty()){
            return 1;
        }else{
            return 0;
        }
        

    }
}
```

## 결과

1. Nesting
Determine whether a given string of parentheses (single type) is properly nested.
Task Score
100%
Correctness
100%
Performance
100%


## 정답해설

이것도 못하면 안되겠지.... 그래도 쉽게 풀었다.


