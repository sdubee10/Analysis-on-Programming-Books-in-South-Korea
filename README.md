# Analysis on Programming Books in South Korea

![image](https://user-images.githubusercontent.com/68809022/148406478-775e525a-43e1-4c16-9baa-01e4395158b1.png)

</br>
</br>


## 🖥 프로젝트 목적

#### 1. **데이터 수집**
  + [Naver Books API](https://developers.naver.com/docs/search/book/) 사용하여 Naver Books 데이터 수집
  <p align = "center">
    <img src = "https://user-images.githubusercontent.com/68809022/148415329-2f3e8c03-fcb5-4f81-8e0b-a0e6653d94cd.png" width = "70%">
  </p>

  + **웹크롤링(Beautifulsoup) 이용**하여 책 페이지 수 데이터 수집

#### 2. **[TIOBE Index 기준 프로그래밍 언어](https://www.tiobe.com/tiobe-index/) 인기도와 국내 출판사에서 발행된 프로그래밍 언어 도서간의 연관성 분석**

<p align = "center">
  <img src = "https://user-images.githubusercontent.com/68809022/148414896-dde48cfb-af8e-453e-af5b-af7b2977c458.png" width = "85%">
</p>

#### 3. 데이터 분석 시각화
  + matplotlib
  + plotly express

</br>

----
## 📝 프로젝트 결과

#### TIOBE INDEX : 2010 - 2019년 프로그래밍 언어 사용량 변화
<p align = "center">
  <img src = "https://user-images.githubusercontent.com/68809022/148413642-a13b4ab4-b488-4153-a701-c6f56e1171e1.gif" width = "60%">
</p>


+ 2016년 AlphaGo의 등장으로 인해 파이썬 언어에 관한 관심이 급 상승하였으며, 파이썬 언어와 관련된 도서 발행 수가 크게 증가함.
+ 책 가격이 코로나 이전(2017-2019)와 이후(2020-2021)에 큰 차이가 없음.
+ 인공지능, 데이터 분석에 대한 수요가 많은 만큼 대부분의 출판사에서 Python과 관련된 책들을 많이 발행함.

## 프로젝트 과정
### 1. 데이터 수집

##### 1). Naver Books API에 검색어로 입력할 문구 설정

``` python
# 언어별 검색할 문구

language_dict ={
    "Python": ["Python", "python", "Python 언어", "파이썬 언어", "파이선", "파이썬 프로그래밍"],
    "C" : ["C language", "c language", "C 언어", "C 프로그래밍"],
    "JAVA" : ["JAVA 언어", "JAVA 프로그래밍", "자바 프로그래밍"],
    "C++" : ["c++ 언어", "C++ 프로그래밍", "c++ language", "C++ language","c++ programing"],
    "C#" : ["C#", "C# 언어", "C# 프로그래밍", "c# language", "C# programming"],
    "Visual Basic" : ["Visual Basic", "Visual Basic 프로그래밍", "비쥬얼베이직", "Visual Basic Programming"],
    "JavaScript" : ["JavaScript", "javascript 언어", "javascript language", "JavaScript 프로그래밍", "자바 스크립트"],
    "SQL" : ["SQL언어","SQL 언어", "SQL 프로그래밍", "SQL programming", "SQL language"],
    "PHP" : ["php언어","php 언어", "PHP 프로그래밍", "php language", "php programming"],
    "R" : ["R언어", "R 언어", "R 프로그래밍", "R language", "R programming"]            
}
```
##### 2). [Naver Books API 사용](https://developers.naver.com/docs/search/book/) 네이버 Books API 사용:
  
    API를 사용하여 책 제목, 작가, 가격, 할인가격, 책 고유번호(ISBN), 출판사, 출판일, 책 웹페이지 링크 정보 수집

##### 3). 수집된 '책 웹페이지 링크'에 접속하여 BeautifulSoup으로 책 페이지수 수집:

<p align="center">
  <img src = "https://user-images.githubusercontent.com/68809022/148487336-c873face-63b0-4bcd-a974-9345184814cc.png" width = "70%">
</p>

##### 4). 결과 확인 (임의로 python 관련 데이터 선택):
![image](https://user-images.githubusercontent.com/68809022/148487653-ba02691b-241c-42d1-bb59-a40a1d0c7698.png)

### 2. 데이터 전처리

  + 결측치 처리
  + 같은 프로그래밍 언어에서 찾아진 중복된 ISBN 값 제거
  + 출판일 YYYYDD 형식으로 처리 후, 2010년 이후에 출판 책으로 필터링 적용
  + 페이지수 숫자 6자리 이하인 것만 필터링 적용

**결과 : 23,963개의 데이터에서 전 처리후 22,095개로 1868개 줄어듦**

### 3. EDA 및 시각화

#### 1) Naver Books API로 검색된 전체 프로그래밍 언어 책 발행 수
![image](https://user-images.githubusercontent.com/68809022/148491471-d04f02d1-4ddf-4ebb-b294-de7e4b7ff18e.png)

+ Naver Books API에서 검색된 전체적으로 발행 된 도서 수를 살펴보면, 통계 및 데이터 분석에 많이 사용되는 R과 SQL관련 도서 발행 수가 많으며, PHP 언어 관련 도서 개수가 가장 적음


#### 2). 2010-2020년 프로그래밍 언어별 발행부 수 변화
![image](https://user-images.githubusercontent.com/68809022/148490496-14ce484d-b9d2-46cc-9002-6444ee682701.png)

+ 2018년도 이후, 파이썬과 관련된 도서 발행 수가 급격히 증가함
+ 2018년도 이후, 데이터 분석에 필수적인 SQL 언어 관련 책 발행 수 또한 증가함

#### 3). 출판사 조사
![image](https://user-images.githubusercontent.com/68809022/148492185-0f24917a-1332-4f24-9364-0bf152909d43.png)

+ 에이콘출판사, 한빛미디어가 순으로 프로그래밍과 관련된 가장 많은 도서를 발행 하였음.

#### 4). 2017-2019 vs. 2020-2021 에 발행된 프로그래밍 언어 도서 비교
![image](https://user-images.githubusercontent.com/68809022/148492997-2618f74a-be57-4841-9de5-ca804e322b36.png)
+ AI, 딥러닝, 머신러닝의 등장으로 Python에 관한 대중들의 관심도가 높아졌기에 Python 언어와 관련된 도서들이 많이 출간된 것으로 보인다.
+ AI의 등장과 함께 빅데이터 분야 역시 중요도가 높아지고 있다. 빅데이터를 잘 다루기 위해선 기본적인 SQL지식이 필수적이다. 이러한 이유로 SQL관련 책 도서가 Python 다음으로 많이 출판된 것으로 짐작된다.
+ Visual Basic과 PHP언어 출판물의 양은 Python에 비해 아주 적게 출판되었다는 것을 확인 할 수 있다. 

#### 5). 프로그래밍 언어 도서 가격
![image](https://user-images.githubusercontent.com/68809022/148496330-efa5073c-9f2e-4877-b90b-8ec843db7c54.png)
+ 대부분의 경우 2~4만원 사이의 가격대를 형성하고 있는 것을 확인할 수 있다.
+ 파이썬 언어와 SQL언어의 경우, 높은 가격(8~10만원)사이에서 outlier가 존재하는 것을 알 수 있다.
+ Outlier들을 검색해본 결과, 세트 구성으로 판매되는 책 이거나, 해외 논문, 혹은 연구 보고서라는 이유로 높은 가격으로 측정 되어 있었다.


## 프로젝트 한계 및 보완점
+ Naver API 무료버전은 검색어 1개 당 1천개의 검색결과로 제한되어 있어서 사용자가 어떤 단어로 검색하냐에 따라 결과 값이 다를 수 있었다. 그래서 각 프로그래밍 언어 별 최대한 다양한 방식의 이름으로 검색을 수행하여 데이터를 수집하였다.

## Index
데이터 변수 타입 :

|책제목	|작가	|가격	|할인가격	|ISBN|	출판사|	출판일	|link|	언어	|페이지수|
|------|---|---|---|---|---|---|---|---|---|
|string|string|int|int|float|string|float|string|string|int|
