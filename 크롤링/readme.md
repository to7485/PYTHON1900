# 크롤링
- 웹페이지에 있는 데이터들을 프로그래밍적으로 추출하는 것을 뜻한다.
- 크롤링의 원리를 이해하기 위해서는 웹페이지의 구성을 알고 있으면 좋다.

## HTML
- HTML은 Hyper Text Markup Language의 약자입니다.
- HTML은 웹페이지를 만드는 대표적인 마크업 언어입니다
- HTML은 웹페이지의 구조를 표현합니다.
- HTML은 여러 요소로 구성되어 있습니다
- HTML은 브라우저에 어떻게 내용을 표시할지 알려주는 역할을 합니다.

## 기본구조

![image](https://user-images.githubusercontent.com/54658614/226808086-fb78d205-363b-4f50-a8b3-739b11d256b3.png)

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>

  </body>
</html>
```

### 설명
- \<!DOCTYPE html\> 
	- HTML5 문서임을 선언합니다. 
	- doctyle에 따라 HTML 종류와 버전이 결정되며 그에 따라 브라우저에서 각 요소 표현 방식이나 호환되는 자바스크립트, CSS 적용 방식이 달라질 수 있습니다.
	- 현재는 거의 모든 브라우저가 HTML5를 지원하므로 HTML5 문서로만 지정해서 사용할 수 있도록 합니다.

	- 문서에서 한번 만 정의되고 페이지의 가장 상단에 위치합니다.
	- DOCTYPE -> doctype과 같이 대소문자 구분 없이 정의해도 인식을 합니다.

- \<html\> ~ \</html\>
	- HTML페이지에서 root 요소입니다(가장 상위 요소)

- \<head\>~\</head\> 
	- 주로 HTML페이지에서 meta 정보를 포함합니다
	- 예) \<meta charset=’utf-8’\>

	- 또한 초기 페이지 렌더링시에 불러와야 할 외부 링크를 정의합니다.(css, javascript)
	```
	<link rel="stylesheet" type="text/css" href="style.css">
	<script src="common.js"></script>
	```

- \<title\>~\</title\>
	- HTML 페이지의 제목을 나타냅니다. 
	- 브라우저 상단의 웹페이지 탭에 제목으로 노출이 됩니다. 


- \<body\>~\</body\>
	- HTML문서에서 실질적으로 보이는 영역을 정의하는 구간입니다.
	- 예) 이미지, 본문내용, 링크, 테이블, 제목 등등

 ## HTML의 요소

 ![image](https://user-images.githubusercontent.com/54658614/226809179-689d77ca-eca9-4989-8b6c-c8888bdcfc9a.png)

- HTML 요소는 일반적으로 태그라는 명칭이 익숙할 수 있습니다.
- HTML 요소는 일반적으로 시작 태그와 닫힘 태그로 정의가 됩니다. 다만 시작 태그와 닫힘태그가 없는 유일한 태그도 있습니다.
```
   (예 - 줄바꿈 태그 <br> 또는 <br />)
   <태그> 내용 </태그>
```

## HTML 속성(attributes)
- 모든 HTML 요소들은 속성(attributes)를 가지고 있습니다. 
- 속성(attributes)는 HTML 요소에 대한 추가적인 정보를 제공 합니다.
- 특정 태그에서의 속성이나 사전 정의된 속성은 적용된 기능으로서 추가정보를 활용합니다.

- 예) 특정기능으로써 속성 예시 a태그, input 태그, img 태그
```html
<a href='https://www.naver.com' target='_blank'>네이버</a>
<input type='text' name='subject'>
<img src='이미지 경로'>
```
## CSS식별자
### 태그로 접근
- 내가 식별하고 싶은 태그의 이름을 직접 적으면 된다.

### 클래스 식별자
- 스타일 변경만을 위해서 사용되는 속성
- 똑같은 태그가 있을때 구별하기 위한 식별자가 된다.
- 같은 문서에 CSS가 HTML 요소로 함께 존재하게 되는 형태입니다. 
- 여러페이지에 공통 스타일이 있는 경우 중복해서 작성해야 하는 불편함이 있고, 중복된 소스가 분산되어 산재하므로  유지 보수에 어려움이 따를 수 있습니다.
- 클래스를 가진 태그로의 접근은 .클래스명 으로 한다.

```html
<div class='value'> content </div>
```

### id 식별자
- id의 경우 나중에 서버로 데이터를 넘겨야 하는 경우도 있기 때문에 중복이 되면 혼란을 야기할 수 있다.
- id를 가진 태그로의 접근은 #id값 으로 한다.
```html
<div id='value'> content </div>
```

# BeautifulSoup
- BeautifulSoup이란 스크래핑을 하기위해 사용하는 라이브러리.
- HTML,XML등의 데이터를 파싱(Parsing)할 수 있다.
- 원하는 데이터를 특정 패턴이나 방법 또는 순서로 탐색,검색,수정등 기능을 수행한다.
- 아무 페이지를 들어가서 '소스보기' 또는 개발자도구를 통해 볼 수 있는 HTML문서가 크롤링의 대상이다.

## HTML문서 읽어오기
```py
fp = open('data/sample.HTML','r',encoding='utf-8')
html = fp.read()
fp.close()

print(html)
```
- 내용을 다 읽어온다.
- 태그로 정리가 되어 불러와지는데 read함수는 모두 문자열로 저장을 한다.
- 여기에서 내가 원하는 것들만 불러오기 힘들기 때문에 사용을 하는것이 BeautifulSoup이다.
- 태그의 이름을 갖고 추출하기도 하고,클래스나id를 가지고 추출하기도 한다.

## BeautifulSoup로 파싱하기
```py
from bs4 import BeautifulSoup

fp = open('data/sample.HTML','r',encoding='utf-8')
html = fp.read()
fp.close()

data = BeautifulSoup(html,”html.parser”)
print(type(data))
print(data)
```

## 파싱을 위한 BeautifulSoup의 함수

### 1. Select,Select_one
- data.select(CSS Selector)
- select 메서드는 파라미터로 전달한 CSS Selector로 select된 elements들로 구성된 list를 반환한다.
    - select메서드는 한개도 select되지 않아도 비어있는 list를 반환한다.
```py
print(data.select(‘.animal’)) # 리스트 형태로 반환
print(data.select(‘h2’)) # 비어있는 리스트 반환

#select()의 결과 element의 개수를 알고싶다면?
print(len(data.select(‘.animal’)))

#indexing
print(data.select(‘.animal’)[0])
print(data.select(‘.animal’)[-1])
```
- data.select_one(CSS Selector)
- select_one 메서드는 파라미터로 전달한 CSS Selector로 select된 첫번째 element 하나를 반환한다.
```html
print(data.select_one(‘h1’))
print(type((ata.select_one(‘h1’))) #element
print(data.select_one(‘h2’)) # None
print(data.select_one(‘ul li’))
```

## text 메서드
- 파싱된 태그에서 Content부분만 문자열 형태로 돌려준다.
```py
print(data.select_one(‘ul li’).text)

animals = data.select(‘.animal’)
for I in range(len(animals)):
	print(animals[i].text)

fruits = data.select(‘.fruit’)

for I in range(len(fruits)):
	print(fruits[i].text)

#공백이 존재하는 경우 -> strip()
# strip() : 좌우 여백 제거
print(data.select(‘.fruit’)[0].text.strip()) 공백이 제거된 상태로 출력
```
## 실습문제 풀어보기
### 실습문제 1
### 배운 내용 토대로 [‘apple’,’banana’] 만들기
```py
result = []
fruits = data.select(‘.fruit’)
for I in range(len(fruits)):
	result.append(fruits[i].text.strip())
```
### 실습문제2
### animals에 대한 리스트 만들기
```py

#[‘dog’,’cat’,’frog’,’this’,’fish’]
result = []
animals = data.select(‘.animals’)
for animal in animals:
	result.append(animal.text.strip())
print(result)
```
### 실습문제3
### animals에 대한 리스트 만들기2
```py

[‘dog’,’cat’,’frog’,’this’]
result = []
animals = data.select(‘ul .animal’) 위계 구조를 잘 알고 있자!
for animal in animals:
	result.append(animal.text.strip())
print(result)

```











 
