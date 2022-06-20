---
title : "Phython 1차원 / 2차원 리스트 선언"
excerpt : "코드업 기초 100제_Phython"

categories :
 - Phython

 tags:
 - [Phython, 코드업, 기초 100제, 파이썬, 60~70번, 코딩테스트,
    리스트, List, 1차원, 2차원, XY좌표, 좌표]
---

Phython 1 & 2차원 리스트 선언 (for문, append() 이용)  
===========

## 1차원 리스트 형성 
<pre>
<code>
## 방법 1
for i in range(10):
    d = ([0] * i) # 0으로 채워진 1차원 리스트 형성 / 0이 9개(i = 0 일 때 0 삽입 X)
print(d) # [0, 0, 0, 0, 0, 0, 0, 0, 0]

# 방법 2
d = []
for _ in range(10):
    d.append(0) # 0으로 채워진 1차원 리스트 형성 / 0이 10개
print(d) # [0, 0, 0, 0, 0, 0, 0, 0, 0, 0] 


# 방법 2 (List Comprehension) -> 사용!
d = [0 for _ in range(10)] # 0으로 채워진 1차원 리스트 형성 / 0이 10개
print(d) # [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

</pre>
</code>

## 2차원 리스트 형성

<pre>
<code>
## 방법 1
d = []
for _ in range(10):
    d.append([]) # 빈 2차원 리스트 형성
print(d) # [[], [], [], [], [], [], [], [], [], []]


## 방법 1 (List Comprehension) -> 사용!
d = [[] for _ in range(10)] # 빈 2차원 리스트 형성
print(d) # [[], [], [], [], [], [], [], [], [], []]


## 방법 2
d = []
for _ in range(10):
    d.append([0]) # 0으로 채워진 2차원 리스트 형성
print(d) # [[0], [0], [0], [0], [0], [0], [0], [0], [0], [0]]


## 방법 2 (List Comprehension) -> 사용!
d = [[0] for _ in range(10)] # 0으로 채워진 2차원 리스트 형성
print(d) # [[0], [0], [0], [0], [0], [0], [0], [0], [0], [0]]
</pre>
</code>
