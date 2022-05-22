---
title : "SQL 1차 과제 - Group by와 join 활용"
excerpt : "SQL 직무 부트캠프, 1주차 과제 진행"

categories :
 - SQL

 tags:
 - [SQL, Redash, group 함수, inner join,  sql 부트캠프]

---

SQL 1차 과제 - Group by와 join 활용
======================


["SQL 입문부터 활용까지"](https://comento.kr/edu/learn/ITSW/%EB%8D%B0%EC%9D%B4%ED%84%B0-G546 )


코멘토 SQL 직무 부트캠프 과정에서 진행하는 1주차 과제 리뷰입니다!  
혼자서 문제를 풀고 나서 답안을 확인하시길 바랍니다!

<br/>  

### 1) Country 별로 ContactName이 ‘A’로 시작하는 Customer의 숫자를 세는 쿼리를 작성  

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/28gYZdQwnkNwiWPIc-QEoIqLk1U.jpg">   


*  @별로 -> GROUP BY 함수 사용
* @로 시작하는 -> WHERE LIKE '@%'  
ex) B로 끝나는 -> WHERE LIKE '%B'
* @의 숫자를 세는 -> 집계함수 Count 사용  

<br/>

### 2) Customer 별로 Order한 Product의 총 Quantity를 세는 쿼리를 작성하세요.

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/EGPWVjuO8KCXujMd2Z4Ejw_b47A.jpg">

* customer 별로 -> GROUP BY a.customerid
* 주문한 제품의 총 Qunatity ->  
 FROM orders a left join orderdetails b on a.orderid = b.orderid  

customer 속성은 order 테이블 / quantity 속성은 Orderdetails 테이블  
즉, customer 테이블 기준 left join하여 총 quantity 계산  
  
<br/>

### 3) 년월별, Employee별로 Product를 몇 개씩 판매했는지를 표시하는 쿼리를 작성하세요.

<img src="https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/OX9M3twM3TlwE7XeCQrrFsCXGks.jpg">

* 년월별, Employee 별로 -> GROUP BY SUBSTR(a.orderdate,1,7), a.employeeid  
orderdate가 원래 'YYYY-MM-DD' 형태라 SUBSTR 함수로 년월 형태로 변환  
* Product를 몇 개씩 판매했는지 -> SUM(b.quantity)  

<br/>

orderdate 속성은 orders 테이블 / quantity 속성은 orderdetails 테이블  
즉, customer 테이블 기준 left join하여 총 quantity 계산

<br/>

## 오늘의 인사이트
### 1)  GROUP BY 절에 사용한 속성을 SELECT 절에 가장 먼저 써줘야 함  
ex) GROUP BY A1(속성), B1(속성) -> SELECT A1, B1  
WHY ?  결과물을 보고 어떤 기준으로 그룹화했는지 판단해야 하므로!  

<br/>

### 2) 두 테이블에 모두 존재하는 속성으로 Join 해야 함
ex) orderid가 orders, orderdetails 모든 테이블에 있는 경우 -> a.orderid = b.orderid

<br/>

### 3) SUBSTR(값, 시작 index, 추출 index 개수)
ex) ABCDE 중 BCD 추출 -> SUBSTR(ABC, 2, 3)