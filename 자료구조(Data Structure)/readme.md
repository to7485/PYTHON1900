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
 
# 리스트(List)
- 대표적인 자료구조중 하나로 '줄 세워져 있는 데이터', '죽 늘어선 데이터'를 의미합니다.
- 서비스를 기다리는 사람의 리스트, 선물 받고 싶은 목록 등 리스트는 정말 다양합니다.
- 파이썬은 리스트를 기본 자료구조로 제공해 많은 작업들을 지원하고 있습니다.

## 리스트의 구현방법
1. 연결리스트(Linked List)
2. 배열 리스트(Array List)

### 배열리스트(파이썬 기본제공)
- 파이썬에서는 기본적으로 리스트 자료구조를 제공합니다.
- 우리는 그 내부가 어떻게 돌아가는지 알 필요 없이 사용법만 알고 사용하면 됩니다.

### 기본적으로 제공하는 기능
- insert(i,x) : x를 리스트의 i번째 원소로 삽입한다.
- append(x) : x를 리스트의 맨 뒤에 추가한다.
- pop(i) : 리스트의 i번 원수롤 삭제하고 삭제한 값을 반환한다.
- remove(x) : 리스트에서 x를 삭제한다.
- index(x) : 원소 x가 리스트의 몇 번째 원소인지 알려준다.
- clear() : 리스트를 깨끗하게 지운다.
- count(x) : 리스트에서 원소 x가 몇번 나타나는지 알려준다.
- extend(a) : 리스트에 나열할 수 있는 객체 a를 추가한다.
- copy() : 리스트를 복사한다.
- reverse() : 리스트의 순서를 역수능로 뒤집는다.
- sort() : 리스트의 원소를 정렬한다.

### 리스트의 작업
```py
li = []
li.insert(0,'test')
li.insert(0,'sample')
li.insert(1,'mid')
li.append('end')
print(li)
print('sample is at',li.index('sample'),"th")

print(li.pop(0))

print(li.pop(-1))

print(li)
```

<img width="282" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/61ae2d1a-3801-4483-b95c-ec4f54eb8c65">

### 파이썬 내장 리스트의 한계
- 파이썬 리스트는 배열로 구현이 되어있습니다.
- 우선 원소 삽입 시에 삽입하는 자리 오른쪽부터 끝까지 모든 원소를 한칸씩 시프트 해주는 부담이 있습니다.

