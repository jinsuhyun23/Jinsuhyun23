---
title : "데이터 분석 Phython Pandas 라이브러리"

excerpt : "판다스(데이터 분석, 전처리, 모델링, 시각화)"

categories :
 - Phython

 tags:
 - [Phython, Pandas, read_csv, 전처리, 시각화,모델링, 데이터 분석]

---

Pandas pd.read_csv 파라미터 및 오류 해결
=====================================

## pd.read_csv() 사용 방법 및 파라미터
> pd.read_csv("파일 경로/파일명.csv")  

<br/>

### 1) sep = '구분자'
> 파일을 구분자 기준으로 분리하는 것
> default : 콤마(,) / csv : Comma Separated value      
>> ex) pd.read_csv(sep = "/")    

<br/>

### 2) header = 정수
> 컬럼명으로 사용할 행의 번호를 입력  
> default : 0    
>> ex) pd.read_csv(sep = "/")      

<br/>

### 3) index_col = 정수
> index로 사용할 열의 번호 입력  
>> ex) pd.read_csv(index_col = 1)    

<br/>

### 4) skiprows = 정수  
> 첫 행을 기준으로 데이터를 얼마나 건너뛰고 읽어올지 결정  
>> ex) pd.read_csv(skiprows = 3)

<br/>

### 5) nrows = 정수 
> 파일을 읽어올 행의 수 입력   
>> ex) pd.read_csv(nrows = 500)  

<br/>

### 6) date_parser = '속성'
> 시계열 타입으로 변환할 변수 입력  
>> ex) pd.read_csv(date_parser=['A', 'B'])        

<br/>  
     
## 오류 해결 방법

## 1. 내 작업 폴더 위치 확인    
> 작업 폴더 위치에 Load할 데이터를 놓아야 한다!  
> 아닐 경우 "해당 디렉토리에 파일이 없다고 나옴"  

<br/>

## 2) 데이터 주소 확인 (마우스 우클릭 - 속성 - 주소)    
> 작업 폴더 위치가 아닐 경우 옮김  
   
<br/>

## 3) pd_read.csv("파일경로/파일명.확장자")    
> 파일 경로에 'money 기호' 대신 '/' or '\\'를 넣어준다    
> \로 입력할 경우 유니코드로 인식하여 오류 발생     
     
    
<img src = "https://blog.kakaocdn.net/dn/b4isSi/btqBtXnABXw/YLkKkVkhYdKTmWl6pWjEg0/img.png">  

<br/>

###  작업 폴더 위치 확인 코드
<pre>
<code>
import os
import pandas as pd

print(os.getcwd()) # 내 작업 폴더 위치 출력
train = pd.read_csv('경로/파일명.csv')

</pre>
</code>


<br/>

### 참고 링크 : https://garlicsnackbar.tistory.com/3      


### 참고 링크 : https://dacon.io/competitions/official/235554/codeshare/585