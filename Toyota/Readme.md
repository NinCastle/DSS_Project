# [5조 Bot] Toyota Corolla 중고차 가격 예측 (회귀분석)

<img src = 'https://www.toyota.co.nz/api/image/vehicle/380/040/'>

# 프로젝트 개요

### (1) 목표 
Toyota Corolla 중고차 관련 spec. 및 price data로  회귀분석하여 **중고차 가격(종속변수)** 을 예측하는 모델을 생성

### (2) 주어진 Data

* Toyota Corolla 가격 및 spec 관련 Data
    * **Training** Data: 
        * 39개의 변수, 1019대의 서로 다른 Corolla spec & price data
        * 1020 row * 39 columns (index 포함)
        
    * **Test** Data
        * Price(종속변수)가 NaN 값인 Data, 417대의 서로 다른 Corolla spec & price
        * 418 row * 39 columns (index 포함)
    

* ** 변수 종류 및 정의 **
    * Model Description : 모델
    * Offer Price in EUROs : 가격
    * Age in months as in August 2004 : 2004 년 8 월 까지 개월 수(연식)
    * Manufacturing month (1-12) : 제조월
    * Manufacturing Year : 제조 년도
    *Accumulated Kilometers on odometer : 주행거리
    * Fuel Type (Petrol, Diesel, CNG) : 연료유형 (오일, 디젤, CNG)
    * Horse Power : 마력
    * Metallic Color? (Yes=1, No=0) : 메탈릭컬러 (예 = 1, 아니오 = 0)
    * Color (Blue, Red, Grey, Silver, Black, etc.) : 차 색깔
    * Automatic ( (Yes=1, No=0) : 자동 (yes = 자동 , no='수동)
    * Cylinder Volume in cubic centimeters : 입방 cm 단위 실린더 크기
    * Number of doors : 문 개수
    * Number of cylinders : 실린더 개수
    * Number of gear positions : 기어 단계 수
    * Quarterly road tax in EUROs : 환경부담금
    * Weight in Kilograms : Kg 단위 중량
    * Within Manufacturer's Guarantee period (Yes=1, No=0) ; 제조사 보증기간 이내
    * BOVAG (Dutch dealer network) Guarantee (Yes=1, No=0) : BOVAG 보증
    * Guarantee period in months : 월 단위 보증 기간
    * Anti-Lock Brake System (Yes=1, No=0) : 특수 제동 장치 -
    * Driver_Airbag (Yes=1, No=0) : 운전석 에어백
    * Passenger Airbag (Yes=1, No=0) : 보조석 에어백
    * Airconditioning (Yes=1, No=0) : 에어컨
    * Automatic Airconditioning (Yes=1, No=0) : 자동 에어컨디셔닝 장치 유무
    * Boardcomputer (Yes=1, No=0) : 기판 컴퓨터 유무
    * CD Player (Yes=1, No=0) : cd플레이어 유무
    * Central Lock (Yes=1, No=0) : 주행중에 자동차 문이 자동으로 잠기는 장치 유무
    * Powered Windows (Yes=1, No=0) : 자동 창문 개폐창 유무
    * Power Steering (Yes=1, No=0) : 동력조향장치 유무(핸들 조작을 쉽게 해줌)
    * Radio (Yes=1, No=0) : 카라디오 유무
    * Mistlamps (Yes=1, No=0) : 자동차 안개등 유무
    * Sport Model (Yes=1, No=0) : 스포츠카인지 아닌지(확인요망)
    * Backseat Divider (Yes=1, No=0) : 등받이 분배기 유무
    * Metallic Rim (Yes=1, No=0) : 메탈릭 림 유무
    * Radio Cassette (Yes=1, No=0) : 라디오 카세트 유무
    * Parking assistance system (Yes=1, No=0) : 주차 보조 시스템 유무
    * Tow Bar (Yes=1, No=0) : 견인바 유무
    
### (3) 요약

1) **데스크 리서치**
   : 중고차 매매 서비스를 제공하는 웹사이트 및 앱 조사를 통해 매매 관련 중요하게 고려되는 요소들을 조사
    
2) **EDA** 
   : 탐색 과정을 통해 데이터 분류 및 이상치 확인, 변수간 관계(Scatter plot, Heat map 등) 확인 

3) **Feature Selection**
   : ANOVA, OLS 등을 통해 회귀모형을 만들기 위한 변수를 선택. 

4) **Modeling**
   : 선택된 변수간 다중공선성, 변수의 스케일링, 변수변환 및 아웃라이어 제거 등의 과정을 통해 모델을 개선

5) **Cross Validation**
   : Train data를 테스트용과 훈련용으로 분리하여, 회귀모형을 테스트 (RMSE 이용)
