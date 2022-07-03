---
title : "Pandas, Seaborn 시각화 기본 설정"
excerpt : "판다스, 파이썬, Seaborn"

categories :
 - Phython

 tags:
 - [Phython, pandas, pd.read_csv, 시각화, 경로, Seaborn]
---

Pandas, Seaborn 시각화 기본 설정
===========


## Pandas Columns, Rows 기본 설정
<pre>
<code>

# rows 500 개수
pd.set_option('display.max_rows', 500)

# columns 개수 및 너비
pd.set_option('display.max_columns', 500)
pd.set_option('display.width', 1000)

</pre>
</code>

<br/>

## 시각화를 위한 그래프 및 폰트 "전역 설정"
<pre>
<code>
# 주피터 노트북 내 그래프를 바로 그리기 위한 설정
%matplotlib inline

# unicode minus를 사용하지 않기 위한 설정
plt.rcParams['axes.unicode_minus'] = False 
plt.rcParams['font.family'] = 'NanumGothic' # 글자체 설정  
plt.rcParams['font.size'] = 13  # 폰트 크기 설정  

# figsize 전역으로 설정
plt.rcParams['figure.figsize'] = (9,4)  ## 그래프 사이즈 설정  

</pre>
</code>

<br/>

## Seaborn Palette 설정 (범주형, 수치형)
<pre>
<code>
# sns.set_palette("dark") 어두운 기본 색상 지정

# 범주형 변수 색상
categorical_color = sns.color_palette("Paired", 9) # 9개 색상  

# 수치형 변수 색상1 (값이 높아질 수록 진해짐)
Sequential_color = sns.color_palette("RdPu", 10) # 10개 색상  

# 수치형 변수 색상2 (양 극단의 색상이 선명해짐)
Diverging = sns.color_palette("RdBu", 10) # 10개 색상  

</pre>
</code>

<br/>

### 참고 블로그 : matplotlib/seaborn으로 시각화할 때 한글 폰트 깨짐현상 해결방법    
https://teddylee777.github.io/visualization/matplotlib-%EC%8B%9C%EA%B0%81%ED%99%94-%ED%95%9C%EA%B8%80%ED%8F%B0%ED%8A%B8%EC%A0%81%EC%9A%A9


### 참고 블로그 : [seaborn] color 팔레트 선택하기    
https://hleecaster.com/python-seaborn-color/
