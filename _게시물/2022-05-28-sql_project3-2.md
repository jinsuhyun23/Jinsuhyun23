---
title : "SQL 3차 과제 - 데이터 분석 보고서 작성(ppt)"
excerpt : "코멘토 SQL 직무 부트캠프, 3주차 과제 진행"

categories :
 - SQL

 tags:
 - [SQL, Redash, group 함수, Sub Query,  sql 부트캠프,
 지표, 데이터분석, 보고서, 가설설정, 문제정의]

---

SQL 3차 과제 - 데이터 분석 보고서 작성(PPT)
===========================================

## ["SQL 입문부터 활용까지"](https://comento.kr/edu/learn/ITSW/%EB%8D%B0%EC%9D%B4%ED%84%B0-G546 )


코멘토 SQL 직무 부트캠프 과정에서 진행하는 3주차 제출본입니다!

<br/>  

## 1) 문제 정의 

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/UEOpX3K48b6gleUi8tFrFs7Ngs4.jpg">

도시 별 배송 비용, 결제 수단 파악 x  
회사 별 주문 개수 파악 x  

<br/>


## 2) 가설 설정

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/qrY5m1Fs9NLOEA0UmBUIVo12S3k.jpg">

<br/>

## 3) 지표 선정

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/Hzc0EXRLYr9H3nRRTcugUtUVriE.jpg">

<br/>

## 4-1) 분석 및 결론 

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/eNFnHa51PheRDFd_1vnK38fpfrE.jpg">

employee_id로 employees 테이블과 orders 테이블 LEFT 조인!!  
'도시'로 그룹화 -> 평균 배송비, 총 배송 횟수, 총 배송비 합계 산출  
평균 배송비 내림차순 정렬 !!  

<br/>

## 4-1) 분석 및 결론

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/KICt37xeMV4Vv6e5GT7lkR9dk4E.jpg">

### Category가 4개로 적으므로 Pie chart를 이용하여 한 눈에 들어오게 표현  

<br/>

## 4-2) 분석 및 결론

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/HZadro-gUSaWxKFeIHW45sA1Mq4.jpg">

employee_id로 employees 테이블과 orders 테이블 LEFT JOIN !!    
결제 수단이 Null값인 row 제거    
도시 -> 결제 수단 순서로 그룹화     
도시, 지불 수단, 결제 횟수 산출       
'결제 횟수' 기준으로 내림차순   

<br/>

## 4-2) 분석 및 결론

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/ogxDDIr8UfPKh-fiomOIw-bA2Ss.jpg">

x -> 도시(그룹화), y: 결제 횟수  
막대 그래프로 도시 별 '결제 수단' 차이를 표현  

<br/>

## 4-2) 분석 및 결론

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/8lHZV1_vyIzEyQjdC_CpndXZoIE.jpg">

x -> 도시(그룹화), y -> 결제 횟수  
막대 그래프(Stacking)로 도시 별 '총 결제 횟수'를 표현  

<br/>

## 4-3) 분석 및 결론 

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/q7LdTySBHluc9WWHJOtopp9hnDk.jpg">

purchase_order_id와 supplier_id를 기준으로 LEFT 조인 2번  
회사로 그룹화 -> 주문량, 평균 재고량, 총 재고량 산출  

<br/>

## 4-3) 분석 및 결론

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/Ki85A69THnESFvvrRiTnnuhXSq0.jpg">

x -> 회사, Y -> 주문 횟수  
line graph로 회사 별 주문 횟수 차이 표현  

<br/>

## 4-3) 분석 및 결론

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/sylhznNUYvasKsMfqcv6__rVre8.jpg">

x -> 회사, y -> 주문 횟수  
막대 그래프로 회사 별 주문 횟수 차이 표현

<br/>


## 오늘의 인사이트

1) 지표를 만드는게 생각보다 쉽지 않다  
-> 목표 도메인 분야의 핵심 지표 및 지표 산출 과정을 확인하자  

2) RDB가 서로 복잡하게 얽혀있는 경우가 많다  
-> SQL로 데이터 추출하는 연습을 많이하고, DB에 대해 더 공부하자  

3) Redash를 통한 시각화는 간편하지만, 한계점이 뚜렷하다  
-> 내가 원하는 디테일한 부분들을 조정할 수 가 없다.  
 So, I realize that why to use phython to data analysis   


