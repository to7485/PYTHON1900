# 기본 입출력

## 표준 출력
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

## print()함수
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

## 형식을 갖춘 문자열
- 형식을 갖춘 문자열이란 %연산자나 format()메서드를 이용해 원하는 형식의 문자열을 만드는것을 의미한다.

|형식 기호|의미|자료형|
|---------|-----|---------|
|%d|decimal|정수(10진수)|
|%o|octal|정수(8진수)|
|%x|hexadecimal|정수(16진수)|
|%f|floating point|실수|
|%s|string|문자열|

### 사용법
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

## format()메서드
- format()메서드로 인수나 변수의 값을 표시하고, 해당 값이 표시될 위맃를 중괄호({})로 표시하는 방식

```py
'My name is {}'.format('James')
>>> My name is James
```
- 괄호안에 순번을 넣어 지정하여 출력을 할수도 있다.
```py
'My name is {0}'.format('James')
>>> My name is James
```

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

## f-string
- 파이썬 3.6 이후버전을 사용하고 있다면 f-srtrings라는 새로운 기능을 사용할 수 있다.
- format() 메서드와 유사한 점이 있으나 format()메서드에 비해 좀 더 가독성이 뛰어다나는 장점이 있다.
- 문자열 앞에 f를 붙히고 작성한다.

```py
who = 'you'
how = 'happy'
print(f'{who} make me {how}'
```

- 중괄호 내부에서 함수의 호출이나 연산자도 사용할 수 있다.

```py
age = 25
print(f'내년에는 {age+1}살이 됩니다.')
```

# 표준 입력
- 키보드(표준입력장치)로부터 입력받을 때 사용한다.

```py
변수명 = input('');
Print(변수명);

n = input('');
20 입력하고 엔터
Print(n);
결과값:20
```
- 그런데 이렇게 개발을 한다고 하면 사용자들이 어떤걸 입력하라고 하는건지 알수가 없다.

```py
n = input('정수를 입력하세요: ');
Print(n);

```

## 형변환
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

## 여러개를 입력하고 싶다면...

```py
a, b = input().split()

```
- int(input().split())과 같이 사용하면 TypeError가 발생한다.
- input().split()의 결과가 list이기 때문이다.
- 정수로 변환하려면 다음과 같이 하는것이 좋다.

```py
a, b = map(int, input().split())
```

### map() 함수
- map(function, iterable)
1. split()은 문자열을 나눠 리스트에 담아주는 함수
2. 1을 바탕으로 처리된 리스트에 담겨있는 모든 요소를 int로 바꾸고자 할 때
3. map()함수를 사용한다.

## 응용문제
1. 사용자로부터 2개의 실수를 입력받아 합계를 구하는 프로그램을 구현하세요
```py
실행 예
첫 번째 실수를 입력하세요 >>> 1.23
두 번째 실수를 입력하세요 >>> 2.34
1.23과 2.34의 합은 3.57입니다.
```
2. 사용자로부터 1에서 12사이의 월을 입력받아 해당 월이 며칠까지 있는지 출력하는 프로그램을 구현하세요
```py
실행 예
1~12 사이의 월을 입력하세요 >>> 2
2월은 28일까지 있습니다.

li = [31,28,31,30,31,30,31,31,30,31,30,31]
month = int(input(1~12사이의 월을 입력하세요 >>> ))
print(f'{month}월은 {li[month-1]}일까지 있습니다.')



```
3. 파이썬으로 영어사전을 구현하고자 한다.다음과 같은 딕셔너리(dict)를 하나 생성하고 실행예외 같이 동작하는 프로그램 구현하기
```py
englist_dict={
  'flower':'꽃',
  'fly':'날다',
  'floor':'바닥'
}

실행 예
영어 단어를 입력하세요>>> flower
flower : 꽃

word = input('영어 단어를 입력하세요 >>> ')

print(f'{word} : {english_dict[word]}')
```

# 연산자
- 연산자(Operator)란 특정한 작업을 수행하기 위해서 사용하는 기호를 의미합니다.
- 연산에서 사용되는 항목의 개수에 따라 단항, 이항, 삼항 연산자로 구분할 수 있고,
- 사용 목적에 따라 산술, 대입, 관계, 논리 연산자로 구분할 수도 있다.

