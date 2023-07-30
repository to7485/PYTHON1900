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

# pandas(Python Data Analysis Library)
- R과 dataframe 데이터 타입을 참고하여 만든것이 pandas dataframe이다.
- pandas는 dataframe을 주로 다루기 위한 라이브러리이며 dataframe을 자유롭게 가공할 수 있다.
- Pandas Dataframe은 테이블 형식의 데이터를 다룰 때 사용한다.
- pandas dataframe은 다양한 데이터 타입으로 부터 만들 수 있다.
  - 딕셔너리
  - dataframe
  - list 등등
## pandas dataframe의 3요소
- column
- row
- index

## DataFrame의 기본 형태
```py
import pandas as pd
df = pd.DataFrame(data,index,columns,dtype,copy)
```
- data : DataFrame을 생성할 데이터
- index : 각 Row에 대해 Label을 추가 ( 옵션 )
- columns : 각 Column에 대해 Label을 추가 ( 옵션 )
- dtype : 각 Column의 데이터 타입 명시 ( 옵션 )

## Pands로 불러온 데이터 확인하기
- df.head() : 상위 5개의 행 출력하기
- df.shape : 데이터의 행,열 크기 확인하기
- df.info() : 데이터에 대한 전반적인 정보.
  - df를 구성하는 행과 열의 크기
  - 컬럼명
  - 컬럼을 구성하는 값의 자료형 등등
- df.describe() : 컬럼별 요약 통계량을 나타낸다.
- df.corr() : 누락값을 제외하고 전체 컬람들 간의 상관관계도를 계산한다.

## pandas 실습
```py
# pandas : 데이터 분석 라이브러리
# 행(row) x 열(column) 형태의 데이터

#주요 객체는
#DataFrame, Series

import numpy as np
import pandas as pd

##엑셀 읽기 & 저장하기
df = pd.read_csv(‘./data/titanic.csv’)
#df 판다스는 데이터를 dataframe 형태로 보여줄 수 있다.

판다스의 여러가지 메서드를 알아보자
df.head(10) #상위 10개만 뽑기

df[‘Age’]
print(type(da[‘Age’]))

df[[‘Age’]]
print(type(df[[‘Age’]]))

#DataFrame[열 이름]은 Series, DataFrame[[열이름]]은 DataFrame

#데이터프레임 : 행과 열로 이루어진 표를 의미합니다.
#시리즈 : 데이터프레임의 하위 자료형으로 1개의 열이 시리즈이고 이 시리즈가 다수 모여 프레임을 형성한다.

#df[‘Age’, ‘Pclass’] 불가능
#df[[‘Age’, ‘Pclass’]] 가능

df.tail(10) #아래서부터 10개

df2 = pd.DataFrame(
    [[1,2,3,4,],
    [5,6,7,8,],
    [9,10,11,12]], -> 개수가 안맞으면 출력했을 때 NaN 이라고 나옴
    columns = ['국어','영어','수학','과학'],
    index = ['안상현','전소정','정도건'],
)
df2
```
<img width="194" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/7dc80335-150a-4adc-b069-92f1e72e4803">

```py
#컬럼 바꿔주기
Df2.colums = [‘국어’,’영어’,’과학’,’수학’]
```

<img width="185" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/94c41409-d051-45bf-8f89-d33f66627e95">

```py
#out이라는 폴더가 없으면 out폴더 만들기
import os
path = ‘out’
if not os.path.exists(path):
	os.mkdir(path)
	print(path,’경로 생성’)
else:
	print(‘경로가 이미 있습니다.’)

df2.to_excel(‘./out/score.xlsx’, encoding=’euc-kr’) -> 인코딩을 해줘야 깨지지 않는다.

#불러오기
df2 = pd.read_excel('./out/score.xlsx')
df2
```
<img width="272" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/a42da6b6-e969-4ee5-ab1d-2b4b65a456d2">

```py

# 첫번째 칼럼을 index로 사용하기
df2 = pd.read_excel('./out/score.xlsx',index_col = 0)
df2
```
<img width="209" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/1d7a824b-e2d1-40cc-9df5-5cdb71d08536">

```py
df2[['국어','영어','영어']]

#인덱스 이름으로 접근
```
<img width="161" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/5300fd23-06a3-4749-96c3-712351b256b3">

### loc
- location의 약어로 데이터 프레임의 행 또는 칼럼의 이름으로 인덱싱 하는 방법이다.
- 사람이 읽을 수 있는 값으로 특정 값들을 골라오는 방법이다.

