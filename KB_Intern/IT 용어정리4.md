---
title : "IT 용어 정리4 (PL/SQL, Dynamic SQL, DBIO 등)"
excerpt : "IT 용어 정리4"

categories :
 - 용어정리

 tags:
 - [증권사, KB, 펀드, 연금, 경제, 주식, 자산, IT, 디지털
 인턴, 전환형, 채용형 인턴]
---

IT 용어 정리4 (PL/SQL, Dynamic SQL, DBIO 등)
===========================================


## PL/SQL(Procedural Language/SQL)
> SQL 구문을 절차적 형태로 프로그래밍할 수 있게 만든 SQL의 확장  
>> 기존의 SQL은 절차적 언어 X  
>> 오라클 내에서만 사용 가능 

<br/>

### PL/SQL 특징  
1. 블록 단위 구성   
-> (DELCARE - BEGIN - EXCEPTION - END)  
2. 순차 처리 지원  
-> IF, LOOP, FOR WHILE 등과 같은 제어문, 반복문 사용 가능  
3. 패키지를 사용한 모듈화 지원  
-> 연관성을 가지는 타입, 상수, 변수, 커서 등의 프로그램들을 엮어 하나의 응용 단위로 구성  

<br/>

## Dynamic SQL(동적 SQL)  
> 사용될 SQL문이 Runtime 시에 결정되는 SQL문  
>> WHERE절이나 UPDATE절 등의 조건이 프로그램이 실행되는 도중 결정될 때 동적 SQL이 필요  

<br/>

### 동적 SQL 사용하는 경우    
1. PL/SQL 블록상 DDL을 사용해야 하는 경우       
2. PL/SQL 블록상 ALTER SYSTEM/SESSION 명령어를 실행해야 할 때    
3. 컴파일 타임에 존재하지 않는 DB 객체를 참조하는 경우(테이블 이름을 동적으로 생성)    

<br/>

## DBIO(DataBase InputOutput)  
> 개발 환경에서 '데이터베이스 접근'에 관한 표준적인 방법    
>> 객체는 클래스라는 틀에서 생겨난 실체(instance)    
>> 각각의 객체 안에는 '자료 구조'와 '알고리즘'이 들어있음    

<br/>

## 프레임워크(Framework)
> 많은 소프트웨어에서 사용되는 '일반적인 기능을 담은 틀'    
>> 개발 과정을 보다 빠르고 편리하게 해주며 오픈 소스이다      
>> 개발자는 프레임워크를 바탕으로 개별 기능을 구현해 좀 더 효율적으로 개발 가능    

<br/>

## 파싱(Parsing)  
> 데이터를 분해하고 조립하여 특정한 데이터만 추출하는 것   
>> 이러한 파싱을 수행하는 프로그램을 '파서(Paser)'라고 함

<br/>

## AS-IS / TO-BE
> AS-IS : 개선되기 전 / TO-BE : 개선된 후  


<br/>

### 참고 사이트
### https://whdvy777.tistory.com/entry/PLSQL-%EC%9D%B4%EB%9E%80-%EA%B8%B0%EB%B3%B8%EA%B0%9C%EB%85%90
### https://www.sindohblog.com/2181