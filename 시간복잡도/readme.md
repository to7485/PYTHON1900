# 복잡도
- 프로그램의 성능은 시간복잡도 (Time complexity)와 공간복잡도(Space Complexity)를 가지고 판단합니다
## 시간복잡도
- 입력하는 데이터의 변화에 따라서 연산 시간이 얼마나 걸리는지
## 공간복잡도
- 입력하는 데이터에 따라서 공간을 얼마나 차지하는지

### 복잡도의 특징
- 프로세스의 발전 속도가 빠르다는 점과 메모리를 추가설치하는 데에 드는 한계 비용이 적다는 점 때문에 공간 복잡도 보단 시간 복잡도가 상대적으로 더 중요합니다 시간.
- 복잡도는 자료구조와 알고리즘의 조합으로 결정되는데, 이 때 단위연산(문제 해결을 위한 주요한 동작)의 횟수를 통해 이를 파악합니다
- 시간 복잡도를 정량적으로 표현하는데 가장 많이 사용하는 지표는 빅오(Big-o) 표기법입니다.

## 입력하는 데이터의 개수(n)가 무한에 접근하면 무슨일이 일어날까?
```py
import time
from datetime import timedelta

def func1(n): # 0부터 n-1까지 더하는 함수
	total = 0;
	for I in range(n):
		total += I #단위 연산
	return total
```
```py
def check_time(func,num, title=’’):
	start = time.time()
	func(num)
	end = time.time()
	print(f’{title} : n = {num}, 경과시간 = {str(timedelta(seconds = end-start))}’)
--------------------------------
size = 10000
for I in range(5) :
	check_time(func1, size, ‘func1’)
	size *= 10

```
# Big-o 표기법
- 입력되는 데이터 n개에 비례해서 시간 복잡도가 증가(정비례)하는지 함수로 표현하는 표기법

![image](https://github.com/to7485/PYTHON1900/assets/54658614/156228dd-af0d-47a2-8a93-85e3ee3683da)

- x축은 입력되는 데이터의 양
- y축은 단위 연산의 횟수

## Big-O 표기법으로 나타내는 방법
1. n이 증가할 때 가장 빨리 증가하는 최고차항만 남기고 다른 항은 모두 생략한다.
2. 최고차항에 곱해진 상수도 생략한다.(최고차항의 계수도 생략한다.)
3. 남은 항에 O()안에 넣어 표기한다.

## O(1) : 일정한 복잡도(constant complexity)
- 일정한 복잡도(constant complexity)라고 하며, 입력값이 증가하더라도 시간이 늘어나지 않는다.
- 입력값의 크기와 관계없이, 즉시 출력값을 얻어낼 수 있다는 의미이다.
- 파이썬의 경우 index, 인덱싱, length, append, pop, clear
```py
def func0(n):
	return n
```
```py
def func0(n):
	n+=1
	n+=1
	n+=1
	return n
```

## O(n) : 선형 복잡도(linear complexity)
- 입력값이 증가함에 따라 시간 또한 같은 비율로 증가하는 것을 의미한다.
- 입력 크기가 두 배로 늘어나면 연산도 두 배로 증가한다.
- 비교, 삽입, 삭제, 복사 등

```py
def func1(n): # 0부터 n-1까지 더하는 함수
	total = 0;
	for I in range(n):
		total += I #단위 연산
	return total

```

## O(log n): 로그 복잡도(logarithmic complexity
- Big-O표기법중 O(1) 다음으로 빠른 시간 복잡도를 가진다.
- 입력 크기에 따라 탐색 범위를 반으로 나누거나, 이진 트리 구조를 활용하여 탐색을 효율적으로 수행한다.
- BST(Binary Search Tree)가 이에 해당
- BST에선 원하는 값을 탐색할 때, 노드를 이동할 때마다 경우의 수가 절반으로 줄어든다.

## O(nlogn) : 선형 로그 시간
- 입력 크기에 비례하여 연산이 증가하지만, 로그 함수의 형태로 증가한다.
- 입력 크기가 두배로 늘어나면 연산은 약간 더 많아지지만 비례적으로 늘어나지는 않는다.
- 병합정렬 : 리스트를 반으로 나누고, 나눠진 부분 리스트를 정렬한 후 병합하는 과정을 재귀적으로 수행한다.
- 파이썬의 sort()함수


## O(n**2) : 2차 복잡도(quadratic complexity)
- 입력값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가하는 것을 의미한다.
```py
def func2(n):
	total = 0;
	for I in range(n): 
		for j in range(n):
			total += 1 #단위 연산
	return total

# n이 100이 들어온다고 가정했을 때
# i가 0일때 j는 100번 수행 -> i가 1일때 j는 100번 수행 ...
# 총 100* 100 만큼의 연산이 수행된다.

size = 10000
for I in range(4) :
	check_time(func2, size, ‘func2’)
	size *= 10 
```
## o(2n**2) 수준의 복잡도
```py
def func2(n):
	total = 0;
	for I in range(n):
		for j in range(n):
			total += 1 #단위 연산
total += 1 #단위 연산 2(n**2)나 (n**2)이나 속도가 같다.
	return total

size = 10000
for I in range(4) :
	check_time(func2, size, ‘func2’)
	size *= 10
```
## o(4n**2) 
```py
def func2(n):
	total = 0;
	for I in range(n*2):
		for j in range(n):
			total += 1 #단위 연산
total += 1 #단위 연산 2(n**2)나 (n**2)이나 속도가 같다.
	return total

size = 10000
for I in range(4) :
	check_time(func2, size, ‘func2’)
	size *= 10
```


## O(2**n) : 기하급수적 복잡도(exponential complexity)
- Big-O 표기법 중 가장 느린 시간 복잡도를 가진다.
- 단위연산을 하는 횟수가 늘어나서 이런 프로그램은 만들면 안된다.
- 재귀로 구현하는 피보나치 수열은 O(2n)의 시간 복잡도를 가진 대표적인 알고리즘이다.

### big-O 표기법의 의의
- 프로그램의 성능이 아무리 나빠도 이정도 성능은 보장을 해주겠다.

