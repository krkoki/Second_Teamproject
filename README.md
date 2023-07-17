# 영화 리뷰 평점 예측 프로젝트

### 수행 기간 : 2023.05.15 - 2023.06.09

## 주제
영화 리뷰를 작성하면 평점을 예측해주는 학습 모델

## 데이터 출처
KOBIS (영화관입장권통합전산망) : ([https://aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=realm&dataSetSn=469](https://www.kobis.or.kr/kobis/business/stat/boxs/findDailyBoxOfficeList.do))
NAVER (영화의 정보, 리뷰 및 평점 크롤링) : (https://www.naver.com/)

## 사용한 언어 및 라이브러리, 프레임워크
#### 언어
<div align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white"/>
  <img src="https://img.shields.io/badge/JavaScript-323330?style=flat-square&logo=javascript&logoColor=F7DF1E"/> 
</div>

#### 데이터베이스
<div align="left">
  <img src="https://img.shields.io/badge/MySQL-005C84?style=flat-square&logo=mysql&logoColor=white"/>
</div>

#### 프레임워크
<div align="left">
  <img src="https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=green"/>
  <img src="https://img.shields.io/badge/Bootstrap-563D7C?style=flat-square&logo=bootstrap&logoColor=white"/>
  <img src="https://img.shields.io/badge/conda-342B029.svg?&style=flat-square&logo=anaconda&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=flat-square&logo=Jupyter&logoColor=white"/>
</div>

#### 라이브러리
<div align="left">
  <img src="https://img.shields.io/badge/Keras-FF0000?style=flat-square&logo=keras&logoColor=white"/>
</div>
<div align="left">
  <img src="https://img.shields.io/badge/Pandas-2C2D72?style=flat-square&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Numpy-777BB4?style=flat-square&logo=numpy&logoColor=white"/>
  <img src="https://img.shields.io/badge/json-5E5C5C?style=flat-square&logo=json&logoColor=white"/>
</div>

## 순서
#### 1. 모델 학습용 데이터 수집 및 처리
##### KOBIS (영화관입장권통합전산망)
  - 2013 ~ 2023년 10년동안 상영된 영화 목록
  - 개봉일, 매출액, 관객수, 스크린수, 상영횟수
  - 총 11,283편의 영화
##### NAVER (네이버 영화 리뷰 크롤링)
  - KOBIS에서 추출한 영화목록으로 네이버 크롤링
  - 개봉일, 장르, 국가, 상영시간, 줄거리, 감독, 배우
  - 총 1,137,995개의 리뷰 및 평점


#### 2. 수집한 데이터 전처리
##### KOBIS (영화관입장권통합전산망)
  - KOBIS에서 수집한 10년치 데이터에서 데이터베이스를 위한 영화ID 컬럼을 만들고 중복값을 제거한 11,283편의 영화 목록을 추려냄.
##### NAVER (네이버 영화 리뷰 크롤링)
  - 11,283편의 영화목록으로 네이버 홈페이지 크롤링하여 리뷰가 없는 영화를 제외한 8200편의 영화화 리뷰 및 평점을 수집.
  > 총 1,183,849개의 리뷰 및 평점 수집

#### 3. 평점 예측 모델 학습
  - RNN 알고리즘
  - CNN 알고리즘

| `RNN` | `CNN` |
| --- | --- |
|![RNN](https://github.com/krkoki/Second_Teamproject/assets/121409518/604d191a-eef9-491b-9202-3ee84e6171f0)|![CNN](https://github.com/krkoki/Second_Teamproject/assets/121409518/10b26fe9-543b-4fe7-97c4-b0644d1dbe4d)|
|![RNN2](https://github.com/krkoki/Second_Teamproject/assets/121409518/ebd72cc5-eccd-4c6c-9332-703b3627554f)|![CNN2](https://github.com/krkoki/Second_Teamproject/assets/121409518/231d2bae-4e1c-4b79-ae69-4e56ce9b7a5d)|

#### 4. Django를 이용한 서비스 구현
  - 서비스 구현 담당 장민수 님 개인사정으로 인한 구현 중지

## 개선사항
- 더 질 높은 리뷰와 평점 데이터 수집
- 불용어사전 및 형태소를 더 세밀하게 수정
- 최적의 파라미터와 레이어를 탐색하여 모델을 보완
- 모델을 보완하여 오차가 적거나 (<1.0) 정확도가 높은(>90%) 모델 생성
- CPU 대신 GPU 사용 고려 & 더 좋은 사양의 PC 사용 고려
- 신규 개봉 영화를 자동으로 데이터베이스에 저장할 수 있도록 구현
- 카테고리별(장르, 배우, 감독 등등) 사용자 선호도 바탕 영화 추천

##### 더 자세한 사항 : [발표자료 링크](https://docs.google.com/presentation/d/1xUBhXUTt6GjCk_n3XkgNg3UWLbuz3igQvk4_vkmEw-0/edit#slide=id.g22de6e763c5_1_50)
