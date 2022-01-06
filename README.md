# Analysis on Programming Books in South Korea

![image](https://user-images.githubusercontent.com/68809022/148406478-775e525a-43e1-4c16-9baa-01e4395158b1.png)

</br>

----

</br>
</br>

<p align="center">
  <img src = "https://user-images.githubusercontent.com/68809022/148406629-9fe30eb2-fc44-4989-afc5-8607037e620f.png" width = "70%">
</p>


## 프로젝트 목적
----
1. 데이터 수집
  + NAVER API 사용하여 책 정보 데이터 수집
  + Beautifulsoup 사용하여 책 페이지 수 데이터 수집
2. 프로그래밍 언어별 인기도와 책 출판 사이의 연관성 확인
3. 국내 프로그래밍 언어 관련 출판 책 데이터의 상관관계 파악


## 프로젝트 결과[분석]
----
<p align = "center">
  <img src = "https://user-images.githubusercontent.com/68809022/148413642-a13b4ab4-b488-4153-a701-c6f56e1171e1.gif" width = "70%">
</p>



### 1. 국내에서 2016년 AlphaGo 등장 후, AI에 대한 관심이 높아지면서 파이썬 언어의 대한 관심도가 높아졌다 

## 프로젝트 과정
----
### 데이터 수집
#### 1.  [Naver Books API 사용](https://developers.naver.com/docs/search/book/)


### 데이터 전처리

### EDA 및 시각화

## 프로젝트 한계 및 보완점
----
+ Naver API 무료버전은 검색어 1개 당 1천개의 검색결과로 제한되어 있어서 사용자가 어떤 단어로 검색하냐에 따라 결과 값이 다를 수 있었다. 그래서 각 프로그래밍 언어 별 최대한 다양한 방식의 이름으로 검색을 수행하여 데이터를 수집하였다.

## Index
----

```python
# 한꺼번에 처리하기 위해 리스트로 저장
data_raw = [data_python, data_c, data_java, data_cpp, data_csharp, data_vb, data_js, data_sql, data_php, data_r]
```

|책제목	|작가	|가격	|할인가격	|ISBN|	출판사|	출판일	|link|	언어	|페이지수|
|------|---|---|---|---|---|---|---|---|---|