## 연산자의 종류
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

## 연산자 우선순위
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

## 산술연산자

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

## 대입연산자
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

## 복합대입연산자
- 복합대입연산자를 통해서 연산을 먼저 진행하고 그 결과를 변수에 저장한다.

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용 방법 </th>
    <th> 의미 </th>
  </tr>
  <tr>
    <td> += </td>
    <td> a += 2 </td>
    <td> 변수 a에 2를 더한 값을 저장합니다. </td>
  </tr>
    <tr>
    <td> -= </td>
    <td> a -= 2 </td>
    <td> 변수 a에 2를 뺀 값을 저장합니다. </td>
  </tr>
  <tr>
    <td> *= </td>
    <td> a *= 2 </td>
    <td> 변수 a에 2를 곱한 값을 저장합니다. </td>
  </tr>
  <tr>
    <td> **= </td>
    <td> a **= 2 </td>
    <td> 변수 a에 2를 거듭제곱 값을 저장합니다. </td>
  </tr>
  <tr>
    <td> /= </td>
    <td> a /= 2 </td>
    <td> 변수 a에 2로 나눈 값을 저장합니다. </td>
  </tr>
  <tr>
    <td> //= </td>
    <td> a //= 2 </td>
    <td> 변수 a에 2로 나눈 몫 값을 저장합니다. </td>
  </tr>
  <tr>
    <td> %= </td>
    <td> a %= 2 </td>
    <td> 변수 a에 2로 나눈 나머지를 저장합니다. </td>
  </tr>
</table>

```py
piggy_bank = 0

money = 10000
piggy_bank += money
print(f'저금통에 용돈 {money}원을 넣었습니다')
print(f'지금 저금통에는 {piggy_bank}원이 있습니다.)

snack = 2000
piggy_bank -= snack
print(f'저금통에 용돈 {money}원을 넣었습니다')
print(f'지금 저금통에는 {piggy_bank}원이 있습니다.')
```

## 관계연산자
- 2개의 항을 비교하여 그 결과를 논리(bool)자료형으로 반환하는 연산자입니다.
- 프로그램의 흐름을 제어하는 제어문에서 널리 활용되는 연산자이기 때문에 반드시 알아둬야 한다.

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용 방법 </th>
    <th> 의미 </th>
    <th> 결과 </th>
  </tr>
  <tr>
    <td> > </td>
    <td> a > 10 </td>
    <td> 크다. </td>
    <td> a가 10보다 크다면 True, 아니면 False </td>
  </tr>
  <tr>
    <td> < </td>
    <td> a < 10 </td>
    <td> 작다. </td>
    <td> a가 10보다 작다면 True, 아니면 False </td>
  </tr>
  <tr>
    <td> >= </td>
    <td> a >= 10 </td>
    <td> 크거나 같다. </td>
    <td> a가 10보다 크거나 같다면 True, 아니면 False </td>
  </tr>
  <tr>
    <td> <= </td>
    <td> a <= 10 </td>
    <td> 작거나 같다. </td>
    <td> a가 10보다 작거나 같다면 True, 아니면 False </td>
  </tr>
    <tr>
    <td> == </td>
    <td> a == 10 </td>
    <td> 같다. </td>
    <td> a가 10이면 True, 아니면 False </td>
  </tr>
  <tr>
    <td> != </td>
    <td> a != 10 </td>
    <td> 같지 않다. </td>
    <td> a가 10이 아니면 True, 아니면 False </td>
  </tr> 
</table>

```py
a = 15
print(f'{a} > 10 : { a > 10}')
print(f'{a} < 10 : { a < 10}')
print(f'{a} >= 10 : { a >= 10}')
print(f'{a} <= 10 : { a <= 10}')
print(f'{a} == 10 : { a == 10}')
print(f'{a} != 10 : { a != 10}')
```

