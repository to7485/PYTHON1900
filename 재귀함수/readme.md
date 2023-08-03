# 재귀함수(Recursive call)
- 함수가 자기 자신을 다시 호출하는 구조
- 장점 : 프로그램을 구조적으로 작성 -> 간결하고, 이해하기 쉽게 작성 가능
- 단점 : 메모리 부담(오버헤드)이 발생

## 일반적인 함수의 작성과 호출
```py
def f():
  return f -> 선언부

f() -> 호출부
```

## 무한으로 작동하는 재귀함수
```py
def recursive(n):
   print(n, end=' ')
   revursive(n+1) # 함수 안에서 자기 자신을 호출
   print('함수 끝')

recursive(1)
```
- 1,2,3,4... 나오다가 오류나고 끝남
- 재귀호출을 할 때에는 종료조건을 적어줘야 한다.

## 종료조건을 명시한 재귀함수
```py
def recursive(n):
   if n == 3:
       return
   print(n, end=' ') # 호출이 이루어지기 전에 실행
   revursive(n+1) # 함수 안에서 자기 자신을 호출
   print('함수 끝') # 모든 호출이 끝나고 return되면서 돌아오면서 수행되는 구문

recursive(1)
```
recursive(1) -> 1 recursive(2) 호출 -> 1 2 recursive(3)-> 1 2 -> 1 2 함수끝 줄바뀌고 함수끝 호출

![image](https://github.com/to7485/PYTHON1900/assets/54658614/3ecaeb41-9384-4fb2-a709-1f4ab50ecb1c)

### 재귀함수의 원리
- 우선 함수의 선언과 호출에 대해서 다시 이해해야 한다.
- 함수는 호출이 되면 명령을 수행하고 다시 호출한곳으로 돌아간다.
- 함수는 호출될 때마다 스택 영역에 쌓인다.
- 모든 호출이 끝나고 마지막 명령부터 다시 돌아온다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/02cb8759-4a08-4e6f-9515-c481ca9aaf6e)

### 팩토리얼
```py
def f(x):
    if(x == 0):
        return 1
    return x*f(x-1)

for i in range(1,6):
    print(f(i),end=' ')
```
![image](https://github.com/to7485/PYTHON1900/assets/54658614/61f92d53-f00b-452a-8381-b7be43245a01)


### 피보나치 수열
```py
def f2(x):
    if(x == 0):
        return 0
    if(x == 1):
        return 1
    return f2(x-1) + f2(x-2)

for i in range(6):
    print(f2(i),end=' ')
```

![image](https://github.com/to7485/PYTHON1900/assets/54658614/8036a3e7-0a43-44fe-92c6-4ee703468ae9)




