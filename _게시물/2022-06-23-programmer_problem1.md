---
title : "프로그래머스 2021 카카오 채용연계형 인턴십 1번 문제"
excerpt : "Lv1 숫자 문자열과 영단어_Phython"

categories :
 - Phython

 tags:
 - [Phython, 프로그래머스, string, 파이썬, 코딩테스트, 스터디]
---

< 숫자 문자열과 영단어> 2021 카카오 채용연계형 인턴십 문제
===================

# 프로그래머스 Lv1 문제 및 풀이
<img src = "https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/d31cb063-4025-4412-8cbc-6ac6909cf93e/img1.png">  

## 문제 설명

네오와 프로도가 숫자놀이를 하고 있습니다. 네오가 프로도에게 숫자를 건넬 때 일부 자릿수를 영단어로 바꾼 카드를 건네주면 프로도는 원래 숫자를 찾는 게임입니다.  
  
<br/>

다음은 숫자의 일부 자릿수를 영단어로 바꾸는 예시입니다.  
1478 → "one4seveneight"  
234567 → "23four5six7"  
10203 → "1zerotwozero3"  
  
<br/>

이렇게 숫자의 일부 자릿수가 영단어로 바뀌어졌거나, 혹은 바뀌지 않고 그대로인 문자열 s가 매개변수로 주어집니다. s가 의미하는 원래 숫자를 return 하도록 solution 함수를 완성해주세요.  
  
참고로 각 숫자에 대응되는 영단어는 다음 표와 같습니다.  
  
숫자	영단어  
0	zero  
1	one     
2	two     
3	three     
4	four    
5	five    
6	six  
7	seven    
8	eight  
9	nine   

__________________________________________________________

## 제한사항  
1 ≤ s의 길이 ≤ 50  
s가 "zero" 또는 "0"으로 시작하는 경우는 주어지지 않습니다.  
return 값이 1 이상 2,000,000,000 이하의 정수가 되는 올바른 입력만 s로 주어집니다.  

<br/>

__________________________________________________________
  
<br/>

   
## 입출력 예  
1 ≤ s의 길이 ≤ 50    
s가 "zero" 또는 "0"으로 시작하는 경우는 주어지지 않습니다.  
return 값이 1 이상 2,000,000,000 이하의 정수가 되는 올바른 입력만 s로 주어집니다.  
  
<br/>

입출력 예 #1  
문제 예시와 같습니다.  
입출력 예 #2  
문제 예시와 같습니다.  
입출력 예 #3  
"three"는 3, "six"는 6, "seven"은 7에 대응되기 때문에 정답은 입출력 예 #2와 같은 234567이   됩니다.    
입출력 예 #2와 #3과 같이 같은 정답을 가리키는 문자열이 여러 가지가 나올 수 있습니다.  
입출력 예 #4  
s에는 영단어로 바뀐 부분이 없습니다.  

<br/>
  
__________________________________________________________

## 제한시간 안내  
정확성 테스트 : 10초
__________________________________________________________
## 해결 아이디어
### 방법 1) one -> 1로 한 번에 바꾸는 방법    
-> .replace 함수로 처음에 못 바꿀거라고 생각했음. 하지만 문자열 내 연속된 원소 값들을 replace로 대체 가능  
  
### 방법 2) 한 글자씩 담다가 key 값('one')에 해당하는 값이 완성될 경우 변경   

<br/>

__________________________________________________________
## 풀이방식 1
<pre>
<code>
def solution(s): # s = one4seveneight
    d = {'zero':'0', 'one' : '1', 'two' : '2', 'three' : '3',
        'four' : '4', 'five' : '5', 'six' : '6',
        'seven' : '7', 'eight' : '8', 'nine' : '9'}
    for key, val in d.items(): # key : 'zero' -> val : '0'
        s = s.replace(key, val)
    return int(s)
</pre>
</code>

<br/>

## 풀이방식 2
<pre>
<code>
def solution(s): # s = one4seveneight
    space = '' # 문자열을 임시로 담을 공간
    anw = '' # 정답 string
    d = {'zero':'0', 'one' : '1', 'two' : '2', 'three' : '3',
        'four' : '4', 'five' : '5', 'six' : '6',
        'seven' : '7', 'eight' : '8', 'nine' : '9'}
    for i in s: # o, n, e, 4, s, e, v, e, n ...
        if (i.isnumeric()): 
            anw += i
        else:
            space += i
            if space in d.keys(): # space = 'one'
                val = d[space] # val = d['one'] = '1'
                anw += val # anw = anw + '1'
                space = '' # 공간 초기화
    return int(anw)        
</pre>
</code>

__________________________________________________________
## 인사이트
### key랑 value를 동시에 사용할 경우 사전형으로 구성  
> dictionary.keys() -> 사전형의 key 값들 반환  
> dictionary.values()) -> 사전형의 value 값들 반환  
> dictionary.items() -> 사전형의 key, value 값들 반환    

> 사전형의 d.items()를 통해 key, value 값을 반환하거나, enumerate를 통해 idx, value 값을 반환하여 풀어야 하는 문제들이 많음!!   

<pre>
<code>
예시
example = ['안녕', '나는', '너의', '친구일걸']
example2 = {'hello' : '0', 'Bye' :'1'}

for idx, val in enumerate(example):
    ~~

for key, val in d.items(example2):
    ~~
</pre>
</code>

### string.replace(기존 값, 바꿀 값)을 통해 중간에 있는 값을 통째로 바꿀 수 있다  


<br/>

__________________________________________________________
