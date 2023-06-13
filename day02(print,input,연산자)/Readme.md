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

### f-string
- 파이썬 3.6 이후버전을 사용하고 있다면 f-srtrings라는 새로운 기능을 사용할 수 있다.
- format() 메서드와 유사한 점이 있으나 format()메서드에 비해 좀 더 가독성이 뛰어다나는 장점이 있다.
- 문자열 앞에 f를 붙히고 작성한다.

```py
who = 'you'
how = 'happy'
print(f'{who} make me {how}'
```

- 중괄호 내부에서 함수의 호출이나 연산자도 사용할 수 있다.

```
age = 25
print(f'내년에는 {age+1}살이 됩니다.')
```

## 표준 입력
- 키보드(표준입력장치)로부터 입력받을 때 사용한다. 
```
변수명 = input('');
Print(변수명);

n = input('');
20 입력하고 엔터
Print(n);
결과값:20
```
- 그런데 이렇게 개발을 한다고 하면 사용자들이 어떤걸 입력하라고 하는건지 알수가 없다.

```
n = input('정수를 입력하세요: ');
Print(n);

```

### 형변환
- input()메서드를 통해 입력받는 모든 값은 문자열로 저장이 된다.

```py
n = input('정수입력>>> ')
print(type(n))
```
- 형변환 함수를 사용한다.

```py
n = int(input('정수입력>>> '))
print(type(n))
```

### 여러개를 입력하고 싶다면...

```
a, b = input().split()

```
- int(input().split())과 같이 사용하면 TypeError가 발생한다.
- input().split()의 결과가 list이기 때문이다.
- 정수로 변환하려면 다음과 같이 하는것이 좋다.
```
a, b = map(int, input().split())
```

## 연산자
- 연산자(Operator)란 특정한 작업을 수행하기 위해서 사용하는 기호를 의미합니다.
- 연산에서 사용되는 항목의 개수에 따라 단항, 이항, 삼항 연산자로 구분할 수 있고,
- 사용 목적에 따라 산술, 대입, 관계, 논리 연산자로 구분할 수도 있다.

### 연산자의 종
<table>
  <tr>
    <th>종류</th>
    <th>연산자</th>
    <th>의미</th>
  </tr>
  <tr>
    <td>산술연산자</td>
    <td>+,-,*,\**,/,//,%</td>
    <td>숫자 연산</td>
  </tr>
    <tr>
    <td>대입연산자</td>
    <td>=,+=,-=,\*=,\*\*=,/=,//=,%=</td>
    <td>대입 및 복합대입</td>
  </tr>
    <tr>
    <td>관계연산자</td>
    <td> >,>=,<,<=,==,!= </td>
    <td>크기 비교</td>
  </tr>
    <tr>
    <td>논리연산자</td>
    <td> and, or, not</td>
    <td>하나 이상의 논리적 처리</td>
  </tr>
    <tr>
    <td>비트연산자</td>
    <td>&,\|,^,~,<<,>></td>
    <td>이진 연산</td>
  </tr>
  <tr>
    <td>삼항연산자</td>
    <td> 참 if 조건식 else 거짓</td>
    <td>조건 연산</td>
  </tr>
  <tr>
    <td>기타연산자</td>
    <td> in, +, *</td>
    <td>시퀀스 연산</td>
  </tr>
</table>

### 연산자 우선순위
- 연산자의 주요 우선순위는 다음과 같다.
- 우선순위를 모두 암기할필요는 없다.
- 먼저 처리하고 싶은 연산이 있다면 ()를 이용하면 된다.

|우선순위|연산자|의미|
|-----|------|------|
|1|[값...],(값...),{값...},{키:값...}|리스트, 튜플, 집합, 딕셔너리|
|2|a[0],a[0:3],a.name|인덱싱,슬라이싱,객체값|
|3|\*\*|거듭제곱|
|4|+,-|양의 부호, 음의 부호|
|5|\*,/,//,%|곱셈,나눗셈,몫,나머지|
|6|+,-|덧셈,뺄셈|
|7|<, <=, >, >=, ==, !=|관계연산자|
|8|not|논리 NOT|
|9|and|논리 AND|
|10|or|논리 OR|
|11| 참 if 조건식 else 거짓|조건 연산자|

### 산술연산자

- +,-,*,/
- //:결과값이 정수형으로 나온다.
- % :나머지연산자
- x%y 연산의 나머지를 결과값으로 가진다
- \**:제곱연산자

```py
a = 7
b = 2
print(f'{a} + {b} = {a+b}')
print(f'{a} - {b} = {a-b}')
print(f'{a} * {b} = {a*b}')
print(f'{a} / {b} = {a/b}')
print(f'{a} // {b} = {a//b}')
print(f'{a} % {b} = {a%b}')


-->홀짝 구분
N%2 = 1
N은 홀수
N%2 = 0
N은 짝수

```

### 대입연산자
- 변수에 값을 저장하기 위해서 사용하는 연산자
- 대입연산자 '='는 반드시 왼쪽에 변수가 배치되고 오른쪽에 저장할 값이 배치되어야 한다.
- 일반적인 프로그래밍 언어들은 한 번에 1개의 변수에 값을 저장할 수 있지만, 파이썬은 2개 이상의 변수에 값을 저장할 수 있다.

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용 방법 </th>
    <th> 의미 </th>
  </tr>
  <tr>
    <td rowspan="2"> = </td>
    <td> a = 1 </td>
    <td> 변수 a에 1을 저장합니다. </td>
  </tr>
  <tr>
    <td> a,b = 1,2 </td>
    <td> 변수 a에1, 변수 b에 2를 저장한다. </td>
  </tr>
</table>

```py
a,b = 10,20
print(f'a = {a}, b = {b}')
a,b = b, a
print(f'a = {a}, b = {b}')
```














