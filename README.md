# Analysis on Programming Books in South Korea
+ 프로젝트 수행일지: 2021.10.21
+ 작성자 : 강승완

국내 프로그래밍 관련 책 출판에 대한 분석

<p align = "center">
  <img src = "https://user-images.githubusercontent.com/68809022/147713250-3828d43b-c616-46dd-a543-8e2fb1b5a0f0.png" width="100%" height="100%">
</p>

## 프로젝트 목적
----
1. 데이터 수집
2. 프로그래밍 언어별 인기도와 책 출판 사이의 연관성 확인
3. 국내 프로그래밍 언어 관련 출판 책 데이터의 상관관계 파악


## 프로젝트 결과[분석]
----

## 프로젝트 과정
----
### 데이터 수집

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
