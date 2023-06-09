# 제어문
- 프로그램의 흐름을 제어하는 문법
  - 프로그램의 흐름? 위에서 아래로, 왼쪽에서 오른쪽으로 작동하는게 일반적이다.
  
## 제어문의 종류
- 조건문 : 조건에 의해서 명령을 실행할지, 실행하지 않을지 흐름을 제어하는 문법
- 반복문 : 조건에 의해서 명령을 반복할지 반복하지 않을지 제어하는 문법

# 조건문
- 특정 조건을 만족하는지 여부에 따라 실행하는 코드가 달라야할때 사용합니다.

## if문
```py
기본형

if 조건식 : 
  조건식의 결과가 True일때 실행문

```

- 변수 a에 저장된 값이 0보다 크면 '양수'를 출력하는 코드를 작성하면 다음과 같다.

```py
a = 3

if a > 0:
    print('양수')
```

### 주의점
- 실행문을 작성할 때는 반드시 들여쓰기를 해야 한다.
-  : 을 작성하고 자동으로 엔터를 치면 들여쓰기가 된다.

- 들여쓰기 규칙
1. 공백(space)나 탭(tab)을 이용하여 들여쓰기를 수행한다.
2. 공백의 개수는 상관없다.
3. 탭은 1개만 사용해야 한다.
4. 동일구역에서 들여쓰기는 통일해야 한다.

## if-else문
- 조건식을 만족하는 경우와 만족하지 않는 경우를 구분하여 코드를 작성할 때 사용한다.

```
기본형
if 조건식 :
  조건식의 결과가 True일 때 실행문
else :
  조건식의 결과가 False일 때 실행문
```

```py
a = 10

if a > 0:
  print('양수')
else :
  print('음수')
```
- 나이를 입력받아 20살 이상이면 '성인', 20살 미만이면 '미성년자'를 출력하는 프로그램

```py
age = int(input('나이는 몇살입니까?>>>'))
if age >=20:
    print('성인')
else:
    print('미성년자')
```

- 중요도가 100 이상이면 '상', 50~99면 '중', 50미만은 '하'로 구분하여 출력하기
```py
important = 84

if important >=100:
    print('상')
else:
    important >= 50:
        print('중')
    else:
        print('하')
```

## if-elif문
- 위 문제는 if-else문 하나로는 해결이 되지 않기 때문에 else문 내부에 또 다른 if-else문을 추가하여 해결을 했다.
- 이 방법은 구분해야할 데이터가 많아지면 많아질수록 코드가 굉장히 복잡해지는 단점이 있다.
- 이러한 단점을 보완하기 위해 if-elif문을 사용한다.

```
기본구조

if 조건식1:
    조건식1의 결과가 True일 때 실행문
elif 조건식2:
    조건식1의 결과가 False이고, 조건식2의 결과가 True일 때 실행문
elif 조건식3:
    조건식1,2의 결과가 False이고, 조건식2의 결과가 True일 때 실행문
```

- elif구문은 원하는 만큼 계속 추가할 수 있고 필요하다면 마지막에 else문을 추가할 수 있다.

```
if 조건식1:
    조건식1의 결과가 True일 때 실행문
elif 조건식2:
    조건식1의 결과가 False이고, 조건식2의 결과가 True일 때 실행문
elif 조건식3:
    조건식1,2의 결과가 False이고, 조건식2의 결과가 True일 때 실행문
else :
    위의 조건식이 모두 False일 때의 
```

```py
if important >= 100:
    print('상')
elif important >= 50:
    print('중')
else :
    print('하')
```

- if문만 사용해도 결과는 같지만 비효율적이다
- 비교하지 않아도 되는것들까지 비교를 합니다. 
```py
if important >=100:
    print('상')

if important >= 50:
    print('중')
    
if important < 50:
    print('하')
```

# 실습문제

