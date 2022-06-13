---
title : "pd.read_csv를 통한 파일 읽기(오류 해결 포함)"
excerpt : "판다스, 파이썬, read_csv"

categories :
 - Phython

 tags:
 - [Phython, pandas, pd.read_csv, 오류, 경로, 작업 폴더]
---

pd.read_csv를 통한 파일 읽기(오류 해결 포함)
===========

## 1) 내 작업 폴더 위치 확인  
### - 작업 폴더 위치에 Load할 데이터를 놓아야 한다!
### - 아닐 경우 "해당 디렉토리에 파일이 없다고 나옴"  

<img src = "https://blog.kakaocdn.net/dn/b4isSi/btqBtXnABXw/YLkKkVkhYdKTmWl6pWjEg0/img.png">

<br/>

## 2) 데이터 주소 확인
### - 파일 경로 확인(마우스 우클릭 - 속성 - 주소) 
### - 작업 폴더 위치로 옮김!

<br/>

## 3) pd_read.csv("파일경로/파일명.확장자")  
### - 파일 경로에 'money 기호' 대신 '/' 1번 또는 '\\' 2번 넣어준다  
### - \로 입력할 경우 유니코드로 인식하여 오류 발생  

### 참고 링크 :   https://garlicsnackbar.tistory.com/3    
  
<br/>  

## - Data Load 코드 예시
<img src = "https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/LPA7nyEAu86bsQrFRaNlb3DhHSw.jpg">  