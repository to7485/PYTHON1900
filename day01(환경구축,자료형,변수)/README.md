# 실습 환경 구축하기

## 내 PC에 실습을 위한 폴더 만들기
내 PC -> D드라이브 진입 -> PYTHON1900_이니셜 -> 안에 util,work 폴더만들기

![image](https://github.com/to7485/PYTHON1900/assets/54658614/f4bce1d3-d084-4877-b44b-78d6c6443958)

## 프로그램
- 컴퓨터가 실행할 수 있는 명령들을 모음

- 사람 : 명령 -> <- 실행 : 컴퓨터

## 프로그래밍언어
- C,C++,C#,JAVA,PYTHON
- 정해진 규칙에 따라 코드를 작성하는 것.
- 수학적인 표현을 사용함
- +,-,*,/,%
- 사람이 직접 계산하기 힘든 걸 컴퓨터에게 명령함 <br>EX) 1부터 1000까지 소수만 종이에  써라

## 파이썬을 왜 배워야 하는가?
1. 가장 쉬운 프로그래밍 언어
  - 다른 언어를 먼저 배워본 사람은 상대적으로 쉽게 느낄수 있다.
  - 언어를 처음배우는 사람은 어렵게 느낄 수 있다.


 2. 동적 타이핑(Dynamic typing)
  - 변수의 자료형을 지정하지 않고 단순히 선언하는 것만으로도 값을 지정할 수 있습니다.<br> 이때 변수의 자료형은 코드가 실행되는 시점에 결정됩니다.<br> 자료형 변환 시 번거로운 과정을 거치지 않아도 된다는 장점이 있지만,<br> 코드 실행 도중 예상하지 못한 타입으로 인한 에러가 발생할 수 있는 특징이 있습니다.

3. 스크립트 언어(Script language)
  - 파이썬은 컴파일 과정 없이 인터프리터(Interpreter, 해석기)가 소스 코드를 한 줄씩 읽어들여<br> 곧바로 실행하는 스크립트 언어(Script language)입니다.<br> 그 때문에 컴파일 과정이 필요하지 않아 실행 결과를 바로 확인하고 수정하면서 손쉽게 코드를 작성할 수 있습니다.

4. 플랫폼 독립적(Platform-independent)
  - 파이썬은 리눅스(Linux), 유닉스(Unix), 윈도우즈(Windows), 맥(Mac) 등 대부분의 운영체제(Operating System, OS)에서 모두 동작합니다.<br> 운영체제별로 컴파일할 필요가 없기 때문에 한 번 소스 코드를 작성하면 어떤 운영체제에서든 활용이 가능합니다.

## 파이썬의 장점
1. 간결하고 쉬운 문법
  - 파이썬은 인간의 사고와 유사한 문법을 갖고 있습니다. 그 때문에 많은 시간을 들이지 않고도 파이썬 문법을 학습할 수 있고,<br> 프로그래밍을 전공으로 하지 않은 사람도 수일 내에 파이썬을 익혀 활용할 수 있다.

2. 빠른 개발속도
  - 쉬운 문법 덕분에 파이썬은 높은 생산성을 자랑한다. 더 적은 코드로 더 많은 작업을 수행할 수 있다.

3. 활발한 생태계
  - 파이썬은 수많은 표준 라이브러리를 제공한다. 그 덕분에 개발자는 모든 코드를 일일히 작성할 필요가 없다.


## 파이썬 설치하기
- 파이썬만 단독으로 설치를 해서 사용을 할 수 있지만, 나중에 내가 필요로 하는 기능을 추가해서 사용하려고 할 때 초보자들은 어려움을 겪을 수 있다.
    - 공식 홈페이지에서 설치한 파이썬은 패키지 관리자인 pip를 제외한 어떤 패키지도 추가로 설치되어있지 않다.

- 머신러닝이나 데이터분석에 사용되는 여러가지 패키지가 기본적으로 포함되어있는 파이썬 배포판인 아나콘다를 사용할 것이다.

## 아나콘다 설치하기
1. ANACONDA.COM 사이트 접속

![image](https://github.com/to7485/PYTHON1900/assets/54658614/99fe3cbf-04f8-4e3e-b931-d2408f1304b0)

프로그램을 다운받아서 설치파일을 util 폴더에 넣어주자.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/8317f919-6c9a-4384-b4e3-be54ac5c204e)

