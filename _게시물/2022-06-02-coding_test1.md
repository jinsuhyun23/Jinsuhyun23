---
title : "코딩 테스트 대비 자료 구조(Stack, Queue)"

excerpt : "스택, queue, dequeue, 재귀 함수/반복 함수"

categories :
 - Phython

 tags:
 - [Phython, 스택, queue, dequeue, 자료구조, 재귀함수]
---

자료 구조(Stack, Queue) 개념 정리
===========================

## [이것이 코딩테스트다](https://book.naver.com/bookdb/book_detail.naver?bid=16439154) 책 코드 참조

<br/>

# 자료구조 기초

## 탐색(Search) 
많은 양의 데이터 중 원하는 데이터를 찾는 과정  
대표적인 탐색 알고리즘으로는 DFS와 BFS가 있음

## 자료 구조(Data Structure)
데이터를 표현하고, 관리하고, 처리하기 위한 구조  
그 중 스택과 큐는 자료 구조의 기초 개념으로 다음의 두 핵심 함수로 구성  

삽입(push) -> 데이터를 삽입한다
삭제(pop) -> 데이터를 삭제한다

<br/>

> 오버 플로(Over flow)  
특정한 자료 구조가 수용 가능한 데이터 크기를 넘은 상태에서,
삽입 연산을 수행할 때 발생한다

> 언더 플로(Under flow)  
특정한 자료구조에 데이터가 전혀 없는 상태에서, 삭제 연산을 수행할 때 발생한다

<br/>

## 스택(Stack)
### 박스 쌓기와 같고, 이러한 구조를 '선입후출'이라 한다  
### 별도의 라이브러리 사용 x / list의 append와 pop 함수 이용

<br/>

stack = [] 

stack.append(5) # 5  
stack.append(2) # 5 2  
stack.append(3) # 5 2 3  
stack.append(7) # 5 2 3 7  
stack.pop()     # 5 2 3  
stack.append(1) # 5 2 3 1  
stack.append(4) # 5 2 3 1 4  
stack.pop()     # 5 2 3 1  

print(stack) # 최하단 원소부터 출력 -> 5 2 3 1  
print(stack[::-1]) # 최상단 원소부터 출력 -> 1 3 2 5  

<br/>

## 큐(Queue)
### 대기 줄과 같고, 이러한 구조를 '선입선출'이라 한다
### Collections 모듈의 deque 라이브러리 사용  

<br/>

from collections import deque  
queue = deque() # 큐 구현을 위한 deque 라이브러리 사용

삽입 - 삽입 - 삽입 - 삽입 - 삭제 - 삽입 - 삽입 - 삭제  
queue.append(5) # 5  
queue.append(2) # 5 2  
queue.append(3) # 5 2 3  
queue.append(7) # 5 2 3 7  
queue.popleft() # 2 3 7  
queue.append(1) # 2 3 7 1  
queue.append(4) # 2 3 7 1 4  
queue.popleft() # 3 7 1 4  

<br/>

print(queue)    # 먼저 들어온 순서대로 출력 -> 3 7 1 4  
queue.reverse() # 역순으로 뒤집기  
print(queue)    # 나중에 들어온 순서부터 출력 -> 4 1 7 3  
list(queue) # deque 객체 -> 리스트 자료형 변환  

<br/>

## 재귀 함수는 '자기 자신'을 다시 호출하는 함수를 의미
### 문제 풀이에서는 재귀 함수가 언제 끝날 지, '종료 조건'을 명시해야 한다!!

<br/>

def recursive_function(i):  
  if i == 20: # 20번째 출력 시 종료  
    return  
  print(i, '번째 재귀 함수에서', i+1, '번째 재귀 함수를 호출')  
  recursive_function(i+1)  
  print(i, '번째 재귀 함수를 종료합니다.')  
  
recursive_function(1)  

<br/>

## 반복적으로 구현한 n!  
def factorial_iterative(n):  
  result = 1  
  for i in range(1, n+1):  
    result *= i  
  return result  
 
<br/>

## 재귀적으로 구현한 n!  
def factorial_recursive(n):  
  if n <= 1: # n이 1이하인 경우 1 반환  
    return 1  
  return n * factorial_recursive(n-1) # n! = n * (n-1)! 작성  
  
print('반복적으로 구현 :', factorial_iterative(5))  
print('재귀적으로 구현 :', factorial_recursive(5))  