### 사용방법
1. df.loc[['행 이름1','행 이름2']] : 첨자 안에 행에 대한 검색 
2. df.loc[['행 이름1','행 이름2']][['열 이름1','열 이름2']] : 행과 열에 대한 데이터 검색
- 슬라이싱이 가능하다.
3. df.loc[['행 이름1 : '행 이름4']]

- loc 실습

```py
#loc
df2.loc[['안상현']] dataframe
```

<img width="188" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/8d5bed6d-d407-4dad-9d53-9682a7f393a6">

```py
df2.loc['안상현'] series

```

<img width="221" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/8bbb1363-1447-432c-a48a-f581f90fb2a9">

```py
df2.loc[[‘홍길동’,’이순신’]][[‘국어’,’영어’]]
```

<img width="119" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/febf57ae-8110-42fd-b435-6ac574dbd5b1">

### loc는 조건을 줄 수 있다.
- 데이터프레임객체.loc[조건 비교할 컬럼과 조건]으로 데이터를 검색

```py
# 나이가 22살인 모든 데이터 검색
df.loc[df[‘Age’] ==22.0] 
```

<img width="617" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/49a8b436-3adc-4e21-81bf-9fdf3aae2ab2">

```py
# 성별이 남자인 사람의 이름, 생존여부, 좌석등급, 나이 데이터 검색
df.loc[df[‘Sex’] == ‘male’][[‘Name’,’Survived’,’Pclass’,’Age’]]
```

<img width="370" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/60099425-5a68-4ad8-8331-f18b98f690d3">

```py
df.loc[df[‘Pclass’] <=2] [[‘Name’,’Pclass’]]
```

<img width="387" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/dee2f6fa-afbb-4b83-ab15-987d4fc27200">

- 한번에 조건을 여러개 검색할 수 있다.
```py
# 조건1 정의
condition1 = (df['fare'] > 30)

# 조건2 정의
condition2 = (df['who'] == 'woman')

df.loc[condition1 & condition2]
```

<img width="600" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/925dbe77-43fb-45bb-99f3-413104129354">

### iloc
- Integer Location의 약자이다.
- 데이터 프레임 행/열의 순서를 나타내는 정수를 통해 가져오는 방법이다.
- loc가 행/열의 이름을 사용한다면 iloc는 행/열의 순번을 사용한다.

1. 데이터프레임.iloc[행 인덱스 번호, 열 인덱스 번호]
2. 데이터프레임.iloc[[행 인덱스 번호, 열 인덱스 번호]]

- 슬라이싱이 가능하다.
    - 데이터프레임.iloc[:인덱스번호,:인덱스번호]

```py
df2.iloc[0]
```
<img width="215" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/ddaead45-4171-4bc2-8098-8cc5639c1766">

```py
df2.iloc[[0]]
```
<img width="181" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/fc3a8882-563a-4635-8209-590a24366571">

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
      - 인자로 들어갈 수 있는 것
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
df = pd.read_csv('data/titanic.csv')

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
- 데이터의 전반적인 형태
- Y라는 종속변수를 계산하기 위해 사용되는 input값 혹은 독립변수

## Input Feature : 데이터 분석을 할 때 들어가는 요소로 분석
- 범주형 변수 : Name, Sex, Ticket, Cabin, Embarked
- 순서가 있는 변수 : Pclass (좌석 등급 1,2,3이 그냥 숫자가 아니라 순서가 있는 것이다.)
- 정수형 변수 : PassengerId, Age, SipSp, Parch, Fare (숫자 형태이다.)

## Target Feature(데이터 분석의 목적)
- 타이타닉 탑승객들에 대한 생존여부를 아는게 목적이다.
- Survived

## 상관관계 표
```py
df.corr(numeric_only=True) #correlation
```

 <img width="581" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/acd94c5b-b5b9-45d0-a6ee-430ce1f8a16a">

- 변수 간 관계의 정도(0~1)와 방향(+,-)을 하나의 수치로 요약해주는 지수
- -1 ~ 1사이의 값을 가진다.
- +이면 양의 상관관계이며 한 변수가 증가하면 다른 변수도 증가한다.
- -이면 음의 상관관계이며 한 변수가 증가할 때 다른 변수는 감소한다.
    - 0.0 ~ 0.2 : 상관관계가 거의 없다.
    - 0.2 ~ 0.4 : 약한 상관관계가 있다.
    - 0.4 ~ 0.6 : 상관관계가 있다.
    - 0.6 ~ 0.8 : 강한 상관관계가 있다.
    - 0.8 ~ 1.0 : 매우 강한 상관관계가 있다.
 
- 범주형 변수는 상관관계표에 등장하지 않는다.
- 상관관계라는건 통계로 표현이 되기 때문에 무언가를 판단할 수 있어야 한다.
- 숫자가 아닌것은 구분할 수 없기 때문에 표로 나타나지 않는다.
- 범주형 변수에는 라벨을 붙혀서(예를 들어 남자면 1, 여자는 0)상관관계를 나타낼 수 도 있다.

- 표로는 한눈에 보기 힘들기 때문에 그래포 표현할 수 있다.

## 상관관계 그래프
### HeatMap이란?
- HeatMap은 열을 의미하는 Heat와 지도를 뜻하는 map을 합친 단어이다.
- Data들의 Array을 색상으로 표현해주는 Graph이다.
### 왜 HeatMap을 사용하는가
- HeatMap을 사용하면 두 개의 카테고리 값에 대한 값 변화를 한눈에 알기 쉽다.
- 대용량 데이터도 HeatMap을 이용해서 시각화 한다면 이미지 몇장으로 표현이 가능하다.
- sns.heatmap (df,vmin,vmax,cbar,center,linewidths,annot, fmt, cmap)
	- vmin : 최소값
   	- vmax : 최대값
   	- cbar : colorbar의 유무
   	- linewidths : cell사이에 선의 굵기 ex) 0.4
   	- linecolor : 선의 색깔 ex) 'white'
   	- annot : 각 cell의 값 표기 유무 ex) True
   	- fmt : 그 값의 데이터 타입 설정 ex) 'd', '.lf'
   	- cmap : 히트맵의 색을 결정한다.
