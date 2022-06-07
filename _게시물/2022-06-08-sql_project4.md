---
title : "SQL 4차 과제 - 대시보드 작성"
excerpt : "코멘토 SQL 직무 부트캠프, 4주차 과제 진행"

categories :
 - SQL

 tags:
 - [SQL, Redash, group 함수, Sub Query,  sql 부트캠프,
 지표, 데이터분석, 보고서, 대시보드, 가설설정, 문제정의]

---

SQL 4차 과제 - 대시보드 작성(for redash)
===========================================

## ["SQL 입문부터 활용까지"](https://comento.kr/edu/learn/ITSW/%EB%8D%B0%EC%9D%B4%ED%84%B0-G546 )


코멘토 SQL 직무 부트캠프 과정에서 진행하는 4주차 제출본입니다!

<br/>  

# 배송비용 추적 대시보드

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/aMlCe1pUOjZUJAyrsoHGnC91G8Y.jpg">

> 배송 회사 / 배송 일자 / 착불 도시 / 배송 유형   
> 배송 일자 파악 !! 

Table에 데이터가 충분하지 않고, Null값을 많이 포함하고 있음.  
그나마 데이터가 많은 orders 테이블을 활용하여 '배송비용'을 추적하는 대시보드 구성!!  

<br/>


## 1) 배송회사 별 배송비용
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/V4PEf08kIFL7IFBCI0mjFeGrUpg.jpg">
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/_QCIZ0e5-aenBkZxALQ1AFAZbC0.jpg">

> 평균 배송비용이 가장 비싼/저렴한 회사 -> Company B / Comapny C 
>> B회사가 합계 배송비도 압도적으로 1위(배송 건수도 가장 많은 것을 의미)
>> C회사는 평균 배송비는 낮지만 매출은 2위(배송 건수가 A회사 보다 많음)
 
> 합계 배송비용이 가장 비싼/저렴한 회사 -> Company B / Company C  
>> B회사는 매출 1위로 평균 배송비용도 높고, 배송 건수도 많은 것을 알 수 있음  
>> A회사는 매출 3위로 평균 배송비용도 낮고, 합계 배송 비용도 낮다

### 인사이트 -> Company B가 시장 내 지배적인 위치를 점하고 있음  

<br/>

## 2) 배송일자 별 배송비용 추이
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/-FfK4c2wxl764wYENdybV7sIS4M.jpg">
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/ekNWwb-R1Pcfowb2psavgCNSNYs.jpg">

> 2006년 1월 ~ 6월 간 평균 배송비용과 합계 배송비용의 추이는 거의 비슷하다
>> 그래프가 거의 동일하나 2006년 4/5/6월에만 합계 배송비가 더욱 높음  
 
> 20016년 1월, 4월, 6월에 배송비용이 증가  
>> 다른 일자에 비해 배송비용이 증가한 이유를 파악해야 함

### 인사이트 -> 1, 4, 6월에 배송비용 증가 원인 분석 및 일시적 Event인지 확인  

<br/>

## 3) 착불도시 별 배송비용
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/6omgrgEBOsfm7REYeEToNbf6b7w.jpg">
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/Wf3WNRt8ttYhoZ6zX_khAKmCHGY.jpg">

> Denver와 Lasvegas, Milwaukee가 배송비 합계 및 평균 배송비가 높음
>> 거주 인원 대비 주문 건수도 반영하여, 배송을 많이 시키는 지역인지 확인 필요  
 
> Memphis, Miami, portland, sait lake city는 배송비용이 평균 합계 배송비가 중간  
>> 평균 배송 비용이 낮아 합계 배송비도 상대적으로 낮은 것으로 보임

### 인사이트 -> 주요 도시(3개)를 위한 별도 마케팅 및 재구매 유도 가능

<br/>

## 4) 결제유형 별 배송비용
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/eMPb6TfofXs0McMBsmKxHSqdBao.jpg">
<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/Bm_XVKAAt2nXdixhbrJ6v5p5lR0.jpg">
 
> 배송비용 결제 시 체크카드와, 신용카드가 90%를 차지한다   
>> 대부분의 결제는 카드로 이뤄지므로, 카드 이용에 대한 혜택이 재구매율 상승으로 연계  

### 인사이트 -> 카드 사용자를 위한 서비스를 특화할 필요가 있음

<br/>
