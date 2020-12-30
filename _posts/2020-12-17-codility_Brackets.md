---
layout: post
title:  "코딜리티 Brackets"
date:   2020-12-16 08:00:24 +0800
categories: 알고리즘
tags: [알고리즘]
comments: false
---

># 문제 설명
  
A string S consisting of N characters is considered to be properly nested if any of the following conditions is true:

S is empty;
S has the form "(U)" or "[U]" or "{U}" where U is a properly nested string;
S has the form "VW" where V and W are properly nested strings.
For example, the string "{[()()]}" is properly nested but "([)()]" is not.

Write a function:

class Solution { public int solution(String S); }

that, given a string S consisting of N characters, returns 1 if S is properly nested and 0 otherwise.

For example, given S = "{[()()]}", the function should return 1 and given S = "([)()]", the function should return 0, as explained above.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [0..200,000];
string S consists only of the following characters: "(", "{", "[", "]", "}" and/or ")".

># 입출력 예



># 문제 풀이

```
import java.util.*;

class Solution {
    public int solution(String S) {
       char[] chars = S.toCharArray();

        Stack<Character> stack = new Stack<>();


        for(int i = 0 ; i < chars.length ; i++){

            if(chars[i] == '{' || chars[i] == '[' || chars[i] =='('){
                stack.push(chars[i]);
            }else{

                if(stack.isEmpty()){
                   return 0;
                }

                char top = stack.pop();

                if (chars[i] == '}' && top != '{') {
                    return 0;
                }

                if (chars[i] == ']' && top != '[') {
                    return 0;
                }

                if (chars[i] == ')' && top != '(')  {
                    return 0;
                }
            }

        }

        if(stack.isEmpty()){
            return 1;
        }

        return 0;
    }
}
```

## 결과

1. Brackets
Determine whether a given string of parentheses (multiple types) is properly nested.
Task Score
100%
Correctness
100%
Performance
100%

## 정답해설

스택문제다... 거의 이건 공식인 문제. 하지만 오랜만에 다시 풀어보니깐 갑자기 생각이 안나서 당황스러웠다
안되면 뭐 계속 다시 풀고 또 풀고 하는거지 뭐... 