1.학생들에게 점수를 입력받아
점수가 100점 이하 90점 이상인 경우에는 A를 출력하고,<br>
점수가 90점 미만 80점 이상인 경우에는 B를 출력하고,<br>
점수가 80점 미만 70점 이상인 경우에는 C를 출력하고,<br>
점수가 70점 미만 60점 이상인 경우에는 D를 출력하고,<br>
점수가 60점 미만 인 경우에는 F를 출력하고<br>
0~100 이외의 수나 글자를 입력하면 잘못입력하셨습니다.<br>
라고 출력하는 프로그램을 만드시오<br>

```py
입력조건 : 점수는 0 이상 100 이하의 정수 값을 가집니다.

입력예시 1
90
출력 예시
A

입력 예시2
75
출력 예시2
C

if score <= 100 and score >= 90:
    print('A')
elif score < 90 and score >= 80:
    print('B')
elif score < 80 and score >= 70:
    print('C')
elif score < 70 and score >= 60:
    print('D')
elif score >=0 and score < 60:
    print('F')
else:
    print('잘못입력하셨습니다.')
```

2. 임의의 정수를 입력받은 뒤 해당 값이 3의 배수인지 아닌지를 판별하는 프로그램을 구현하세요
```
실행예

정수를 입력하세요>>> 14
14는 3의 배수가 아닙니다

정수를 입력하세요>>>15
15는 3의 배수입니다.
```

```py
number = int(input('정수를 입력하세요>>>'))

if number % 3 == 0:
    print(f'{number}는 3의배수입니다.')
else:
    print(f'{number}는 3의배수가 아닙니다.')
```

3. 임의의 정수 3개를 입력받아 그 중에서 가장 큰 수를 출력하는 프로그램을 구현하세요
```
실행예

정수1 입력>>>3
정수2 입력>>>1
정수3 입력>>>2

가장 큰 수는 3입니다.
```

```py
num1 = int(input('정수1을 입력하세요>>>'))
num2 = int(input('정수2을 입력하세요>>>'))
num3 = int(input('정수3을 입력하세요>>>'))

max = num1

if max <= num2:
    max = num2
    if max <= num3:
        max = num3
    
print(f'가장 큰 수는{max}입니다.')
```

# 반복문
- 반복문은 작업을 한번이 아니라 계속해서 수행해야할 때 사용합니다.

## 반복문의 종류
- while
- for

## while문
- while문은 특정 조건을 만족하는 동안 반복해서 수행해야 하는 코드를 작성할 때 사용합니다.

```
기본형

while 조건식:
  반복실행문
```

- if문에서는 조건식이 Ture라면 한번 실행하고 빠져나가 밑에있는 명령을 실행했다.
- 하지만 while문에서는 조건식이 참이라면 명령을 다시한번 실행한다.

- 1~10 사이의 모든 정수를 순서대로 출력하는 프로그램
```py
n = 1 -> 초기값
while n<=10: -> 조건식 : 반복하고자 하는 횟수
    print(n, end=' ')
    n+=1 -> 초기값의 증감
```

- 1~10 사이의 모든 정수를 역순으로 출력하는 프로그램
```py
n = 10
while n>=1:
    print(n, end=' ')
    n-=1
```

## while문이 필요한 경우
- 내가 몇번을 반복해야 끝나는지 모르는 경우가 있습니다.
- 이럴 때 while문이 정말 유용하게 사용됩니다.

- 사용자로부터 임의의 정수를 입력받아 모두 리스트에 보관합니다. 단, 사용자가 0을 입력하면 더이상 입력받지 않고 종료합니다.
- 이 때 0은 리스트에 보관하지 않습니다.

```py
my_list = []

n = int(input('정수를 입력하세요(종료는 0입니다.)>>>'))

while n != 0: -> 0을 입력하게 되면 조건이 거짓이 되서 빠져나오게 된다.
    my_list.append(n)
    n = int(input('정수를 입력하세요(종료는 0입니다.)>>>'))
    
print(my_list)
```
