# 자료구조
- 자료구조(Data Structure)는 컴퓨터가 데이터를 효율적으로 다룰 수 있게 도와주는 <b>데이터 보관 방법과 데이터에 관한 연산의 총체</b>를 뜻한다.
- 예를들어 int도 자료구조이다. int는 32bit 메모리 공간 안에 수를 할당하되 첫 비트를 부호 표현에 사용하는 등의 '보관방법'을 정의하고 있고, 덧셈/뺄셈/나눗셈/곱셈/논리/시프트등 다양한 '연산' 또한 정의하고 있다.

## 자료구조의 종류
- 자료구조는 크게 선형과 비선형으로 나뉜다.
- 선형 자료구조의 경우 데이터가 일렬로 나열되어 있는것을 의미한다.
- 비선형 자료구조의 경우 특정한 형태를 띄는 것을 의미한다.

### 단순 자료구조
- 프로그래밍 언어에서 통상적으로 제공하는 기본 데이터 형식을 말한다.
    - int, float, bool, str 
### 복합 자료구조
- 선형 자료구조
    - 데이터 요소를 순차적으로 연결하는 자료구조로, 구현하기 쉽고 사용하기도 쉽다.
    - 배열(Array),링크드 리스트(Linked List), 스택(Stack), 큐(Queue)가 있다.
 
![image](https://github.com/to7485/PYTHON1900/assets/54658614/48c398e8-07cd-4fb4-816f-af060fc2f436)

- 비선형 자료구조
    - 데이터를 비 순차적으로 연결한다.
    - 한 데이터 요소에서 여러 데이터 요소로 연결되기도 하고, 여러 데이터 요소에서 하나의 데이터 요소로 연결되기도 한다.
    - 트리(Tree),그래프(Graph)가 있다.
 
![image](https://github.com/to7485/PYTHON1900/assets/54658614/ab5c43c5-09fa-4715-b641-eb2aff50b1fb)

- 자료구조의 종류

![image](https://github.com/to7485/PYTHON1900/assets/54658614/0a08c8f5-2f90-48cc-979d-50d66af93a6a)

## 자료구조 선택 기준
- 자료의 처리 시간
- 자료의 크기
- 자료의 활용 빈도
- 자료의 갱신 정도
- 프로그램의 용이성

## 자료구조의 특징
- 효율성
    - 자료구조 사용의 목적은 효율적인 데이터관리 및 사용이다.
    - 따라서 문제에 알맞은 자료구조를 사용한다면 업무 효율성이 증가한다.
- 추상화
    - 복잡한 자료, 모듈, 시스템 등으로부터 핵심적인 개념, 기능을 간추려 내는 것이다.
- 재사용성
    - 자료구조를 설계할 때 특정 프로그램에서만 동작하게 설계하지 않는다.
    - 다양한 프로그램에서 동작할 수 있도록 범용성 있게 설계해 다른 프로젝트에서 사용 또한 가능하다.
 
## Node
- Node란 어떤 정보를 담고있는 하나의 단위로, 자료구조에서 개별적인 정보를 나타낼 때 사용하는 단위입니다.
- 노드 간에는 연결이 가능하며 이는 주로 포인터(pointer)로 연결하곤 합니다.

### pointer
- 데이터가 저장되는 공간을 가리키는 변수를 의미합니다.
- 노드 간 연결을 포인터로 지정하여 연결해주기도 합니다.

### Class를 사용한 노드 만들기
- 기본적인 노드에서 각 개별 노드는 다음과 같은 정보를 가지고 있습니다.
  - 변수 : value, pointer
  - 메서드 : value 수정, value 검색, pointer 수정 등등
 
<img width="608" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/ed8f84ff-04b0-4461-820c-d7434486b383">

- 결국 자료구조라는건 노드를 담고있는 형태 가리킨다. 노드는 정보를 갖고 있다.
- 정보는 우리가 마음대로 설정할 수 있다.
- 노드는 포인터를 갖고 있다 포인터를 통해서 다른 노드를 가리킬 수 있다.
- 연결되지 않은 1개의 노드로도 자료구조가 될 수 있다.

```py
Class Node:
    countOfNode = 0 # 클래스변수
    def __init__(self, value= None, pointer=None):
		self.value = value
		self.pointer = pointer
		Node.countOfNode+=1 #클래스 변수의 사용

   def getData(self):
		return self.value
   def setData(self,value):
		self.value = value

n1 = Node(‘a’ None)
print(n1.getData())
n1.setData(‘b’)
print(n1.getData())

n1 = Node()
n2 = Node()
n3 = Node()
print(Node.countOfNode) #클래스 변수에 대해서 불러올 수 있다.
```

## pointer
```py
#pointer
n5 = Node(‘dog’,None)
n6 = Node(‘cat’, n5) #n5의 노드를 가리킨다.
print(n5.getData()) #dog
print(n6.getData()) #cat

#pointer의 활용
print(n6.pointer.getData())
n7 = Node(‘monkey’,n6)
n8 = Node(‘lion’, n6)
print(n8.pointer.pointer.getData())
print(n7.pointer.getData())
```

- 여러가지 모양으로 구조를 이룰 수 있다.
- 포인터가 꼬리를 물듯이 만든 모양을 리스트 라고 한다.
- 파이썬에서 리스트의 구조가 이런식으로 되어있다.
- 클래스를 만들어서 포인터에 포인터에 물고 물려서 만든 구조를 리스트, 좀더 덧붙이면 링크드 리스트라고 한다.
- 리스트라고 하는 클래스를 만들고 거기에 노드라고 하는 클래스를 사용을 해 볼것이다.