![IMG_B8A2F04B8F60-1](https://github.com/to7485/PYTHON1900/assets/54658614/0f1141be-ccd3-40a8-bf36-ca0a4ddee3ad)

- 반대로 삭제에서는 반대 방향으로 시프트가 발생합니다.

<img width="394" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/f8b47b15-d59f-4c7d-b121-f9b99a7da0f5">

- 배열은 공간의 크기를 미리 정해서 받을 수 밖에 없습니다.
- 이때문에 받아놓은 공간이 꽉차있는 상태에서 삽입이 시도되면 배열의 한계를 넘어가 삽입을 할 수 없게 됩니다.
- 파이썬 리스트의 사용자 입장에서는 이런 불편을 느끼지 않고 사용할 수 있는데, 하부에서는 이런 경우에 대한 처리가 포함되어있기 때문입니다.
- 이럴 때는 새 배열을 할당받아 기존 배열의 내용을 새 배열로 복사하고 리스트가 새 배열과 매핑이 되도록 합니다.
- 이 복사의 부담은 삽입이나 삭제보다 큽니다.
- 사용자는 느끼지 못하지만 파이썬 기본 내장 리스트에는 이런 비효율성이 숨어있습니다.

<img width="374" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/8cddd334-a9c7-4b74-8fe9-bc78eaa91801">

## 연결리스트(Linked List)
- 리스트의 하부 구조로 배열을 사용할 경우 공간을 미리 확보해두고 시작해야 합니다.
- 리스트에 원소가 궁극적으로 얼마나 들어올지는 예상하기 쉽지 않으므로 많은 적든 공간 낭비가 불가피합니다.
- 공간을 낭비하지않으려면 배열의 크기를 빠듯하게 잡아놓아야 하는데 이 경우 다 차면 더 큰 배열을 할당받아 원소를 모두 옮겨주는 작업을 자주해야 함으로 상당히 번거롭습니다.
- 연결리스트는 배열의 공간 낭비를 피할 수 있는 자료구조입니다.
- 원소가 추가될 때마다 공간을 할당받아 추가하는 동적 할당 방식을 따르기 때문입니다.

## Node
- Node란 어떤 정보를 담고있는 하나의 단위로, 자료구조에서 개별적인 정보를 나타낼 때 사용하는 단위입니다.
- 노드는 정수나 실수 혹은 복잡한 객체가 들어갈 수 있는 item 필드
- 다음 노드를 가리키는 next필드가 존재합니다.

<img width="171" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/56f65e36-682c-45f5-a738-284dc833b397">

## 연결리스트의 작업
- 연결리스트의 작업들을 핵심 중심으로 소개하겠습니다.

## 노드의 생성
```py
#노드의 생성
class ListNode:
    def __init__(self, newItem, nextNode):
        self.item = newItem
        self.next = nextNode
```

## 리스트의 구현
```py
#리스트의 구현
class LinkedListBasic:
    def __init__(self):
        self.__head = ListNode('dummy',None)
        self.__numItems = 0
```

## 원소의 삽입
- 리스트 구현 클래스에 밑에 이어서 작성합니다.
- 연결리스트에서 중간에 노드를 삽입하려면 삽입 노드 바로 앞에 있는 녿, 즉 직전 노드를 가리키는 레퍼런스 prev가 있어야 합니다.
```py
    #원소 삽입
    def insert(self, i, newItem):
        if i >= 0 and i <= self.__numItems:
            prev = self.__getNode(i-1) # __getNode(i-1) : 삽입할 노드의 직전 노드
            newNode = ListNode(newItem,prev.next)
            prev.next = newNode #prev.next-> 다음 노드를 가리킨다.
            self.__numItems +=1
        else:
            print("index",i,":out of bound in insert()")

```

## i번째 노드 찾기
```py
    #i번째 노드 찾기
    def __getNode(self, i)->ListNode: # -> ListNode : 함수의 반환값을 명시
        curr = self.__head # 현재노드 : 더미헤드부터 탐색 ,index:-1
        for index in range(i+1):
            curr = curr.next
        return curr
```

## 원소 추가하기
```py
    #원소추가하기(append)
    def append(self,newItem):
        prev = self.__getNode(self.__numItems -1)
        newNode = ListNode(newItem, prev.next)
        prev.next = newNode
        self.__numItems +=1
```

## 원소 삭제하기
```py
    #원소 삭제하기
    def pop(self,i):
        if(i>=0 and i<=self.__numItems-1):
            prev = self.__getNode(i - 1)
            curr = prev.next
            prev.next = curr.next
            retItem = curr.item
            self.__numItems -=1
            return retItem
        else:
            return None
```

## value를 통해 원소 삭제하기
```py
    #value로 원소 삭제하기
    def remove(self,x):
        (prev,curr) = self.__findNode(x)
        if curr != None:
            prev.next = curr.next
            self.__numItems -= -1
            return x
        else:
            return None
```

## index를 통해 value 알려주기
```py
    #i번 원소 알려주기
    def get(self, i):
        if self.isEmpty():
            return None
        if(i >= 0 and i<=self.__numItems -1):
            return self.__getNode(i).item
        else:
            return None
```
## value가 리스트의 몇번 원소인지 알려주기
```py
    #x가 연결리스트의 몇번째 원소인지 알려주기
    def index(self,x)->int:
        curr = self.__head.next #0번노드 : 더미헤드 다음 노드
        for index in range(self.__numItems):
            if curr.item ==x:
                return index
            else:
                curr=curr.next
        return -12345 #안쓰는 인덱스
```

## 기타 작업들
```py

    #비었는지 검증하기
    def isEmpty(self) -> bool:
        return self.__numItems == 0

    #리스트의 사이즈 반환
    def size(self) -> int:
        return self.__numItems

    #리스트 비우기
    def clear(self):
        self.__head = ListNode("dummy",None)
        self.__numItems = 0
        
   def count(self,x) -> int:
        cnt = 0
        curr = self.__head.next #0번 노드
        while curr != None:
            if curr.item == x:
                cnt+=1
            curr = curr.next
        return cnt
        
    def extend(self,a):
        for index in range(a.size()):
            self.append(a.get(index))
            
    def copy(self):
        a = LinkedListBasic()
        for index in range(self.__numItems):
            a.append(self.get(index))
        return a
    
    def reverse(self):
        a = LinkedListBasic()
        for index in range(self.__numItems):
            a.insert(0,self.get(index))
        self.clear()
        for index in range(a.size()):
            self.append(a.get(index))
            
    def sort(self)->None:
        a = []
        for index in range(self.__numItems):
            a.append(self.get(index))
        a.sort()
        self.clear()
        for index in range(len(a)):
            self.append([index])
            
    def __findNode(self,x)->(ListNode,ListNode):
        prev = self.__head
        curr = prev.next
        while curr != None:
            if curr.item == x:
                return(prev,curr)
            else:
                prev = curr
                curr = curr.next
                return (None,None)
            
    def printList(self):
        curr = self.__head.next
        while curr != None:
            print(curr.item, end=' ')
            curr = curr.next
        print()
```
## 링크드 리스트 사용 예
```py
li = LinkedListBasic()
li.append(30); li.insert(0,20)
a = LinkedListBasic()
a.append(4);a.append(3);a.append(3),a.append(2);a.append(1);
li.extend(a)
li.reverse()
li.pop(0)
print('count(3) : ',li.count(3))
print("get(2) : ",li.get(2))
li.printList()
```

<img width="128" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/a318ea38-9be1-4cf5-83ce-c509634fe17c">

# 배열 리스트와 연결리스트의 차이

## 크기
- 배열 리스트 : 시작부터 고정된 크기를 지정한다.
- 연결 리스트 : 원소가 들어오는대로 공간을 할당받아 넣는다.
- 배열리스트는 정적이고 연결리스트는 동적이라고 할 수 있다.

## 연속성
- 배열 리스트 : 연속된 공간에 원소를 저장
- 연결 리스트 : 공간의 연속성이 없다.

## 탐색
- 이 차이로 인해 정렬이나 검색 작업을 할 때 배열 리스트보다 연결리스트에서 시간이 더 걸린다.
- 배열 리스트는 i번 원소를 찾을 때 i값으로 즉시 접근할 수 있다.
- 반면 연결리스트는 헤드 노드에서부터 시작하여 i번 원소를 찾아야 한다.
- 그러므로 배열 리스트는 O(1), 연결 리스트는 O(n)의 시간이 걸린다.

## 공간
- 연결 리스트에는 다음 원소의 링크를 위한 공간이 추가로 필요하다.
- 배열리스트에는 다음 원소에 대한 링크가 없으므로 원소 하나당 필요한 공간이 상대적으로 더 작다.
- 다만 배열에 들어올 총 원소의 수를 미리 알 수 없는 경우가 대부분이라 충분한 수의 원소를 소화할 수 있는 크기로 선언해야 해서 공간의 낭비가 불가피하다.
- 겉보기에는 배열의 비효율성이 보이지 않을 분이지 내부에서는 번거로운 작업을 감수해야 한다.


<hr>
<h1>구자료</h1>





- Linked List는 포인터가 존재한다. 포인터가 다른 노드를 가리키고 또 그 노드의 포인터가 다른 노드를 가리키고.. 이런형태를 갖고 있고 순서가 있다. 선형자료구조를 가지고 있다.
- 차이점은 포인터가 뒤로 넘어가는것만 해봤고 뒤에서 앞으로 오는거는 구현하지 않았다 포인터가 하나였는데 포인터가 두개가 존재하는걸 볼수 있다.

- 포인터가 하나면 싱글 링크드 리스트 포인터가 두개면 더블릭 링크드리스트 라고 한다.

- ArrayList라고 하는 파이썬에서는 존재하지 않는 문법이 있다.
- 배열형태를 리스트로 만든것.
- 이썬에서 리스트와 비슷하다고 생각을 하면 된다.
- 인덱싱을 이용해서 자료를 저장하거나 검색할 수 있었다.

- 링크드 리스트 중간 23 a 사이에 데이터를 삽입하고 싶다면 23에서 앞으로 향하는 포인터를 중간에 삽입할 노드를 가리키게 하고 a에서 23으로 오는 포인터를 중간에 삽입할 노드를 가리키게 하면 연결구조를 그대로 이어갈 수 있다.

- ArrayList 중간 23 a 사이에 데이터를 삽입하려고 하면 a부터 7a까지 모든 내용을 복사해서 한칸씩 뒤로 옮겨준다. 뒤에 데이터가 100만개 있으면 복사해서 한칸씩 뒤로 옮겨주는 일을 해야겠죠.

- 링크드 리스트의 단점은 n번째 인덱스에 있는 노드를 찾고 싶으면 처음부터 n번째까지 탐색을 해야한다.

- ArrayList의 경우 Array가 메모리에서 저장을 할 때 선형으로 저장이 된다.바로 옆에 있는 인덱스의 주소를 알고 있기 때문에 검색에 유리하다.

 
## Node


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














