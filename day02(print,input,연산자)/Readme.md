## 기본 입출력

### 표준 출력
- 파이썬은 이스케이프문자(escape character)를 지원한다.
- 확장문자 라는 의미로 대부분의 프로그래밍언어에서 지원하기 때문에 알아두는것이 좋다.
- 이스케이프문자들은 \\로 시작한다.

|이스케이프 문자|의미|
|---------|-----|
|\\'|작은따옴표|
|\\"|큰따옴표|
|\\n|줄바꿈(LineFeed)|
|\\r|캐리지 리턴|
|\\t|탭(tab)|
|\\v|수직탭(vertical tab)|
|\\\ |역슬래쉬|
|\\a|벨(bell)|
|\\b|백스페이스|

```py

print('Hello \'World\'')
print("Hello \"World\"")
print('*\n**\n***\n')
print('이름\t연락처')
print('제시카\t02-123-4567')
print('마틴\t010-8765-1234')

```

### print()함수
- 사실 print()함수를 정석적으로 사용하고자 한다면 다음과 같이 작성해야 한다.
```py
print(value. ..., sep='', end='\n', file=sys.stdout, flush=False)
```

|속성명|속성 의미|기본값|기본값 의미|
|---------|-----|---------|-----|
|sep|출력할 value의 구분자|''|공백|
|end|value 출력 후 출력할 문자|'\n'|줄 바꿈|
|file|출력 방향 지정|sys.stdout|모니터를 의미|
|flush|flush 유무 지정|False|스트림 비우지 않음|

### 형식을 갖춘 문자열
- 형식을 갖춘 문자열이란 %연산자나 format()메서드를 이용해 원하는 형식의 문자열을 만드는것을 의미한다.

|형식 기호|의미|자료형|
|---------|-----|---------|
|%d|decimal|정수(10진수)|
|%o|octal|정수(8진수)|
|%x|hexadecimal|정수(16진수)|
|%f|floating point|실수|
|%s|string|문자열|

#### 사용법
```py
print('형식문자' % 데이터)
```

```py
name = 'kai'
print('내 이름은 %s입니다.' % name)

height = 120.5
print('제 키는 %fcm입니다.' % height)

weight = 23.55
print('제 몸무게는 %.1fkg입니다.' % weight)

year, month, day = 2014, 8, 25
print('제 생일은 %d년 %d월 %d일입니다.' %(year,month,day))
```

### format()메서드
- format()메서드로 인수나 변수의 값을 표시하고, 해당 값이 표시될 위맃를 중괄호({})로 표시하는 방식

```py
'My name is {}'.format('James')
>>> My name is James
```
- 괄호안에 순번을 넣어 지정하여 출력을 할수도 있다.
```
'My name is {0}'.format('James')
>>> My name is James
```py
- 내가 출력하고자 하는 변수명을 지정할수도 있다.
- 이럴경우 반드시 format()메서드에 '변수병=값'과 같은 방식으로 인수를 지정해야 한다.

```py
'My name is {name}'.format(name='James')
>>> My name is James
```
- 2개 이상의 인수를 사용하는 경우
```py
'My name is {}. I\'m {}years old'.format('James',25)
>>> My name is James. I'm 25years old

'My name is {1}. I\'m {0}years old'.format(25,'James')
>>> My name is James. I'm 25years old

'My name is {name}. I\'m {age}years old'.format(name='James',age=25)
>>> My name is James. I'm 25years old
```




