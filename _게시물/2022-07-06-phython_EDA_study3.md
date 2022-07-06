---
title : "Pandas 및 Phython 내장 함수"
excerpt : "판다스, 파이썬, 함수 정리"

categories :
 - Phython

 tags:
 - [Phython, pandas, pd.read_csv, 시각화, 함수, 정리, Seaborn]
---

Pandas 및 Phython 내장 함수1
===========================  


## 1) pandas.read_csv('경로')
ex) df = pd.read_csv('Data/sample_data.csv')

### 유용한 인자(argument)  
> parse_dates : 해당 속성을 datetime64[ns] 형태로 읽어 옴    
ex) df = pd.read_csv('Data/sample_data.csv',
                    parse_dates = ['sales_date']) # sales_date를 datetime64[ns] 형태로 읽기

> usecols : 여러 열 중에 필요한 열만 가져 옴    
ex) df = pd.read_csv('Data/sample_data.csv',
                    usecols = ['store', 'product', 'sales_qty])  # store, product, sales_qty 속성만 읽기    

> nrows : 파일의 처음 n개 행만 읽어 옴  
ex) df = pd.read_csv('Data/sample_data.csv',
                    nrows = 100) # 상위 100개 행만 읽기  

<br/>

## 2) map(function, iterable)    
ex) result = list(map(int, mylist))  # mylisxt에 int 함수 적용  

첫 번째 매개변수 : 함수  
두 번째 매개 변수 : 반복 가능한 자료형(리스트, 튜플 등)   
-> map 함수의 반환 값은 <map 객체>이므로 해당 자료형을 직접 list 혹은 tuple로 형 변환 시켜줘야 함  

* map(적용시킬 함수, 적용할 값들)

<br/>

## 3) Dataframe.astype(dtype)  
ex) result = result.astype(int) # result의 자료형을 int로 변환      
ex) result = result.astype({'store' : 'category', 'sales' : 'float'}) # result의 store 속성 범주형 변환 / sales 속성 float 형 변환    

첫 번째 매개 변수: 변경할 데이터 타입  

<br/>


### 매개 변수 
-> 변수의 특별한 종류로서, 함수 등과 같은 '서브 루틴'의 인풋으로 제공되는 변수를 의미  

### 인자(argument)   
-> 매개변수의 실제로 담기는 값

<pre>
<code>
def test(a, b): # a, b -> 매개 변수
    return a + b

test(1, 2) # 1, 2 -> 인자
</pre>
</code>