```py
sns.heatmap(df.corr(numeric_only=True), annot = True, cmap = 'RdYlGn', linewidth = 0.2)
fig = plt.gcf()
fig.set_size_inches(10,8)
plt.show()
```
- plt.gcf() : gcf는 get current figure의 약자로 현재 figure를 확인할 수 있다.
- fig.set_size_inches() : 크기지정
- plt.show() : 화면에 표시하는 기능

<img width="450" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/10974874-4e63-4f81-94da-51620b1ed0b9">

## 상관계를 통해 도출한 내용
- Fare와 Pclass는 음의 상관관계를 가지고 있다.(-0.55)
	- Pclass 1이 2,3보다 높은 등급이기에 가격이 더 비싼 것으로 추측할 수 있다.
- Survived와 Pclass는 음의 상관관계를 가지고 있다.(-0.34)
	- 체크 말로 표현하기 힘든 것은 그래프를 통해서 보면서 설명하는게 좋다.
- Age와 Pclass 음의 상관 관계를 가지고 있다.
	- 나이가 많을수록 높은 등급의 클래스를 가질 확률이 높다.
- Pclass는 Survived는 음의 상관 관계가있고, Age와 Plcass가 음의 상관 관계를 갖고 있는데 Age는 Survived와 상관관계가 없다 -> 체크 뭔가 이상하다.
- SipSp는 Parch는 양의상관 관계를 가지고 있다.
	- 가족이 탑승한 경우에는 SipSp(형제자매, 배우자) Parch( 부모,자식)이 함께 탑승했기에 그랬을 것이라 추측할 수있다.
- Fare와 Survived, Parch와 Fare에는 약한 양의 상관관계가 있다.

- 상관관계표를 보고 도출한 내용을 보고 체크를 해봐야 한다.
- 논리적으로 생각을 할 수 있어야 한다.
- 범주형 변수랑 같이 상관관계를 찾아보려고 할 때도 그래프를 그려봐야 한다.

## 1. Sex와 Survived의 그래프
```py
fig, ax = plt.subplots(2, figsize=(18,15)) # 서브플롯을 2개, 크기는 18,15로 만들어라
sns.countplot(x='Sex', data=df, ax = ax[0]) #countplot -> 막대그래프
#df라는 데이터를 가지고 성별이라는 컬럼을 가지고 count를 확인해줘라. 0번째에 그려줘라

sns.countplot(x='Sex', data=df, ax=ax[1], hue = 'Survived')
#hue : 범례를 추가해준다.
plt.show()
```

<img width="978" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/4627cae6-b276-4c81-8323-bcd0a59fc10b">

<img width="979" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/4498b9be-9b20-4a72-97ad-dc4674b134ad">

- 주황색이 생존 파란색이 사망
- 왼쪽이 남자 오른쪽이 여자
- 남자는 600명중에 100명 생존
- 여자는 300명중에 100명 생존

- 성별이 생존과 영향이 있구나?
- 레이디 퍼스트 문화 때문!

- 실제로 그래프에서 막대가 무슨 의미를 지니고 있는지 혹은 라벨이 크기가 작아서 잘 안보이니까 더 꾸며주기 위한 옵션을 주자

```py
fig, ax = plt.subplots(2, figsize=(18,15))
sns.countplot(x='Sex', data=df, ax = ax[0])
#제목 작성 및 라벨 크기 키우기
ax[0].set_title('Sex Count Plot', size = 20) #-> 위에 제목
ax[0].set_xlabel('Sex', size = 15) #-> x축 제목
ax[0].set_ylabel('Count', size = 15) #-> y축 제목
ax[0].tick_params(labelsize = 15) #-> 눈금에 있는 숫자

sns.countplot(x='Sex', data=df, ax=ax[1], hue = 'Survived')
#제목 작성 및 라벨 크기 키우기
ax[1].set_title('Sex Count Plot', size = 20)
ax[1].set_xlabel('Sex', size = 15)
ax[1].set_ylabel('Count', size = 15)
ax[1].tick_params(labelsize = 15)
ax[1].legend(['Not Survived','Survived'], loc = 'upper right', prop = {'size' : 15}) #-> 범례에 이름을 붙힘,위치, 크기 설정
plt.show()
```

<img width="977" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/c002d411-6fce-4cb9-a247-2102ea824cff">


<img width="979" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/f6412d61-9f03-489e-b038-4465ef47ce67">






