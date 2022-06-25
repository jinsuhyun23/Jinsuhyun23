---
title : "SQL 스터디 1차 5문제 풀이"
excerpt : "SQL 스터디 문제 풀이"

categories :
 - SQL

 tags:
 - [SQL, 스터디, 5문제, 풀이, 모두의 SQL, 관계 차수, 관계 선택 사양, LEFT JOIN, LEFT OUTER JOIN, 집합 연산자]

---

< SQL 스터디 > 1차 5문제 풀이 
============================

## 1번 문제
### first_name이 Georgi 인 직원들이 받은 가장 높은 연봉을 높은 순서로 조회하세요.   
### (조회컬럼 emp_no,  last_name, salary)  

<pre>
<code>
SELECT e.emp_no 직원번호, last_name 마지막이름, salary 연봉
FROM employees e LEFT JOIN salaries s ON e.emp_no = s.emp_no
WHERE first_name = 'Georgi' # 성이 Georgi인 고객명
ORDER BY salary DESC
</pre>
</code>

<img src = "https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/cOEz_QE5M7L4-0SjDdngz7F_kfI.jpg">

<br/>

## 2번 문제
### 현재 마케팅 부서에서 근무중인 직원을 조회하세요 (조회컬럼 emp_no, first_name, last_name) 

<pre>
<code>
SELECT e.emp_no, e.first_name, e.last_name
FROM employees e LEFT JOIN dept_emp de ON e.emp_no = de.emp_no
		 LEFT JOIN departments d ON de.dept_no = d.dept_no
WHERE dept_name ='Marketing'
</pre>
</code>

<img src = "https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/EjHc4fGto4jBvgO2ThUHB6Iqoe4.jpg">

<br/>

## 3번 문제
### 생일이 6월인 여성 직원을 부서명 기준 오름차순으로 정렬하세요  

<pre>
<code>
SELECT e.emp_no, dept_name, MONTH(birth_date)
FROM employees e LEFT JOIN dept_emp de ON e.emp_no = de.emp_no
		 LEFT JOIN departments d ON de.dept_no = d.dept_no
WHERE e.gender = 'F' AND MONTH(birth_date) ='6' -- 생일이 6월인 여성 직원
ORDER BY dept_name ASC -- 부서명 기준
</pre>
</code>

<img src = "https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/vnxQ1ACvz5ed-pDwlUgmSqOJytE.jpg">

<br/>

## 4번 문제
### production 부서의 직원들을 누적급여 상위 50명을 조회하세요.  

<pre>
<code>
SELECT e.emp_no, SUM(salary) 누적급여
FROM employees e LEFT JOIN dept_emp de ON e.emp_no = de.emp_no
		 LEFT JOIN salaries s ON de.emp_no = s.emp_no
		 LEFT JOIN departments d ON de.dept_no = d.dept_no
WHERE d.dept_name ='Production' -- prduction 부서 직원
GROUP BY e.emp_no
ORDER BY SUM(salary) DESC
LIMIT 0, 50
</pre>
</code>

<img src = "https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/lfu0Z3Vtb35iF8P3aAklECsWFAA.jpg">

<br/>

## 5번 문제
### 자기생일에 고용된 사람중 first_name이 A로 시작하는 사람을 조회하세요

<pre>
<code>
SELECT first_name, last_name, birth_date, from_date
FROM employees e LEFT JOIN titles t ON e.emp_no = t.emp_no
WHERE first_name LIKE 'A%'
AND SUBSTR(from_date,6,5) = SUBSTR(birth_date, 6,5)
</pre>
</code>

<img src = "https://img1.daumcdn.net/thumb/R1280x0/?fname=http://t1.daumcdn.net/brunch/service/user/e0Ty/image/ZT6fEAP1tufErG8IBSaILaGDqVk.jpg">

<br/>