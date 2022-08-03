---
title : "SQL 공부1 (오라클 기본 함수)"
excerpt : "SQL"

categories :
 - 프로그래밍 공부

 tags:
 - [증권사, KB, C언어, 프로그래밍, 코딩,
 개발자, IT, 디지털
 인턴, 전환형, 채용형 인턴]
---

SQL 공부1 (오라클 내장 함수)
===========================================

## 숫자 함수(Number Function)    
1. ABS(n) : n의 절대값 반환    
> n = -10 -> ABS(-10) = 10  

2. CEIL(n) : n보다 큰 최소 정수값 반환    
> n = 5.1 -> CEIL(5.1) = 6   

3. FLOOR(n) : n보다 작거나 같은 최대 정수 값 반환     
> n = 5.1 -> FLOOR(5.1) = 5    

4. MOD(m, n) : m을 n으로 나눈 '나머지'를 반환    
> m, n = 5, 3 -> MOD(5, 3) = 2  

5. POWER(m, n) : m의 n승 값을 반환  
> m, m = 5, 3 -> POWER(5, 3) = 125  

6. ROUND(m, n) : m을 소수점 n번째 자리까지 반올림  
> m, n = 11.126, n = 1 -> ROUND(11.126, 1) = 11.1  

7. TRUNC(m, n) : m의 소수점 n번째 자리에서 절삭  
> m, n = 10.678, 2 -> ROUND(10.678, 2) = 10.67  

<br/>

## 문자 함수(String Function)  
1. CONCAT(str1, str2) : 두 문자열을 합치는 함수("||" 연산자와 같은 역할)  
> CONCAT('ORACLE', 'Korea') -> ORACLE Korea  

2. INITCAP(str) : 주어진 문자열의 첫 번째 글자를 '대문자 변환'  
> INITCAP('test') -> Test    
   
3. LOWER(str) : 소문자 변환     
> LOWER('HELLO') -> hello    

4. UPPER(str) : 대문자 변환    
> UPPER('hello') -> HELLO  

5. SUBSTR(str, n, m) : 문자열을 n부터 m개만큼 슬라이싱  
> SUBSTR('Hello', 2, 3) -> ell  

6. REPLACE(str1, str2, str3) : str1에서 str2와 일치하는 부분을 str3으로 대체  
> REPLACE('Hello', 'o', 'H') -> HellH  

<br/>
  
## 날짜 함수  
1. SYSDATE : 현재 시스템 일자 반환  

2. SYSTIMESTAMP : 현재 시스템 타임스탬프 반환  

3. ADD_MONTHS(date, int) : date에 int만큼 월 수를 더한 날짜 반환  

4. MONTHS_BETWEEN(date1, date2) : date1과 date2 사이의 개월 수 반환  

5. LAST_DAY(date) : date의 월말일 반환  

<br/>

## 변환 함수  
1. TO_CHAR(char or date, format) : 숫자 혹은 날짜를 format에 맞는 문자로 변환   

2. TO_NUMBER(data, format) : data를 format에 맞는 숫자로 변환    

3. TO_DATE(char, format) : char를 format에 맞는 날짜로 변환   

4. TO_TIMESTAMP(char, formart) : char을 format에 맞는 타임스탬프로 변환  

<br/>

## NULL 관련 함수  
1. NVL(i1, i2) : i1이 NULL이면 i2를 반환  

2. NVL2(i1, i2, i3) : i1이 NULL이면 i2를 아니면, i3를 반환  

3. LNNVL(조건식) : 조건식의 결과가 FALSE 혹은 unknown이면 True, True이면 False 반환  

4. NULLIF(i1, i2) : i1과 i2가 동일한 값이면 NULL을, 아니면 i1을 반환  

 
<br/>

### 참고 게시글 : https://jhbench.tistory.com/27, https://preamtree.tistory.com/40  



