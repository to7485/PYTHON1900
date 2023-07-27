# 데이터의 분석
- 기업의 의사결정을 위해 빅데이터를 정리/변환/모델링의 과정을 거쳐 데이터를 분석하는 것을 의미합니다.
- 일반적으로 <b>문제 정의 -> 데이터 수집 -> 데이터 전처리와 EDA -> 모델링 -> 의사결정</b>의 과정을 거칩니다.

## 데이터 분석의 단계
1. 문제 정의
  - 기업의 현재 문제를 어떤식으로 정의하느냐에 따라 앞으로 진행하게될 데이터 분석의 방향이 달라집니다.
    - Top-down 방식 : 기업 임원진들이 문제를 확인하고 분석하라고 하는 방식
    - Bottom-up 방식: 실무진이 데이터를 확인하고 데이터 분석 후 임원진들에게 보고하는 방식
    - 오티스 사의 엘리베이터 거울의 사례 : 1853년 미국에 고층빌딩이 들어서기 시작하면서 엘리베이터가 보급이 되었다<br>하지만 속도가 느려서 손님들이 불만이 많자 엘리베이터에 거울을 설치하여 거울을 보느라 지루함을 못느끼게 된 사례

2. 데이터 수집
  - 앞서 정의한 문제와 관련된 질좋은 데이터 수집 과정이 필요합니다.
  - 실제로 질좋은 데이터가 없어서 데이터 분석 과정이 매우 어려울 수 있습니다.

3. 데이터 전처리와 EDA
  - EDA란 데이터 분석에 앞서 데이터의 시각화를 통해 데이터에 대한 이해하는 과정을 의미합니다.
  - 실제 데이터를 확인해보고 데이터가 어떤 모양을 가지고 있는지 데이터의그래프 형태가 어떤지 확인하는 것.
  - 데이터 전처리와 EDA(Exploratory Data Analysis)과정을 거쳐 현재 주어진 데이터를 확인하고 정제하는 작업을 진행합니다.
  - 전처리 이후에 EDA를 진행하기에 이 둘을 구분하는 경우도 있지만 EDA를 통해 데이터의 모양이 이상한 것을 확인한다면 다시 전처리를 진행해야합니다.
  - 실제 데이터 분석에서 70% 이상을 차지하기도 합니다.

4. 모델링
  - 실제 데이터를 머신러닝을 통해 학습시켜 모델을 만드는 과정입니다.
  - 일반적으로 훈련집합과 테스트집합(+ 검증집합)으로 나눠 학습과 테스트를 진행하여 모델의 정확도를 구합니다.
  - 데이터 분석은 크게 두가지로 분류할 수 있다.
    - 예측: 여태까지의 데이터를 토대로 미래의 일을 예측하는 것 ex) 주식 가격 예측 / 농산물 가격 예측 등
    - 분류: 여태까지의 데이터를 토대로 추후에 주어진 데이터를 분류하는 것 ex) 신용불량자 분류 / 암 환자 분류 등

5. 의사결정
  - 분석된 결과를 바탕으로 실제 의사결정에 반영하는 것입니다.
  - 월마트의 맥주와 기저귀 사례 -> 남편들이 기저귀를 사러가서 가는김에 맥주까지 사고오기 때문에 매출이 같이 올라 맥주를 눈에 띄는곳에 배치했더니 이전보다 매출이 5배가 오른 사례

## 데이터 분석 예시
- Titanic Survival Prediction
  - 타이타닉 탑승객들에 대한 정보(생존유무,이름,성별,나이,동행자 등등)으로 데이터 분석
- Iris Analysis
  - 프로그래밍 분야에서의 'Hello World'와 같다고 할만큼 유명하다.
  - 붓꽃의 발생학적 특징(꽃받침의 길이,너비 / 꽃잎의 길이,너비 / 꽃의 종류)에 대한걸 가지고 분석을 하는것.
- 은행 계좌 정보를 토대로 신용불량자 예측
- 교통사고 다발지역 예측
- 서울시 지하철 혼잡도 분석을 통한 지하철 노선도 제안 등등

# EDA(Exploratory Data Analysis) 탐색적 데이터 분석
## EDA란?
- 본격적인 데이터 분석에 앞서 데이터의 시각화를 통해 데이터에 대해 이해하는 과정을 의미합니다.
- 의미없는 데이터를 학습시킨다면 정확하지 못한 결과가 나올 수 있습니다.
- 데이터 시각화를 통해 데이터를 이해하고 올바른 학습을 하는 것이 중요합니다.

