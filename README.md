[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/g6ZC_OOE)
## FastCampus x Upstage Competetion 2조

## Team

| ![진성준](https://avatars.githubusercontent.com/u/156163982?v=4) | ![김준호](https://avatars.githubusercontent.com/u/156163982?v=4) | ![김하연](https://avatars.githubusercontent.com/u/156163982?v=4) | ![송현지](https://avatars.githubusercontent.com/u/156163982?v=4) | ![엄효범](https://avatars.githubusercontent.com/u/156163982?v=4) | ![정다슬](https://avatars.githubusercontent.com/u/156163982?v=4) |
| :--------------------------------------------------------------: |:-------------------------------------------------------------:| :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
|            [진성준](https://github.com/UpstageAILab)             |            [김준호](https://github.com/UpstageAILab)             |            [김하연](https://github.com/UpstageAILab)             |            [송현지](https://github.com/UpstageAILab)             |            [엄효범](https://github.com/UpstageAILab)             |            [정다슬](https://github.com/UpstageAILab)             |
|                            팀장, 담당 역할                             |                             담당 역할                             |                            담당 역할                             |                            담당 역할                             |                            담당 역할                             |                            담당 역할                             |

## 1. Competiton Info

### Overview

- 서울시 아파트 실거래가 매매 데이터를 기반으로 아파트 가격을 예측하는 대회

### Timeline

- January 15, 2024 - Start Date
- January 26, 2024 - Final submission deadline

### Evaluation

- RMSE

## 2. Components

### Directory

|-- Miniconda3-latest-Linux-x86_64.sh <br>
|-- bus_feature.csv <br>
|-- code <br>
|   |-- baseline_code.ipynb <br>
|   |-- highschoolscore_done.csv <br>
|   |-- outliers_done.csv <br>
|   |-- requirements.txt <br>
|   `-- saved_model.pkl <br>
|-- code.tar <br>
|-- data.tar <br>
|-- sample_submission.csv <br>
|-- subway_feature.csv <br>
|-- test.csv <br>
`-- train.csv <br>

## 3. Data descrption

### Dataset overview

- 주요 데이터셋은 .csv 형태로 제공되며, 목표는 서울시 아파트의 각 시점에서의 거래금액(만원)을 예측하는 것입니다. 학습 데이터에는 1,118,822개의 샘플이 있으며, 52개의 아파트에 대한 변수와 거래시점에 대한 변수가 포함되어 있습니다.  
데이터의 기간은 2007년 1월 1일부터 2023년 6월 30일까지이며, 변수명은 한글로 되어 있어 정보를 쉽게 확인할 수 있습니다. 예시로 시군구, 아파트명, 전용면적(㎡), 건축년도 등이 주어집니다.  
각 변수는 결측치를 가지고 있으며, 교통적인 요소의 영향을 고려하여 추가 데이터로 서울시 지하철역과 버스정류장의 정보가 주어집니다. 이 추가 데이터에는 위도, 경도, 좌표 X와 좌표 Y 등 거리 정보가 포함되어 있어 학습 데이터와 함께 활용할 수 있습니다.

### EDA

- Missing Values  
  연속형 변수의 경우에는 선형보간(Linear interpolation)으로 대체하겠습니다.  
  범주형 변수의 경우에는 'NULL' 이라는 임의의 범주로 대체해주도록 하겠습니다.  
  ![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/96f90362-ee76-4fe2-8180-de61e210efe5)  
  ![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/6665efcf-5a36-4d1c-a377-86f76c36cbcf)

- Outliers  
  ![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/983057bc-eaf2-420b-b81c-be7007c40d5b)  
  ![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/bc9f1df5-d997-4705-b0a5-b61aceaecb60)  

### Feature engineering

- 외부데이터 활용
### 학군 변수
1. **수능 국어수학 영역 백분위 평균:**
2. **가까운 고등학교 (상위 3개)**
3. **3개 학교의 거리 평균**
4. **3개 학교의 백분위 평균**

### 한국은행 기준금리 변수
  
- Feature Engineering
  ### 위경도 좌표를 3차원으로 변환
  ### Cyclical Feature
  ![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/288ceb60-e30f-4e45-834e-f965d44cc5d5)
  ### Categorical Feature
  ![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/ca219c8b-db75-4d1d-b4aa-cef657f81369)


## 4. Modeling

### Model descrition

![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/c2a8da92-1d4b-4f2e-a630-e8156fbd3e4c)

- 성능이 가장 잘 나오는 LGBM 모델 선택

### Modeling Process

- _Write model train and test process with capture_

## 5. Result

### Leader Board

![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/358f9458-329a-4139-8de1-82bc4e77da82)

- 4위 88064.8558

### Presentation

- _Insert your presentaion file(pdf) link_


### Meeting Log

![image](https://github.com/UpstageAILab/upstage-ml-regression-02/assets/106041730/e6873ad6-f38d-4bc0-b7de-46197dab4c0a)
- 대회 마지막 주간은 데일리 미팅 진행

### Reference

- 부동산분석 학술지(https://www.ejrea.org/archive/view_article?doi=10.30902/jrea.2020.6.1.19)https://www.ejrea.org/archive/view_article?doi=10.30902/jrea.2020.6.1.19
- 공간정보시스템 지오서비스(http://www.gisdeveloper.co.kr/?p=11030)http://www.gisdeveloper.co.kr/?p=11030
- 서울시 고교 국어수학 백분위 평균(https://cafe.naver.com/we2you/6167)https://cafe.naver.com/we2you/6167
- 한국은행 기준금리(https://www.bok.or.kr/portal/singl/baseRate/list.do?dataSeCd=01&menuNo=200643)https://www.bok.or.kr/portal/singl/baseRate/list.do?dataSeCd=01&menuNo=200643
