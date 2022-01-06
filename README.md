# Analysis on Programming Books in South Korea

![image](https://user-images.githubusercontent.com/68809022/148406478-775e525a-43e1-4c16-9baa-01e4395158b1.png)

</br>
</br>


## 프로젝트 목적

### 1. **데이터 수집**
  + [Naver Books API](https://developers.naver.com/docs/search/book/) 사용하여 Naver Books 데이터 수집
  <p align = "center">
    <img src = "https://user-images.githubusercontent.com/68809022/148415329-2f3e8c03-fcb5-4f81-8e0b-a0e6653d94cd.png" width = "70%">
  </p>

  + **웹크롤링(Beautifulsoup) 이용**하여 책 페이지 수 데이터 수집

</br>
</br>

### 2. **[TIOBE Index 기준 프로그래밍 언어](https://www.tiobe.com/tiobe-index/) 인기도와 국내 출판사에서 발행된 프로그래밍 언어 도서간의 연관성 분석**

<p align = "center">
  <img src = "https://user-images.githubusercontent.com/68809022/148414896-dde48cfb-af8e-453e-af5b-af7b2977c458.png" width = "85%">
</p>

</br>
</br>

### 3. 데이터 분석 시각화

</br>
</br>

----
## 프로젝트 결과

#### TIOBE INDEX : 2010 - 2019년 프로그래밍 언어 사용량 변화
<p align = "center">
  <img src = "https://user-images.githubusercontent.com/68809022/148413642-a13b4ab4-b488-4153-a701-c6f56e1171e1.gif" width = "60%">
</p>


### 1. 국내에서 2016년 AlphaGo 등장 후, AI에 대한 관심이 높아지면서 파이썬 언어의 대한 츨판량이 압도적으로 증가하였다. 
![image](https://user-images.githubusercontent.com/68809022/148417241-1e316d00-fd7c-45ea-9bd3-66279ea5897b.png)

(수정 중..)

## 프로젝트 과정
----
### 데이터 수집
#### 1.  [Naver Books API 사용](https://developers.naver.com/docs/search/book/)


#### 데이터 전처리

#### EDA 및 시각화

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
|string|string|int|int|float|string|float|string|string|int|
