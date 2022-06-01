---
title : "코딩 테스트를 위한 Phython 문법(조건문, 반복문, 입출력 등)"

excerpt : "조건문, 반복문, 입출력 등"

categories :
 - Phython

 tags:
 - [Phython, 조건문, 반복문, 입출력, 코딩 테스트, for문, while문, if문]
---

코딩 테스트를 위한 Phython 문법
(조건문, 반복문, 입출력 등)
===========================


'''
조건문 구조

if 조건문 1:
  조건문 1이 True일 때 실행되는 코드
elif 조건문 2:
  조건문 1이 아니라, 조건문 2가 True일 때 실행되는 코드
else:
  위의 모든 조건문이 아닐 경우, 실행되는 코드
'''

score = 90

if score >= 90:
  print("학점 A")
elif score >= 80:
  print("학점 B")
elif score >= 70:
  print("학점 C")
else:
  print("학점 F")

# if 중첩문
if score >= 70:
  print("성적 70점 이상")
  if score >= 90:
    print("우수한 성적입니다.")
else:
  print("분발 하세요")


'''
비교 연산자
X == Y -> X와 Y가 서로 같을 때 True
X != Y -> X와 Y가 서로 다를 때 True
X > Y -> X가 Y보다 클 때 True
X < Y -> X가 Y보다 작을 때 True
X >= Y -> X가 Y보다 크거나 같을 때 True
X <= Y -> X가 Y보다 작거나 같을 때 True

논리 연산자
X and Y -> X와 Y 모두 만족할 때 True
X or Y -> X와 Y 중 하나 이상 만족할 때 True
Not X -> X가 거짓일 때 True

In / Not in 연산자
X in 리스트 -> 리스트 안에 X가 있을 때 True
X not in 문자열 -> 문자열 아넹 X가 없을 때 True

Pass / Continue / Break
pass -> 실행할 코드가 없는 것, 다음 코드 진행
continue -> 바로 다음 순번의 loop 수행
break -> 반복문 멈추고 loop 밖으로 이탈
'''

a = [1, 2, 3, 4, 5, 5, 5]
remove_set = {3, 5}

result = [] # 빈 리스트 선언
for i in a: 
  if i not in remove_set: # 제거 집합에 속하지 않을 경우, result 리스트에 추가
    result.append(i)

print(result)

result = [i for i in a if i not in remove_set] # 위의 코드와 결과 동일
print(result)


'''
반복문
1) While문 : 조건문이 참일 때, 반복적으로 코드가 수행
While 조건:
  실행할 소스 코드

2) for문 : 반복문
for 변수 in 리스트:
  실행할 소스 코드
'''

i = 1
result = 0

while i<=9:
  if i % 2 == 1:
    result += i
  i += 1

print(result)

result = 0
for i in range(1, 10):
  result += i

print(result)

scores = [90, 85, 77, 65, 97]
cheating_list = {2, 4}

for i in range(5):
  if i+1 in cheating_list:
    continue
  if scores[i] >= 80:
    print(i+1, "번 학생은 합격입니다.")

# 중첩 반복문 (구구단 예시)
for i in range(2, 10):
  for j in range(1, 10):
    print(i, "X", j, "=", i*j)
  print()


'''
함수
동일 코드의 반복을 줄이기 위해 사용하는 도구
def 함수명(매개 변수):
  실행할 소스코드
  return 반환 값 [없어도 됌]
'''

a = 0
def func():
  global a # 전역변수 사용 선언
  a += 1

for i in range(10):
  func()

print(a)

'''
map 함수 (파이썬 내장함수)
map(변환 함수, iterable 데이터) -> 리스트, 튜플 등
map 함수의 반환 값은 'map 함수 객체'이므로, 리스트로 변환 해주어야 함.
'''

# 입출력 
# input() -> 한 줄의 문자열 입력 받음

# 입력을 위한 전형적인 소스코드
n = int(input())
data = list(map(int, input().split())) # 각 데이터를 공백 구분하여 입력 받음

data.sort(reverse = True)
print(data)

# 공백을 기준으로 구분한, 적은 수 데이터 입력
n, m, k = map(int, input().split())
print(n,m,k)

import sys
sys.stdin.readline().rstrip() # 입력 개수가 많은 경우 사용!!

data = sys.stdin.readline().rstrip()
print(data)