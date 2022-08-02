---
title : "Proframe < FML 조회 프로그램 >"
excerpt : "Proframe, C언어, FML 방식"

categories :
 - IT Tool 공부

 tags:
 - [증권사, KB, C언어, 프로그래밍, 코딩,
 개발자, IT, 디지털
 인턴, 전환형, 채용형 인턴]
---

Proframe < FML 조회 프로그램 >
===========================================

## FML 조회 프로그램  
> '반복되는' 출력 데이터를 조회하는 프로그램    
> '전문 표준 크기'에 따라 1회 전송 건수 제한 존재    
>> 조회 성능이 좋고(조회 시간 적음), 특정 시점의 데이터 조회시 사용 권장  

- O-FML : O(Only, Other) / F(First) / M(Middle) / L(Last)  

- 예시 : 1회 송신시 최대 30건 전송 가능할 경우  
1) 15건 -> O : 15건 / 총 1회 전송
2) 40건 -> F : 30건, L : 10건 / 총 2회 전송
3) 100건 -> F : 30건, M : 30건, M : 30건, L : 10건 / 총 4회 전송  

<br/>

### 작동 방식  
[ 첫 호출 ] 송신 - 수신(F or O), 수신(M), 수신(M), ..., 수신(L)  
> '다음키' 누를 때마다 < 송신 - 수신 > 반복하는 것과 차이  

최초 조회 시점 기준 리스트  

타임 아웃 : 첫 호출 - 마지막 수신까지 적용  

<br/>

### 주요 가이드 내용  
1) SM(소프트웨어 모듈)에 별도 셋팅 없음  
> FETCH LOOP 내에서 메시지 처리를 해주는 것이 핵심  

2) 주요 FUNCTION 및 변수     
2-1) FML 셋팅    
    -> SetDataHdrPosition(DHDR_FML_FIRST)  
    -> SetDataHdrPosition(DHDR_FML_MIDEUM)  
    -> SetDataHdrPosition(DHDR_FML_LAST)  
    -> SetDataHdrPosition(DHDR_FML_OTHER)  

    2-2) 전문 사이즈 셋팅  
    -> BA_FML_MSG_REAL_SZ("TR명", OUTPUT)  

    2-3) 실제 사이즈 전문 전송  
    -> pfmSendPartialOutput("TR명", OUTPUT)

<br/>

### 장애 예방 포인트  
1) F, M 전송 후 LAST가 전송되지 않을 때, TR은 종료했지만 화면은 무한정 기다리다 오류 발생  
-> LAST 셋팅 확인  

2) 속도가 느린 DBIO 혹은 FETECH LOOP 안에서 SM을 호출하는 경우  
-> 건수가 많아지면, M 단계에서 타임하는 경우 존재  

3) FML 셋팅에 주의 필요  
-> 클라이언트 화면에서는 TR의 

<br/>  

### ORACLE 내 커서(Cursor) 및 FETCH
> 커서 : 쿼리문에 의하여 반환되는 결과값들을 저장하는 메모리 공간  
> Fetch : 커서에서 원하는 결과값을 추출하는 것  

- 여러 복수 행의 결과를 '행 단위'로 처리하기 위해 Cursor를 사용  

<br/>  

### 커서의 정확한 정의  
> SQL Plus 내에서 사용자가 실행한 SQL문의 단위    

- 오라클에서 수행한 모든 쿼리문은 커서 단위로 처리합니다  