## 논리연산자
- 논리연산자는 관계 연산자와 함께 사용되는 연산자로 2개 이상의 항을 논리적으로 연결할 때 사용하는 and, or연산자
- 1개의 항을 논리적으로 처리하는 not 연산자로 구성되어 있습니다.

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용 방법 </th>
    <th> 의미 </th>
  </tr>
  <tr>
    <td> and </td>
    <td> a and b </td>
    <td> a와 b가 모두 참이라면 True, 아니면 False </td>
  </tr>
  <tr>
    <td> or </td>
    <td> a or b </td>
    <td> a와 b중 하나라도 참이라면 True, 아니면 False </td>
  </tr>
  <tr>
    <td> not </td>
    <td> not a </td>
    <td> a가 참이라면 False로 a가 거짓이라면 True </td>
  </tr>
</table>

```py
a = 10
b = 0
print(f'{a} > 0 and {b} > 0 : {a > 0 and b > 0}')
print(f'{a} > 0 or {b} > 0 : {a > 0 or b > 0}')
print(f'not {a} : {not a}')
print(f'not {b} : {not b}')
```

## 비트연산자
- 비트 연산자는 어떤 변수의 값을 0과 1의 조합인 2진수, 즉 비트로 변환한 뒤에 비트 단위로 연산을 수행한다.

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용 방법 </th>
    <th> 의미 </th>
  </tr>
  <tr>
    <td> & </td>
    <td> a & b </td>
    <td> a와 b를 비트 AND처리 </td>
  </tr>
  <tr>
    <td> | </td>
    <td> a | b </td>
    <td> a와 b를 비트 OR처리 </td>
  </tr>
  <tr>
    <td> ^ </td>
    <td> a ^ b </td>
    <td> a와 b를 비트 XOR처리 </td>
  </tr>
  <tr>
    <td> ~ </td>
    <td> ~a </td>
    <td> a를 비트 NOT 처리(보수연산) </td>
  </tr>
  
  <tr>
    <td> << </td>
    <td> a << 2 </td>
    <td> a를 비트로 변환하여 왼쪽으로 2비트 이동 </td>
  </tr>
  
  <tr>
    <td> >> </td>
    <td> a >>2 </td>
    <td> a를 비트로 변환하여 오른쪽으로 2비트 이동 </td>
  </tr>
</table>

```py
a = 10
b = 70
print(f'a & b : {a & b}')
print(f'a | b : {a | b}')
print(f'a ^ b : {a ^ b}')
print(f'~ a : {~ a}')
print(f'a << 1 : {a << 1}')
print(f'a >> 1 : {a >> 1}')

a = 0000 1010 (10)
b = 0100 0110 (70)

a & b = 0000 0010 (2)
a | b = 0100 1110 (78)
a ^ b = 0100 1100 (76)
~a = 1111 0101(-11)
a << 1 = 0001 0100 (20)
a >> 1 = 0000 0101 (5)
```

## 시퀀스 연산자
- 시퀀스 연산자는 순서가 있는 데이터 구조인 시퀀스(리스트,튜플,range,문자열)에서 사용할 수 있는 연산자

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용방법 </th>
    <th> 의미 </th>
    <th> 결과 </th>
  </tr>
  <tr>
    <td rowspan="2"> + </td>
    <td> [1,3,5] + [2,4,6] </td>
    <td rowspan="2"> 연결하기 </td>
    <td> [1,2,3,4,5,6] </td>
  </tr>
  <tr>
    <td> 'hello' +' '+ 'python'</td>
     <td> 'hello python'</td>
  </tr>
   <tr>
    <td rowspan="2"> * </td>
    <td> [1,3,5]*2 </td>
    <td rowspan="2"> 반복하기 </td>
    <td> [1,3,5,1,3,5] </td>
  </tr>
  <tr>
    <td> '★'*5</td>
     <td> '★★★★★'</td>
  </tr>
</table>

```py
tree = '#'
space = ' '
print(space * 4 + tree * 1)
print(space * 3 + tree * 3)
print(space * 2 + tree * 5)
print(space * 1 + tree * 7)
print(space * 0 + tree * 9)
```

## 기타연산자
### 멤버십 연산자
- 특정 데이터가 컬렉션(리스트,문자열,딕셔너리 등)에 속해있는지 여부를 판단해주는 연산자
- 속했으면 True, 아니면 False를 반환한다.

