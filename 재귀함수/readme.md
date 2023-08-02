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
   print(n, end=’ ‘)
   revursive(n+1) # 함수 안에서 자기 자신을 호출
   print(‘함수 끝’)
   return None;
```
recursive(1) -> 1 출력 recursive(2) 호출 -> 1 2 출력 recursive(3)-> 1 2 함수끝