![image](https://github.com/to7485/PYTHON1900/assets/54658614/b28c1364-6d6a-4311-9774-fd5f67ff3276)

![image](https://github.com/to7485/PYTHON1900/assets/54658614/7a774281-841a-44ea-a312-238299a132b4)

- 경로에 한글이 들어가지 않게 주의해야 한다.(오류가 날수도 있고 나지 않을수도 있기 때문에)

![image](https://github.com/to7485/PYTHON1900/assets/54658614/1f18eb82-4f08-427e-84e6-5d670157137b)

- 따로 체크하는것 없이 install을 눌러서 설치를 진행하자

![image](https://github.com/to7485/PYTHON1900/assets/54658614/eb467180-b68d-4ee0-a39a-8d53a198ad38)

![image](https://github.com/to7485/PYTHON1900/assets/54658614/e4a1c146-1a14-42c2-b53d-cee442c771f2)

- 체크를 해제하지 않으면 아나콘다 홈페이지가 다시 한번 열린다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/08501ba1-1a47-4697-bc16-2f7e9514e47b)

## 아나콘다 실행하기

![image](https://github.com/to7485/PYTHON1900/assets/54658614/936dff2e-dbf7-46ec-aba2-600c61801662)

Anaconda Navigator를 실행하면 아나콘다 로고와 함께 검은색 창이 깜빡거리다가 실행되게 됩니다.

## JupyterNotebook
- 주피터 노트북이란 오픈소스 기반의 웹 플랫폼으로, 파이썬을 비롯한 다양한 프로그래밍언어로 코드를 작성 실행하는 통합 개발 환경을 말한다.

※ 통합 개발 환경(Integrated Development Environment) : 소스코드 작성, 오류 수정, 컴파일, 실행, 배포 등 프로그램을 개발하기 위해 필요한 모든 작업을 하나의 프로그램 안에서 처리할 수 있는 환경
파이썬 환경에서 사용할 수 있는 IDE는 VSCODE, PyCham,Jupyter Notebook 등 이 있다.

- 다른 프로그래밍 언어들은 모두 자체 프로그램을 통안 언어들인데 주피터 노트북은 특이하게 웹을 기반으로 작동을 한다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/0d4e161d-b070-4a82-8f6f-b337af33d78a)

- 맨 처음 화면은 다음과 같습니다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/13d69781-5a4d-4504-aa0b-932045e9499c)

- 주피터를 처음 깔게 되면 C드라이브 > 사용자 > 사용자 이름 으로 경로가 설정이 되어있을거에요.
- 파일을 컴퓨터 안에서 찾기가 힘드니 우리가 만들어놓은 work폴더로 설정을 해놓자.

- anaconda prompt 실행하기

![image](https://github.com/to7485/PYTHON1900/assets/54658614/905e0125-0625-4a1e-a3e1-9c68c8f23e86)

- jupyter notebook --generate-config 입력하기

![image](https://github.com/to7485/PYTHON1900/assets/54658614/73ca7c58-4539-4381-8b6f-2660ff5c521b)

- "C:\Users\사용자이름\.jupyter" 경로에 설정파일이 생성되었을 것이다.
- jupyter_notebook_config.py 파일을 메모장으로 열어보자.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/629bf4c3-e1e3-4a0d-bcc0-665990ab82c3)

- # c.NotebookApp.notebook_dir="경로"  부분을 찾아서 내가 원하는 경로를 대입하고 앞의 #을 제거합니다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/dccc2d76-51cf-4dac-a474-8b58b4a36c20)

- 시작메뉴의 jupyter notebook의 속성을 수정하기

![image](https://github.com/to7485/PYTHON1900/assets/54658614/637cc947-9a0d-4414-a6ba-141bddaef45e)

- 폴더의 Jupyter Notebook을 우클릭 한 후 속성을 선택

![image](https://github.com/to7485/PYTHON1900/assets/54658614/a9de4863-6ef0-4564-948c-d7ead2da0d1b)

- 대상(T) 부분에서 끝의 "%USERPROFILE%/"부분을 변경한 폴더로 바꿔줍니다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/1eebd4d2-1290-446b-83f6-561fad2d49a6)

- 저장을 한 후 Jupyter Notebook을 껐다가 다시 실행하면 경로가 바뀌어있는걸 확인할 수 있습니다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/fb19b0e3-e8d9-40ff-80a1-52b6440b9e48)

- 우측에 new -> python3를 눌러 파이썬 코드를 작성할 수 있는 파일을 생성할 수 있습니다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/2bbb3d03-0fd6-425f-9f06-25f42376b8bf)

## 주피터 노트북 사용법
- 주피터 노트북은 셀 형태로 이루어져 있습니다.




