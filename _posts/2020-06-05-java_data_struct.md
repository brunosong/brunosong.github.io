---
layout: post
title:  "스택, 큐, 덱"
date:   2020-06-05 08:00:24 +0800
categories: 자바
tags: [자바]
comments: false
---

># 스텍(Stack)

LIFO(last in first out) 으로 처음 들어간 데이터가 제일 나중에 나오는 자료구조이다.
함수를 실행할때(콜 스택) 쓰이고 재귀에 단골메뉴이다.
- 삽입은 push()를 사용
- 꺼낼때 pop()을 사용
- 맨위에 있는 데이터를 확인할때 peek()을 사용

<br />

># 큐(Queue)

FIFO(first in first out) 으로 처음 들어간 데이터가 가장 먼저 나오는 자료구조이다.  
컴퓨터 버퍼에 주로 사용되며 많은 입력 데이터로 인해 처리를 하지 못할 때 버퍼(큐)를 만들어 대기 시킨다.  
개선된 원형 큐가 나왔으며 메모리 공간을 잘 활용하나 배열로 구현되어 있기 때문에 큐의 크기가 제한되는 단점도 존재한다.  
Queue q = new LinkedList<>() 이렇게 사용이 가능하다.
- 삽입은 offer()를 사용
- 꺼낼때 poll()을 사용
- 맨뒤에 있는 데이터를 확인할때 peek()을 사용

<br />

># 덱(Deque)

자료의 입력과 출력이 양쪽 끝에서 가능하게 하는 자료구조.    
스크롤(scroll) : 입력이 한쪽 끝으로만 가능하도록 제한한 덱.  
셀프(shelf) : 출력이 한쪽 끝으로만 가능하도록 제한한 덱.  




