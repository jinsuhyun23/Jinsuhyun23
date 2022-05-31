---
title : "코딩 테스트를 위한 Phython 문법(자료형)"

excerpt : "자료형(리스트, 튜플, 집합, 연산, 관련 함수)"

categories :
 - Phython

 tags:
 - [Phython, 자료형, 리스트, 튜플, 집합, 연산, 코딩 테스트]

---

코딩 테스트를 위한 Phython 문법(자료형)
===========================

## [이것이 코딩테스트다](https://book.naver.com/bookdb/book_detail.naver?bid=16439154) 책 코드 참조

<br/>

## 10억 지수 표현 방식
a = 1e9 # a = 1000000000 (0이 9개 있는 것과 동일)
print(a)

a = 75.25e1 # 752.5
print(a)

a = 3954e-3 # 3.954
print(a)

a = 0.3 + 0.6 # 0.89999999
print(a)


<br/>


## 사칙 연산
a = 7
b = 3

print(a / b) # 나누기

print(a % b) # 나머지

print(a // b) # 몫

print(a ** b) # 거듭제곱

<br/>


## 리스트 자료형
a = [1,2,3,4,5,6,7,8,9]
print(a)

print(a[5]) # 슬라이싱 a의 6번째 index 추출

a = list() # 빈 리스트 선언 방법 1
print(a)

a = list() # 빈 리스트 선언 방법 2
print(a)

n = 10
a = [0] * n 
print(a) # [0,0,0,0,0,0,0,0,0,0]


<br/>


## 인덱싱(indexing)
### 인덱스 값을 통해 리스트의 '특정 원소 값'에 접근하는 것
a = [1,2,3,4,5,6,7,8,9]

print(a[-1]) # 뒤에서 첫 번째

print(a[-3]) # 뒤에서 세 번째

a[3] = 7 # 네 번째 원소 값 변경
print(a)

<br/>



## 슬라이싱(Slicing)
### 리스트에서 인덱스 값을 통해 연속적인 위치를 갖는 원소들을 가져오는 것
print(a[1:4]) # 두 번째 ~ 네 번째 원소 추출

<br/>


## 리스트 컴프리헨션(List Comprehension)
### 대괄호[] 안에 '조건문'과 '반복문'을 넣어 리스트를 초기화하는 방법 중 하나
array = [i for i in range(20) if i % 2 == 1] # (순서) 결과 값 / 반복문 / 조건문 
print(a) # 1 ~ 20 사이 홀수 출력

array = [i * i for i in range(1,10)] 
print(array) # 1 ~ 9의 제곱 값 출력


<br/>


## N x M 크기의 2차원 리스트 초기화
n = 3
m = 4
array = [[0]*m for _ in range(n)] # n x m 형태 2차원 리스트 [0]으로 초기화
print(array)

array[1][1] = 5 # 2 x 2 자리의 원소 값 5로 변경
print(array)

<br/>


## 리스트 관련 함수 
a = [1,4,3]
print("기본 리스트 :", a)

a.append(2) # 맨 오른쪽에 추가
print("삽입 :", a)

a.sort() # default : 오름차순 정렬
print("오름차순 정렬 :", a)

a.sort(reverse = True) # 내림차순 정렬
print("내림차순 정렬 :", a)

a.reverse()
print("원소 뒤집기 :", a)

<br/>

a.insert(2, 3)
print("2번째 인덱스에 3 추가 :", a)

print("값이 3인 데이터 개수 :", a.count(3))

a.remove(1)
print("값이 1인 데이터 삭제 :", a)

<br/>

a = [1, 2, 3, 4, 5, 5, 5]
remove_set = [3, 5]

result = [i for i in a if i not in remove_set] # 중복 값도 모두 삭제
print(result) # 1, 2, 4


<br/>


## 문자열 자료형 
data = "Hello World"
print(data)

data = "Don't you Know \"Phython\"?" # 탈출 문자(\) 뒤에 " or '(따옴표 삽입)
print(data)

data = "Don't you Know 'Phython'?" # 큰 따옴표 안에 작은 따옴표
print(data)

data = 'Don\'t you Know "Phython"?' # 작은 따옴표 안에 큰 따옴표
print(data)

<br/>

a = "Hello"
b = "World"

print(a + " " + b) # Hello World

a = 'String'
print(a*3) # StringStringString

a = 'ABCDEF'
print(a[2:4]) # CD


<br/>


## 튜플 자료형
### 한 번 선언 후 변경 불가
### 리스트는 대괄호[] 사용, 튜플은 소괄호() 사용
a = (1,2,3,4)
print(a)

-> a[2] = 7 -> 오류 발생 / 튜플 원소 값은 수정 불가 !!


<br/>


## 사전 자료형
### 키(Key)와 값(Value)의 쌍을 데이터로 가지는 자료형
data = dict()
data['사과'] = 'Apple' # 1개 원소 값 입력 방식
data['바나나'] = 'Banana'
data['코코넛'] = 'Coconut'
print(data)

data2 = dict()
data2 = {'사과' : 'Apple', '바나나' : 'Banana', '코코넛' : 'Coconut'} # 여러 개 원소 값 입력 방식 
print(data2)

<br/>

if '사과' in data and '바나나' in data2:
  print('사과와 바나나를 키로 가지는 데이터 존재')

key_list = data.keys() # 키 데이터만 담은 리스트
value_list = data.values() # Value 데이터만 담은 리스트
print(key_list)
print(value_list)

for key in key_list:
  print(data[key]) # 키 값을 토대로 값 추출

<br/>

'''
파이썬 내 리스트, 문자열, 튜플 등은 원소들을 차례로 반복 가능한 iterable 자료형이라 함.
이러한 iterable 자료형은 in 문법도 사용 가능함
'''

<br/>


## 집합 자료형
### 중복 허용 x / 순서 x  -> 인덱싱 불가

data = set([1,1,2,3,4,4,5]) # 1, 2, 3, 4, 5 (중복 불가)
print(data)

data = {1, 1, 2, 3, 4, 4, 5} # 1, 2, 3, 4, 5
print(data)

a = set([1, 2, 3, 4, 5])
b = set([3, 4, 5, 6, 7])

print(a | b) # 합집합
print(a & b) # 교집합
print(a - b) # 차집합

<br/>

data = set([1,2,3])
print(data)

data.add(4) # 맨 오른쪽 원소 추가
print(data)

data.update([5,6]) # 맨 오른쪽 원소 '여러 개' 추가
print(data)

data.remove(3) # 특정 원소 제거
print(data)

print(type(data))

<br/>