## matplotlib
- 파이썬에서 가장 널리 사용되는 대표적인 시각화 라이브러리(모듈)입니다.
  - figure : 이미지 전체의 영역을 확보(종이)
  - ax(axes) : 그 공간중 내가 사용할 부분
    - fig = figure() : ax 없는 빈 figure 생성 (후에 ax를 추가해줘야함)
    - fig, ax = plt.subplots() : 하나의 ax 만을 가지는 하나의 figure 생성
    - fig, axes = plt.subplots(2,2) : 4개(2*2)이 ax들을 가지는 하나의 figure 생성
   
<img width="646" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/4d4d9915-9a42-46be-8f24-6145dca74c58">

  - plot : 그래프를 그리는 함수
    - plot()
      - figsize : (width, height)의 튜플을 전달한다. 단위는 인치이다.
      - dpi : 1인치당의 도트 수
      - facecolor : 배경색
      - edgecolor : 외곽선의 색
  - subplot : 여러개의 그래프를 그리고 싶을 때 사용한다.
    - subplot(행,열,index) -> figure와 axes 전달
  - add_subplot(행,열, 변호)
  - legend: 범례나 레이블 등 추가정보를 포함해 작성
    - legend('위치')
  - show() : 그래프를 화면에 나타내도록 하는 함수

## seaborn
- matplotlib 기반으로 만들어진 통계 데이터 시각화 라이브러리

## pandas(Python Data Analysis Library)
- R과 dataframe 데이터 타입을 참고하여 만든것이 pandas dataframe이다.
- pandas는 dataframe을 주로 다루기 위한 라이브러리이며 dataframe을 자유롭게 가공할 수 있다.
- Pandas Dataframe은 테이블 형식의 데이터를 다룰 때 사용한다.
- pandas dataframe은 다양한 데이터 타입으로 부터 만들 수 있다.
  - 딕셔너리
  - dataframe
  - list 등등
### pandas dataframe의 3요소
- column
- row
- index

### DataFrame의 기본 형태
```py
import pandas as pd
df = pd.DataFrame(data,index,columns,dtype,copy)
```
- data : DataFrame을 생성할 데이터
- index : 각 Row에 대해 Label을 추가 ( 옵션 )
- columns : 각 Column에 대해 Label을 추가 ( 옵션 )
- dtype : 각 Column의 데이터 타입 명시 ( 옵션 )

### Pands로 불러온 데이터 확인하기
- df.head() : 상위 5개의 행 출력하기
- df.shape : 데이터의 행,열 크기 확인하기
- df.info() : 데이터에 대한 전반적인 정보.
  - df를 구성하는 행과 열의 크기
  - 컬럼명
  - 컬럼을 구성하는 값의 자료형 등등
- df.describe() : 컬럼별 요약 통계량을 나타낸다.
- df.corr() : 누락값을 제외하고 전체 컬람들 간의 상관관계도를 계산한다.

# Titanic Survival Prediction
```py
#matplotlib가 설치가 안되어 있는 경우
#!pip install matplotlib

#seaborn이 설치가 안되어있는 경우
#!pip install seaborn

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

#셀 아래에 그래프 출력하도록 지원
%matplotlib inline

import warnings
warnings.filterwarnings('ignore') #경고 메세지 무시

#데이터 불러오기
df = pd.read_csv('./data/titanic.csv')

#데이터 상위 5개 불러오기
df.head()

```

<img width="643" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/df218fc1-a230-4de0-b5c3-074c59413fe5">


```py
#변수 정보 확인
df.info()
```
- column : 총 12개의 컬럼이 존재
- non-null count : null이 아닌 데이터의 개수
- NaN : 어떠한 이유에서인지 관측이 불가능한 값
- dtype : 데이터 타입 object는 문자열이라고 보면 된다.

<img width="383" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/77759bb0-81bf-4795-91c1-2f5bcef79bf9">

- 위와 같은 방식들로 데이터의 전반적인 형태를 둘러볼 수 있다.

# Feature
- Y라는 종속변수를 계산하기 위해 사용되는 input값 혹은 독립변수








