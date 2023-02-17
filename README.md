# 서울 시민 데이터를 활용한 도시문제 해결 경진대회

## 대회 개요
  - https://dacon.io/competitions/official/235966/overview/description
  - 서울 시민 데이터를 활용한 도시문제 해결 경진대회
  
## 대회 기간
  - 후 순위 참가자(추가 참가자)팀으로 배정받아 10월 3일부터 10월 14일까지 참여
  
### 주제
  - 서울시에서 제공하는 서비스인 킥보드로 인하여 사회문제가 발생하였다.
  - 수거비용 및 불법 주정차한 킥보드들 때문에 문제가 되고 있다.
    - https://mediahub.seoul.go.kr/archives/2004079
    - http://www.newskr.kr/news/articleView.html?idxno=75768
    - https://www.segye.com/newsView/20220923509500
    
### 활용 데이터
  1. 자치구단위 서울 생활인구 데이터 : https://data.seoul.go.kr/dataList/OA-15379/S/1/datasetView.do

    서울시 구별로 인구수를 확인할 수 있다. (일별로 집계되어있음)
    분석에는 주,야간 인구수와 최대 및 최소 인구수만 사용

  2. 서울시 전동킥보드 견인 현황 :https://data.seoul.go.kr/dataList/OA-15379/S/1/datasetView.do

    서울시 자치구 별로 어떠한 유형대로 전동 킥보드를 수거하였는지 집계
    전동 킥보드를 수거한 날짜 데이터


### 데이터 분석 방법
  
  - 서울시 제공 데이터들을 통하여 가장 많이 발생한 지역구 확인
  - 데이터 크롤링을 통하여 위치 데이터를 지도에 표시하기 위한 위, 경도 데이터로 변환
  - 유동인구 데이터와 킥보드 견인 데이터를 활용한 예측 모델 생성
  - RandomForest를 사용하여 각 발생할 킥보드 개수 예측(회귀)
  ![decistion-tree](https://user-images.githubusercontent.com/110336043/219580224-50340593-e810-444a-a5dd-9ed2f12b2294.png)

  - RandomForest인 Tree계열의 특징인 feature importance를 확인하여 어떠한 feature가 가장 큰 요인이였는지 확인
  - folium을 활용하여 견인 킥보드 지도에 표시
  
### 개선사항
  
  - 대회 기간이 짧아 예측 모델 까지 밖에 만들지 못하였음
  - 결국 도시문제를 해결해야하기 때문에 최적화 하는 방안이 필요
  - 위의 모델과 추가 데이터 수집 및 여러 방식을 통하여 최적화하는 알고리즘 개발 필요