<table style="border: 2px;">
  <tr>
    <th> 연산자 </th>
    <th> 사용방법 </th>
    <th> 의미 </th>
    <th> 결과 </th>
  </tr>
  <tr>
    <td rowspan="3"> in </td>
    <td> 5 in [1,2,3,4,5] </td>
    <td rowspan="3"> 포함되어있으면 True </td>
    <td> True </td>
  </tr>
  <tr>
    <td> 'h' in 'apple'</td>
    <td> False</td>
  </tr>
  <tr>
    <td> 'a' in {'a':'apple', 'b':'banana'}</td>
    <td> True </td>
  </tr>
   <tr>
    <td rowspan="3"> not in </td>
     <td> 5 in [1,2,3,4,5] </td>
    <td rowspan="3"> 포함되어있지 않으면 True </td>
    <td> False </td>
  </tr>
  <tr>
    <td> 'h' in 'apple'</td>
    <td> True</td>
  </tr>
  <tr>
    <td> 'a' in {'a':'apple', 'b':'banana'}</td>
    <td> False </td>
  </tr>
</table>

### 삼항(조건)연산자
- 어떤 조건식의 결과가 참(True)일경우와 거짓(False)일 경우에 사용할 결과를 한번에 작성할 수 있는 연산자
- 조건식, 참일경우의 결과, 거짓일경우의 결과를 한번에 작성하려면 항이 3개가 필요하기 때문에 삼항 연산자라고 부른다.

<table>
  <tr>
    <th> 연산자 </th>
    <th> 의미 </th>
  </tr>
  <tr>
    <td> 참 if 조건식 else 거짓 </td>
    <td> 조건식의 결과가 참(True)일경우와 거짓(False)일 경우를 한번에 처리함 </td>
  </tr>
</table>

```py
a = 10
b = 20

result = (a - b) if (a >= b) else (b - a)
print(f'{a}와 {b}의 차이는 {result}입니다')
```

## 응용문제
1. 임의의 두 자리 정수(10~99)를 입력받아서 십의 자리와 일의 자리로 분리하여 출력하는 프로그램 구현하기

```py
실행 예
10~99 사이의 숫자를 입력하세요>>> 45
십의자리: 4
일의자리 : 5

str = int(input('10~99사이의 정수를 입력하세요>>>'))

n= 10
str1 = str // n
str2 = str % n

print(f'십의자리 : {str1}')
print(f'일의자리 : {str2}')
```

2. 1분은 60초이고 1시간은 60분입니다. 따라서 1시간은 3600초입니다. 임의의 초를 입력받아 해당 초를 시,분,초로 변환하여 출력하는 프로그램 구현하기

```py
실행예
초를 입력하세요>>> 3690
변환 결과는 1시간 1분 30초 입니다.

str = int(input('초를입력하세요>>>'))

n = 3600

hour = str // n
mi = (str % n) // 60
sec = ((str % n) % 60) % 60

print(f'변환 결과는 {hour}시간 {mi}분 {sec}초입니다.')
```

3. 네자리 정수로 구성된 사원번호를 기준으로 근무시간을 결정한다. 사원번호의 끝자리 숫자가 5이상이면 '오전'아니면 '오후'를 출력하는 프로그램 구현하기
```py
실행예

4자리 사원번호를 입력하세요>>>1255
근무시간은 오전입니다.

str = int(input('사원번호를 입력하세요>>>'))

str %= 10

result = '오전' if str >=5 else '오후'

print(f'근무시간은 {result}입니다.')
```

4. 1박스에 라면이 20개씩 들어간다. 라면이 21개가 있다면 2박스가 있어야 모두 담을 수 있다.<br>라면의 개수를 입력받아 라면을 담기 위해 필요한 박스의 개수를 구하여 출력하는 프로그램 구현하기
```py
실행 예
한 박스에 20개의 라면을 담을 수 있다.
라면의 개수를 입력하시면 필요한 박스 수를 알려드립니다.
라면의 개수를 입력하세요 >>> 50
50개의 라면을 담으려면 3박스가 필요합니다.

ramen = int(input('라면의 개수를 입력하세요 >>> '))

box = ramen // 20 if ramen % 20  == 0 else ramen//20 + 1
print(f'{ramen}개의 라면을 담으려면 {box}박스가 필요합니다.')

```
