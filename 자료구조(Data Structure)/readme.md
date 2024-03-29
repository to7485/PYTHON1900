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

## 스택
- 스택은 '끝' 에서만 데이터에 접근하는 구조
### 생활속의 스택
- 접시가 쌓여있으면 맨 위에 있는 접시부터 사용해야 한다.
- 이런방식으로 데이터를 쌓고 빼는 자료구조가 스택이다.
- 가장 뒤에 들어온것이 가장 먼저 나가는 구조라는 뜻으로 LIFO(Last In First Out)이란 별칭이 붙었다.

<img width="246" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/a48dda4c-41dc-4816-96fc-5745582206a6">

### 스택을 활용한 예
- 키보드 입력을 하다가 백스페이스를 누르면 최근에 입력한 글이 지워진다.
- 한글,워드,파워포인트,액셀 등 모든 편집기는 최근에 작업한 순으로 취소하는게 가능하다.
- 프로그램에서 함수 A가 함수 B를 호출하고 함수 B는 함수 C를 호출하는 호출 체인은 나중에 각 함수가 끝나면 돌아갈 때 대비해서 호출 경로를 잘 관리해야 한다.

## 스택의 개념과 원리
- 스택은 맨 위의 원소만 접근 가능한 것이 특정이다.
- 스택의 맨 위 원소를 탑(Top)또는 스택 탑 원소라고 한다.
- 새 원소를 삽입할 때는 스택 탑 바로 윗자리에 원소를 저장한 후 새 원소가 새 스택탑이 되게 한다.
- 원소를 삭제할 때는 무조건 탑에 있는 원소를 삭제한 후 바로 아래 원소가 스택 탑이 되게 한다.

<img width="647" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/69a11c7f-b686-4e34-b661-08a322b0ad3c">

## 리스트를 이용한 스택의 구현
- 파이썬 내장 리스트를 스택의 하부 구조로 이용한다.
- 파이썬에서는 리스트가 기본으로 제공되어 이를 이용하면 코딩이 매우 간결해진다.

```py
class ListStack:
    def __init__(self):
        self.__stack=[]
```
## 원소 삽입
- 스택에 새 원소를 삽입할 때는 스탭 탑 바로 윗자리에 원소를 저장한다.
- 리스트에서는 맨 끝 원소 다음에 원소를 삽입하면 된다.
- 파이썬에는 리스트의 맨 끝에 원소를 추가하는 append()메서드가 있다.
```py       
    def push(self,x):
        self.__stack.append(x)
```
## 원소 삭제
- 스택에 있는 원소를 삭제할 때는 무조건 탑에 있는 원소를 삭제해야 한다.
- 리스트에 그냥 pop()을 하면 맨 끝 원소를 삭제하므로 그냥 호출하면 된다.

```py        
    def pop(self):
        return self.__stack.pop()
```

## 맨위의 원소 호출하기
- top()메서드는 단순히 리스트의 마지막 원소를 리턴한다.
- 스택이 비어있으면 알려줄 원소가 없음을 알린다.

```py
    def top(self):
        if self.isEmpty():
            return None
        else:
            return self.__stack[-1]
```
## 비어있는지 점검
- 스택이 비어있는지 확인하는 메서드
- bool() 함수는 다음과 같은 경우 False를 리턴하고 나머지는 모두 True를 리턴한다.
    - 객체가 비어있다: [],(),{}
    - 객체가 False
    - 객체의 값이 0
    - 객체가 None
```py       
    def isEmpty(self) -> bool:
        return not bool(self.__stack)
```
## 스택 비우기

```py    
    def popAll(self):
        self.__stack.clear()
```

```py        
    def printStack(self):
        print("Stack from top:",end=' ')
        for i in range(len(self.__stack)-1,-1,-1):
            print(self.__stack[i],end=' ')
        print()
```
```py
st1 = ListStack()
print(st1.top())
st1.push(100)
st1.push(200)
print("Top is",st1.top())
st1.pop()
st1.push('Monday')
st1.printStack()
print('isEmpty?',st1.isEmpty())
```

<img width="237" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/be6f193c-73b5-4b53-b16d-89257ab749c7">


## 연결 리스트를 이용한 스택
- 연결리스트 스택을 사용한다면 스택을 연결 리스트로 구성하고 연결 리스트의 어느 쪽을 스택 탑으로 삼을 것인지 결정해주면 된다.
- 연결리스트의 맨 앞을 스택탑으로 삼아보자.
```py
class LinkedStack:
    def __init__(self):
        self.__list = LinkedListBasic()
```

## 원소 삽입
- 링크드 리스트 맨 앞에 새 노드를 삽입하고 스탭 탑 레퍼런스를 새 노드로 바꿔주면 된다.
- 링크드 리스트의 맨 앞을 스택 탑으로 삼기로 했으므로 새 노드는 연결 리스트 __list의 맨 앞에 삽입되었다.

<img width="381" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/54f9ecc5-0c0e-46d3-82c2-067c86c10a84">

```py        
    def push(self,newItem):
        self.__list.insert(0,newItem)
```
## 원소 삭제
- 스택에서 원소를 삭제할 때는 무조건 스택 탑 원소를 삭제한다.
- 연결 리스트에서 pop(i)는 i번째 원소를 삭제하면서 리턴하므로
- pop(0)을 하면 스택 탑 원소를 삭제하면서 리턴한다.

```py
    def pop(self):
        return self.__list.pop(0)
```
## 스택 탑 리턴하는 메서드
- 스택이 비어있으면 알려줄 원소가 없음을 알린다.
```py
    
    def top(self):
        if self.isEmpty():
            return None
        else:
            return self.__list.get(0)
```

## 비어있는지 검증
- 연결 리스트가 비어있는지 보면 된다.
```py 
    def isEmpty(self)->bool:
        return self.__list.isEmpty()
```

## 완전히 비우기
```py    
    def popAll(self):
        self.__list.clear()
        
    def printStack(self):
        print("Stack from top:",end=' ')
        for i in range(self.__list.size()):
            print(self.__list.get(i), end=' ')
        print()
```

```py
st1 = LinkedStack()
st1.push(100)
st1.push(200)
print("Top is",st1.top())
st1.pop()
st1.push('Monday')
st1.printStack()
print('isEmpty?', st1.isEmpty())
```

<img width="226" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/8953791d-9928-4b9f-81eb-4ea0f6bbc59f">

# 큐
- 큐(Queue)는 줄을 의미하는 단어이다.
- 큐는 우리에게 익숙하기 때문에 리스트와 더불어 가장 쉽게 받아들일 수 있는 자료구조다.
- 가장 먼저 들어온 것이 가장 먼저 나가는 구조라는 뜻의 FIFO란 별칭을 가지고 있다.

## 예시
- 우리나라 항공사들이 고객이 쌓은 마일리지를 쓸 때 스택 방식으로 차감하였다.
- 그러다 보니 최근에 쌓은 마일리지가 먼저 차감되고 오래 전에 쌓은 마일리지의 유효 기간이 지나버려 못쓰게 되는 경우가 빈번하게 발생했다.
- 당국에서 개선 명령을 내려 지금은 큐 방식으로 차감하고 있다.

## 큐의 개념과 원리
- 큐의 맨 앞에 있는 원소를 front라 하고, 맨 뒤에 있는 원소를 tail이라고 한다.
- 큐에 삽입할때는 삽입할 원소를 알려주어야 하지만 삭제를 할 때는 단순히 삭제하라고 한다.
- 무조건 맨 앞에 있는 것을 삭제하기 때문이다.

<img width="342" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/1a52407f-3025-462e-aa86-58faca3365c2">

## 리스트를 이용한 큐
```py
class ListQueue:
    def __init__(self):
        self.__queue=[]
    
    def enqueue(self, x):
        self.__queue.append(x)
        
    def dequeue(self):
        if self.isEmpty():
            return None
        else:
            return self.__queue[0]
        
    def isEmpty(self) -> bool:
        return (len(self.__queue)==0)
    
    def dequeueAll(self):
        self.__queue.clear()
        
    def printQueue(self):
        print("Queue from front:",end=' ')
        for i in range(len(self.__queue)):
            print(self.__queue[i],end=' ')
        print()

q1 = ListQueue()
q1.enqueue("Mon")
q1.enqueue("Tue")
q1.enqueue(1234)
q1.enqueue("Wed")
q1.dequeue()
q1.enqueue('aaa')
q1.printQueue()
```

<img width="331" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/fffa7274-a85d-4bad-ba1c-2863345e452a">

## 연결리스트를 이용한 큐
- 자연스럽게 리스트의 맨 앞을 front로, 맨 뒤를 tail로 삼는다.

## 원소의 삽입
- 큐에 원소를 삽입할 때는 맨 뒤에 넣는다.
- 큐의 하부 구조로 사용되는 리스트의 맨 끝에 원소를 추가하면 된다.
- 이때 리스트의 맨 끝에 원소를 추가하는 작업 append()를 사용한다.

```py
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedListQueue():
    def __init__(self):
        self.front = None
        self.rear = None
```

## 추가하기
```py        
    def enqueue(self, data):
        new_node = Node(data)
        
        if self.front is None:
            self.front = new_node
            self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = self.rear.next
```

## 삭제
```py
    def dequeue(self):
        dequeue_object = None
        if self.isEmpty():
            print("Queue is Empty")
        else:
            dequeue_object = self.front.data
            self.front = self.front.next
            
        if self.front is None:
            self.rear = None
        return dequeue_object
```
## 가장 위에있는 데이터 찾기

```py    
    def peek(self):
        front_object = None
        if self.isEmpty():
            print("Queue is Empty")
        else:
            front_object = self.front.data            
        return front_object
```

## 비어있는지 검증하기

```py    
    def isEmpty(self):
        is_empty = False
        if self.front is None:
            is_empty = True
        return is_empty
```

## 라이브러리를 이용한 큐 구현
- 파이썬의 collections 라이브러리는 유용한 자료구조를 제공하는 표준 라이브러리이다.
- 그 중 많이 사용되는 deque가 있다.

### deque 메서드
|기능|메서드명|
|----|--------|
|가장 앞쪽에 원소 추가|appendleft(x)|
|가장 뒤쪽에 원소 추가|append(x)|
|가장 앞쪽에 있는 원소 제거|leftpop()|
|가장 뒤쪽에 있는 원소 제거|pop()|

```py
from collections import deque
queue = deque([])
print(queue)

queue.append(1)
queue.append(2)
print(queue)

x = queue.popleft()
print(queue, x)
```

## 백준 2161번 문제

![image](https://github.com/to7485/PYTHON1900/assets/54658614/7783f330-1193-4dc1-911c-6a8d5a624f77)

```py
from collections import deque

n = int(input())
queue = deque([])
for i in range(1, n+1):
    queue.append(i)
    
print(queue)

while len(queue) != 1:
    queue.popleft()
    x = queue.popleft()
    queue.append(x)
    print(queue)
print(queue[0])

6
deque([1, 2, 3, 4, 5, 6])
deque([3, 4, 5, 6, 2])
deque([5, 6, 2, 4])
deque([2, 4, 6])
deque([6, 4])
deque([4])
4
```

# 정렬(sort)
- 전렬 알고리즘은 n개의 숫자가 주어졌을 때, 이를 사용자가 지정한 기준에 맞게 정렬하여 출력하는 알고리즘 입니다.
- 예를 들어 n개의 숫자가 저장되어 있는 리스트를, 오름차순의 조건으로 작성하여 입력하면 오름차순으로 정렬된 리스트를 출력으로 구할 수 있습니다.
- 다양한 정렬 알고리즘이 존재하고 수행시간도 각각 천차 만별입니다.
1. 삽입 정렬 *
2. 선택 정렬 *
3. 버블 정렬
4. 퀵 정렬….

## 선택정렬
- 이름에 맞게 현재 위치에 들어갈 값을 찾아 정렬하는 알고리즘이다.
- N개의 요소가 주어질 때
1. 처음부터 ... N-1 범위에서 가장 작은 값의 위치(min_idx)를 찾아 선택한다.
2. 위에서 선택한 min_idx번째와 i번째의 데이터를 교환한다.
3. i는 1씩 누적시켜가며 증가시킨 뒤 i가 N-2가 될 때까지 step1 ~ step2를 반복한다.

<img width="321" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/9a2e6d38-982e-47b3-b411-6d4589b92eb1">

```py
[29,10,14,37,13]
[10,29,14,37,13] 1번째 사이클 후
[10,13,14,37,29] 2번째 사이클 후
[10,13,14,37,29] 3번째 사이클 후
[10,13,14,29,37] 4번째 사이클 후
```

```py
연습
[11,3,28,43,9,4]		-> 3과 11 비교
[3|,11,28,43,9,4] 1번째 사이클 이후 -> 4와 11 비교
[3,4|,28,43,9,11] 2번째 사이클 이후 -> 9와 28 비교
[3,4,9|,43,28,11] 3번째 사이클 이후 -> 11과 43 비교
[3,4,9,11|,28,43] 4번째 사이클 이후 -> 28과 11 비교
[3,4,9,11,28|,43] 5번째 사이클 이후
```

### 코드로 구현하기
```py
def selectionSort(seq):
	N = len(seq)
	for i in range(N-1): #N-1만큼 사이클을 돈다.
		# i번째부터 시작해서 끝까지의 최솟값을 찾는다.
		# 최솟값의 위치(min_idx)를 선택!
		min_idx = i
		for j in range(i+1, N):
			if seq[min_idx] > seq[j]: #더 적은 값이 등장하면
				min_idx = j #최솟값 갱신
		# 선택된 min_idx번째 데이터와 i번째 데이터 교환
		seq[min_idx], seq[i] = seq[i], seq[min_idx]
		print(seq, f'{i+1}번째 사이클 후')
	return seq

seq = [11,3,28,43,9,4]
seq = selectionSort(seq)
print(seq)
```

<img width="287" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/b5a44f9c-b7a3-4aa9-a51f-28a472c07087">

## Insertion Sort(삽입정렬)
1. 삽입정렬은 두번째 인덱스부터 시작한다. 현재 인덱스는 별도의 변수에 저장해주고, 비교 인덱스를 현재 인덱스 -1로 잡는다.
2. 별도로 저장해둔 삽입을 위한 변수와, 비교 인덱스의 배열 값을 비교한다.
3. 삽입 변수의 값이 더 작으면 현재 인덱스로 비교 인덱스의 값을 저장해주고 비교 인덱스를 -1하여 비교를 반복한다.
4. 만약 삽입 변수가 더 크면, 비교 인덱스+1에 삽입 변수를 저장한다.

<img width="236" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/fc1d0d58-60ac-45aa-aa26-286372b070a9">

```py
연습
[11,3,28,43,9,4]	       -> 3과 11 비교		i = 1	j = 0
[3,11,28,43,9,4] 1번째 사이클 이후 -> 28과 11 비교		i = 2	j = 1
[3,11,28,43,9,4] 2번째 사이클 이후 -> 43과 28 비교		i = 3	j = 2
[3,11,28,43,9,4] 3번째 사이클 이후 -> 9와 43,28,11,3 비교	i = 4	j = 3,2,1,0
[3,9,11,28,43,4] 4번째 사이클 이후 -> 4와 43,28,11,9,3 비교	i = 5   j = 4,3,2,1,0
[3,4,9,11,28,43] 5번째 사이클 이후
```

### 코드로 구현
```py
def insertionSort(seq):
	# 1부터 len(seq)-1 만큼 사이클 횟수
	for i in range(1, len(seq)): 
		insData = seq[i] #반복문을 돌면서 요소를 insData로 잡는다.
		j = i-1
		while j>= 0: #삽입할 위치 찾기
			if seq[j] <= insData: 
			#왼쪽에 있는 값과 insData의 값을 비교해서 참이라면 거기서 탐색 종료를 하겠다.
				break
			seq[j+1] = seq[j]
			j -= 1
		seq[j+1] = insData
		print(seq,f'{i}번째 사이클 후')
	return seq

seq = [11,3,28,43,9,4]

insertionSort(seq)
```

<img width="294" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/9e057f0b-8bf7-4b4f-b671-e62de8425dd2">

## 버블정렬
- 매번 연속된 두 개의 인덱스를 비교하여, 정한 기준의 값을 뒤로 넘겨 정렬하는 방법이다.
- 오름차순으로 정렬하고자 할 경우, 비교시마다 큰 값이 뒤로 이동하여, 1바퀴 돌 시 가장 큰 값이 맨 뒤에 저장된다.
- 맨 마지막에는 비교하는 수들 중 가장 큰 값이 저장 되기 때문에, (전체 배열의 크기 - 현재까지 순환한 바퀴수 )만큼 반복해주면 된다.

### 로직
- 주어진 N개의 배열에 대해
1. 인접한 두개의 데이터(a,b)비교
2. 오름차순의 경우 a>b라면 값 교환
3. 배열 끝까지 다다를 때까지 1번과 2번을 반복
4. 마지막 비교는 N-2와 N-1을 비교한다.
5. 3번이 끝나면 맨 끝의 데이터는 가장 큰 값이 될 것이다.
6. N을 1씩 감소하고 N이 1이 될 때까지 1번부터 반복한다.

<img width="360" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/ca488227-a74d-473d-bace-1f7b491f17f2">

```py
[3,2,7,5,6] 			2,3 -> 3,7 -> 7,5 -> 7,6 비교
[2,3,5,6,7] 1번재 싸이클 후
[2,3,5,6,7] 2번재 싸이클 후
[2,3,5,6,7] 3번재 싸이클 후
[2,3,5,6,7] 4번재 싸이클 후

버블정렬이 비효율적인 경우 1번째 사이클을 통해 정렬이 완료되었음에도 불구하고 의미없는 정렬을 계속 하게 된다.
```
### 연습
```py
[11,3,28,43,9,4]
[3,11,28,9,4,43] 1번째 사이클 후
[3,11,9,4,28,43] 2번재 사이클 후
[3,9,4,11,28,43] 3번째 사이클 후
[3,4,9,11,28,43] 4번째 사이클 후
[3,4,9,11,28,43] 5번째 사이클 후
```

## 버블정렬 구현
```py
def bubbleSort(seq):
	length = len(seq) - 1
	for num in range(length, 0 , -1) : #cycle 횟수
		for i in range(num): #비교 횟수
			if seq[i] > seq[i+1] : # 왼쪽이 오른쪽 보다 크다면 값의 위치를 바꾼다.
				seq[i], seq[i+1] = seq[i+1], seq[i]
		print(seq, f'{length - num + 1} 번째 사이클 후')
	return seq

seq = [11,3,28,43,9,4]

bubbleSort(seq)
```

<img width="303" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/a3d48bb6-ef45-4e68-8557-dd29bf6ea2aa">

## 퀵정렬
- 기준 데이터를 설정하고 그 기준보다 큰 데이터와 작은 데이터의 위치를 바꾸는 방법이다
- 일반적인 상황에서 가장 많이 사용되는 정렬 알고리즘 중 하나이다
- 병합 정렬과 더불어 대부분의 프로그래밍 언어의 정렬 라이브러리의 근간이 되는 알고리즘이다
- 가장 기본적인 퀵 정렬은 첫 번째 데이터를 기준 데이터(Pivot)로 설정한다

## 퀵 정렬 동작 예시
- [Step 0] 현재 피벗의 값은 '5'이다. 왼쪽에서부터 '5'보다 큰 데이터를 선택하므로 '7'이 선택되고
오른쪽에서부터 '5'보다 작은 데이터를 선택하므로 '4'가 선택된다. 이제 이 두 데이터의 위치를 서로 변경한다

![image](https://github.com/to7485/PYTHON1900/assets/54658614/0dbe6fc8-dcb4-4282-b88f-b62a336867f9)

- [Step 1] 현재 피벗의 값은 '5'이다. 왼쪽에서부터 '5'보다 큰 데이터를 선택하므로 '9'가 선택되고
오른쪽에서부터 '5'보다 작은 데이터를 선택하므로 '2'가 선택된다. 이제 이 두 데이터의 위치를 서로 변경한다

![image](https://github.com/to7485/PYTHON1900/assets/54658614/d4a2088f-1a31-40ff-bb49-141576235908)

- [Step 2] 현재 피벗의 값은 '5'이다. 왼쪽에서부터 '5'보다 큰 데이터를 선택하므로 '6'이 선택되고
오른쪽에서부터 '5'보다 작은 데이터를 선택하므로 '1'이 선택된다. 단, 이처럼 위치가 엇갈리는 경우 '피벗'과
'작은 데이터'의 위치를 서로 변경한다


![image](https://github.com/to7485/PYTHON1900/assets/54658614/f429fbb8-63b3-4d89-9998-fb64656e2c83)

- [분할 완료] 이제 '5'의 왼쪽에 있는 데이터는 모두 5보다 작고, 오른쪽에 있는 데이터는 모두 '5'보다 크다는
특징이 있다. 이렇게 피벗을 기준으로 데이터 묶음을 나누는 작업을 분할(Divide)이라고 한다

![image](https://github.com/to7485/PYTHON1900/assets/54658614/1478030a-3670-42ae-a905-543d8c34ba41)

- [왼쪽 데이터 묶음 정렬] 왼쪽에 있는 데이터에 대해서 마찬가지로 정렬을 수행한다

![image](https://github.com/to7485/PYTHON1900/assets/54658614/951f1c84-3cec-48be-957a-295bafc3c64c)

- [오른쪽 데이터 묶음 정렬] 오른쪽에 있는 데이터에 대해서 마찬가지로 정렬을 수행한다
    - 이러한 과정을 반복하면 전체 데이터에 대해서 정렬이 수행된다

![image](https://github.com/to7485/PYTHON1900/assets/54658614/209bac01-9377-4d96-9a38-5d933e6eace0)

## 퀵 정렬이 빠른 이유
- 직관적인 이해가 빠르기 때문이다.
- 이상적인 경우 분할이 절반씩 일어난다면 전체 연산 횟수로 O(NlogN)의 복잡도를 기대할 수 있다.
    - 너비 X 높이 = N X logN = NlogN
 
![image](https://github.com/to7485/PYTHON1900/assets/54658614/0789e803-69ca-4d74-8bf2-17fcb975cfb5)

## 퀵 정렬 소스코드
```py
array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8]

def quick_sort(array, start, end):
    if start >= end: # 원소가 1개인 경우 종료
        return
    pivot = start # 피벗은 첫 번째 원소
    left = start + 1
    right = end
    while(left <= right):
        # 피벗보다 큰 데이터를 찾을 때까지 반복 
        while(left <= end and array[left] <= array[pivot]):
            left += 1
        # 피벗보다 작은 데이터를 찾을 때까지 반복
        while(right > start and array[right] >= array[pivot]):
            right -= 1
        if(left > right): # 엇갈렸다면 작은 데이터와 피벗을 교체
            array[right], array[pivot] = array[pivot], array[right]
        else: # 엇갈리지 않았다면 작은 데이터와 큰 데이터를 교체
            array[left], array[right] = array[right], array[left]
    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행
    quick_sort(array, start, right - 1)
    quick_sort(array, right + 1, end)

quick_sort(array, 0, len(array) - 1)
print(array)
```

### 파이썬의 장점을 살린 방식
```py
array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8]

def quick_sort(array):
    # 리스트가 하나 이하의 원소만을 담고 있다면 종료
    if len(array) <= 1:
        return array

    pivot = array[0] # 피벗은 첫 번째 원소
    tail = array[1:] # 피벗을 제외한 리스트

    left_side = [x for x in tail if x <= pivot] # 분할된 왼쪽 부분
    right_side = [x for x in tail if x > pivot] # 분할된 오른쪽 부분

    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬을 수행하고, 전체 리스트를 반환
    return quick_sort(left_side) + [pivot] + quick_sort(right_side)

print(quick_sort(array))
```

# 탐색
- 데이터를 검색하여 찾는것을 의미합니다.

## 탐색 유형
- 순차 탐색
- 이진 탐색

```
[‘a’,2,’g’,3,5] 여기에 알파벳 g가 있는지 없는지 확인하기 위해서 어떻게 해야 할까?
```

### 순차탐색
```py
for i in ['a',2,'g',3,5]:
	if 'g' == i:
		print('g 찾음')
```

### 순차탐색 vs 이진탐색

<img width="472" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/13846c54-2f36-4d2b-aa2b-32aa4454eed8">

### 순차탐색의 단점
- 없는 데이터를 찾으려고 해도 끝까지 훑고나서 없다고 한다. 데이터가 100만개라면 어떻게 할것인가?

## 이진탐색
- 데이터가 정렬되어있다는 가정이 필요하다.
- 절반을 떼어서 확인한다.
- J는 L보다 앞에 있기 때문에 L의 뒤는 아예 탐색하지 않는다. 그리고 또 절반 또 절반을 탐색한다.
- log n의 시간복잡도를 가지고 있다.

```py
seq1 = []
seq2 = []
for I in range(1,10000000):
	seq1.append(i) # 오름차순 정렬
	seq2.append(10000000 -i) # 내림차순 정렬

#시간 체크 함수
import time
from datetime import timedelta

#func의 수행시간 체크
def checkTime(func, seq, value, title=''):
	start = time.time()
	func(seq,value)
	end = time.time()
	print(f'{title} : value = {value} 경과시간 {str(timedelta(seconds = end - start))}')


def binarySearch(seq,value):
	# 시작 인덱스와 끝 인덱스
	start = 0
	end = len(seq) -1 	while start <= end:
		mid = (start+end) // 2
		if seq[mid] < value:
			start mid + 1
		elif seq[mid] > value:
			end = mid -1
		else:
			return mid

print(binarySearch(seq1,100))
print(binarySearch(seq1,10000))
print(binarySearch(seq1,1000000))

for cnt in [10000,100000,1000000,99999999]:
	checkTime(binarySearch, seq1, cnt, ‘오름차순 정렬된 배열 순차 탐색’)
	checkTime(binarySearch, seq1, cnt, ‘내림차순 정렬된 배열 순차 탐색’)
	print()

```
# 트리
- 트리는 나무를 닮은 자료구조이다.
- 나무에는 뿌리가 있고 뿌리에서는 가지가 뻗어나오며 가지의 끝에는 잎이 달린다.
- 이러한 나무의 구조를 사람들이 다양한 형태로 응용을 하고 있다.
- 기업에서 전략을 수립할 때 사용하는 의사 결정트리, 게임의 성장 시스템에 사용되는 스킬 트리가 그 예이다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/572ac3eb-80f5-4d3e-95a8-7894fb5bf3e5)

- 현실의 나무는 뿌리가 땅 속에 있고 가지가 위로 뻗어나가는 모습이다.
- 하지만 소프트웨어를 비롯한 추상 세계에 서식하는 트리는 뿌리가 심어진 곳이 따로 없기 때문에 가지가 위에서 아래로 뻗어나가는 그림으로 표현된다.

## 트리의 개념
1. 트리는 하나의 루트 노드를 갖는다.
2. 루트 노드는 0개 이상의 자식 노드를 갖고 잇다.
3. 그 자식 노드 또한 0개 이상의 자식 노드를 갖고 있고, 이는 반복적으로 정의된다.

<img width="462" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/f2f2a2f2-4af1-4b1e-8217-29d66810b306">

### 트리 관련 용어
- 루트 노드(root node) : 부모가 없는 노드, 트리는 하나의 루트 노드만을 가진다.
- 단말 노드(leaf node) : 자식이 없는 노드, ‘말단 노드’ 또는 ‘잎 노드’라고도 부른다.
- 내부 노드(internal) 노드 : 단말 노드가 아닌 노드
- 간선(edge) : 노드를 연결하는 선(link, branch라고도 부름)
- 형제(sibling) : 같은 부모를 가지는 노드
- 노드의 크기(size) : 자신을 포함한 모든 자손 노드의 개수
  
<img width="510" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/8bb53555-d900-4c39-bf3a-2c923ca3eb86">

- 트리의 높이(height) : 한 노드와 단말 노드 사이의 최대 깊이
- 노드의 깊이(depth) : 루트에서 어떤 노드에 도달하기 위해 거쳐야 하는 간선의 수

<img width="510" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/617e7f5a-8479-414b-a923-c1f833d69fba">

- 노드의 레벨(level) : 트리의 특정 깊이를 가지는 노드의 집합(depth)가 같은 노드의 집합
- 노드의 차수(degree) : 하위 트리 개수/ 간선수(degree) = 각 노드가 지닌 가지의 수
- 트리의 차수(degree of tree) : 트리의 최대 차수

## 일상생활에서의 트리
- 비선형 자료구조의 계층적 관계를 표현한다.
    - ex) 디렉토리 구조, 조직도
 

<img width="418" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/91500bc3-0d30-4163-b8ac-250a835e58b0">


## 트리 응용 분야
1. Expression Tree(수직 트리)
	1. 입력 수식 평가(evaluation)

 <img width="510" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/f8a28f4b-f5f4-4e0c-85c2-48251d233a02">

2. 허프만 트리
    1. 압축 알고리즘 : 얼마나 자주 등장하는지에 따라서 트리구조로 만든 것
3. 의사결정 트리
    1. 머신러닝, 인공지능 분야를 배우면 가장 먼저 배우는 알고리즘
<img width="463" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/edc49b72-a388-4316-bc67-124504a1e225">

4. 최대힙, 최소힙
    1. 최대값, 최소값 찾기 알고리즘
5. Document Object Model(DOM)
    1. 웹문서(HTML,XML...)

<img width="510" alt="image" src="https://github.com/to7485/PYTHON1900/assets/54658614/01b9dc68-2eac-4906-8bad-8bae664c4488">

## 이진트리
- 하나의 노드가 N개의 자식 노드를 가질 수 도 있다.
- 이진트리는 하나의 노드가 자식 노드를 2개까지만 가질 수 있는 트리이다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/a592579f-3cdb-4529-8a23-b91b5deea0d1)

### 이진트리의 상태
1. 포화 이진 트리
    - 잎 노드를 제외한 모든 노드가 자식을 둘씩 가진 이진 트리

![image](https://github.com/to7485/PYTHON1900/assets/54658614/0d03ff16-4fe4-4c5f-9952-940556167537)

2. 완전 이진 트리
    - 잎 노드들이 트리 왼쪽부터 채워지고 있는 모습이 특징이다.
  
![image](https://github.com/to7485/PYTHON1900/assets/54658614/755f5e63-c8a3-44f3-b292-21105eba44cc)

    - 다음과 같은 모습은 완전 이진 트리가 아니다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/a2160ab3-f475-4175-8375-2ff08619fcf8)

- 이진 트리는 일반 트리처럼 나무 모양의 자료를 담기 위한 자료구조가 아니라 컴파일러나 검색과 같은 알고리즘의 뼈대가 되는 특별한 자료구조다.
- 특히 이진트리를 이용한 검색에서는 트리의 노드를 가능한 한 완전한 모습으로 유지해야 높은 성능을 낼 수 있다.

## 트리의 구현
1. 딕셔너리 사용
```py
tree = {}
tree[1] = [2,3]
tree[2] = [4,5]
tree[3] = [6,7]
tree[4] = [8]
print(tree[1]) # [2,3]
print(tree[tree[1][0]]) #tree[1][0] -> 2  / tree[2] -> [4,5]
```

2. 클래스 사용하기
```py
class Node:
	def __init__(self,value = None, pointer = None):
		self.value = value
		self.pointer = pointer

class NodeBT:
	def __init__(self,value=None):
		self.value = value
		self.left = None #left subtree
		self.right = None # right subtree

	def __repr__(self):
		return f'{self.value}'

bt1 = NodeBT(1)
bt2 = NodeBT(2)
bt3 = NodeBT(3)
bt4 = NodeBT(4)
bt5 = NodeBT(5)
bt6 = NodeBT(6)

bt1.left = bt2
bt1.right = bt3
bt2.left = bt4
bt2.right = bt5
bt3.left = bt6

print(bt1.left.right)
```

# 힙
- 데이터에서 최댓값과 최솟값을 빠르게 찾기 위해 고안된 완전 이진 트리(Complete Binary Tree)를 사용한 자료구조이다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/bc49fa8c-b88d-49b6-8ee2-4845e0710ccb)

- 부모 노드의 인덱스는 1로, 왼쪽 자식 노드부터 2,3 순서이다.
    - 부모 노드의 인덱스 = 자식 노드 인덱스 // 2
    - 왼쪽 자식 노드의 인덱스 = 부모 노드의 인덱스 * 2
    - 오른쪽 자식 노드의 인덱스 = 부모 노드의 인덱스 * 2 + 1

## 힙을 사용하는 이유
- 최솟값이나 최댓값을 찾기 위해 배열을 사용하면 O(n)만큼 시간이 걸린다.
- 하지만 힙을 사용하면 O(logn)만큼 소요되므로, 배열을 사용할 때보다 빠르게 최솟값과 최댓값을 구할 수 있다.
- 우선순위 큐와 같이 최댓값 또는 최솟값을 빠르게 찾아야 하는 알고리즘 등에 활용된다.

## 힙의 특징
1. 노드가 왼쪽부터 채워지는 완전 이진 트리 형태를 가진다.
2. 중복을 허용한다.

## 힙의 종류
- 힙은 최대힙(Max heap)과 최소힙(Min heap)으로 나뉜다.
### 최대 힙(Max heap)
- 부모 노드의 값이 자식 노드의 값보다 크거나 같은 완전 이진 트리

![image](https://github.com/to7485/PYTHON1900/assets/54658614/d450b17d-a3a3-4b11-8cb2-372589b10c66)

### 최소 힙(Min heap)
- 부모 노드의 값이 자식 노드의 값보다 작거나 같은 완전 이진 트리

![image](https://github.com/to7485/PYTHON1900/assets/54658614/ac343219-aa7f-46fe-a54c-df806459900c)


## 구현하기
- 최대힙을 구현해보자.
- 루트의 인덱스 번호를 1로 하기 위해, 리스트의 0번째 자리에 None을 넣는다.
```py
class Heap:
    def __init__(self):
        self.heap = []
        self.heap.append(None)
```

### 삽입하기
- 데이터를 삽입할 때, 맨 뒤부터 차례대로 저장한다.
- 만약 삽입한 데이터가 부모보다 클 경우, 부모와 위치를 바꿔줘야 한다.
```py
    # 해당 노드가 부모 노드보다 큰지 비교
    def check_swap_up(self, idx):
        # 삽입한 모드의 부모 노드가 없을 경우
        if idx <= 1:
            return False

        parent_idx = idx // 2

        if self.heap[idx] > self.heap[parent_idx]:
            return True
        else:
        return False

    # 데이터 삽입
    def insert(self, data):
        self.heap.append(data)
        idx = len(self.heap) - 1

        # check_swap_up() 의 값이 참이라면 부모와 위치 바꾸기
        while self.check_swap_up(idx):
            parent_idx = idx // 2

            self.heap[idx], self.heap[parent_idx] = self.heap[parent_idx], self.heap[idx]
            idx = parent_idx

        return True
    
    # 해당 노드가 부모 노드보다 큰지 비교
    def check_swap_down(self, idx):
        left_idx = idx * 2
        right_idx = idx * 2 + 1

        # 자식 노드가 하나도 없을 경우
        if left_idx >= len(self.heap):
            return False

        # 왼쪽 자식 노드만 있을 경우
        elif right_idx >= len(self.heap):
            if self.heap[left_idx] > self.heap[idx]:
                self.flag = 1
                return True
            else:
                return False

        # 자식 노드가 모두 있을 경우
        else:
            if self.heap[left_idx] > self.heap[right_idx]:
                if self.heap[left_idx] > self.heap[idx]:
                    self.flag = 1
                    return True
                else:
                    return False
            else:
                if self.heap[right_idx] > self.heap[idx]:
                    self.flag = 2
                    return True
                else:
                    return False
```

### 삭제하기
- 최댓값을 꺼내면 루트 노드가 비어있게 된다.
- 가장 마지막 노드와 루트 노드의 자리를 바꾼 뒤, 자식 노드와 값을 비교한다.
- 만약 루트 노드가 자식 노드보다 더 작을 경우, 자식과 위치를 바꾼다.
```py
    # 데이터 삭제
    def pop(self):
        if len(self.heap) <= 1:
            return None

        max = self.heap[1]
        self.heap[1] = self.heap[-1]
        del self.heap[-1]
        idx = 1

        # 0 = False, 1 = (왼쪽 자식과 swap), 2 = (오른쪽 자식과 swap)
        self.flag = 0 

        while self.check_swap_down(idx):
            left_idx = idx * 2
            right_idx = idx * 2 + 1

            if self.flag == 1:
                self.heap[idx], self.heap[left_idx] = self.heap[left_idx], self.heap[idx]
                idx = left_idx
            elif self.flag == 2:
                self.heap[idx], self.heap[right_idx] = self.heap[right_idx], self.heap[idx]
                idx = right_idx
        return max
```

## 힙의 동작

### 데이터의 삽입
- 힙은 완전 이진 트리이기 때문에, 삽입할 노드는 기본적으로 왼쪽 최하단 노드부터 채워진다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/5e4cf8ae-fa36-4861-94ca-360c7b654030)

1. 15를 왼쪽 최하단 노드에 삽입한다.
2. 10을 왼쪽 최하단 노드에 삽입한뒤, 부모와 비교한다. 부모보다 작으므로 그 자리에 위치한다.
3. 왼쪽 최하단 노드가 이미 있으므로 8을 오른쪽 최하단 노드에 삽입한 뒤, 부모와 비교한다. 작으므로 그 자리에 위치한다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/7daa7dc4-51f5-485a-b06a-c606ea2bc723)

4. 3을 왼쪽 최하단 노드에 삽입한 뒤, 부모와 비교한다. 부모보다 작으므로 그 자리에 위치한다.
5. 왼쪽 최하단 노드가 이미 있으므로 4를 오른쪽 최하단 노드에 삽입한 뒤, 부모와 비교한다. 부모보다 작으므로 그 자리에 위치한다.

### 힙의 데이터보다 클경우

![image](https://github.com/to7485/PYTHON1900/assets/54658614/78dd05af-5f83-4770-b99e-86f610199e60)

1. 20을 왼쪽 최하단부 노드에 삽입한다.
2. 20의 부모 노드인 8과 비교한다. 20이 더 크므로 8과 위치를 바꾼다. (swap)

![image](https://github.com/to7485/PYTHON1900/assets/54658614/646a8dfd-2bc4-4265-80df-a3fcef4cada1)

3. 20의 부모 노드인 15와 비교한다. 20이 더 크므로 15와 위치를 바꾼다. (swap)

### 데이터 삭제
- 힙 자료구조의 목표는 바로 최대값이나 최소값을 알아내는것이다.
- 데이터가 삭제 된다면 가장 큰 값인 부모 노드의 값이 삭제된다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/4ead9c8f-723a-48b4-8853-fa2197521597)

1. 최대값을 갖는 부모 노드를 삭제한다.

![image](https://github.com/to7485/PYTHON1900/assets/54658614/66726267-eb3d-4379-b126-ed1b089942c8)

2. 부모 노드가 비었으므로, 가장 최하단부 노드를 루트로 옮긴다.
3. 부모 노드인 8보다 값이 큰 자식 노드가 있는지 비교한다.
    1) 왼쪽, 오른쪽 자식 노드 모두 부모 노드보다 클 경우
        - 왼쪽 자식 노드와 오른쪽 자식 노드를 비교하여, 더 큰 자식 노드와 부모 노드의 위치를 바꾼다. (swap)
    2) 왼쪽, 오른쪽 자식 노드 중 하나만 부모 노드보다 클 경우
        - 둘 중에 부모 노드보다 큰 자식 노드와 부모 노드의 위치를 바꾼다. (swap)

## heapq 모듈 사용하기
- 파이썬에서 기본적으로 제공하는 heapq 모듈은 우선순위 큐(Priority Queue) 알고리즘을 제공한다.
- 파이썬의 리스트를 사용해 인덱스 0부터 시작해 k번째 원소가 항상 자식 원소(2k+1, 2k+2)보다 작거나 같은 최소 힙의 형태로 정렬한다.

### import
```py
import heapq #heapq 모듈은 파이썬의 내장 모듈이기 때문에 따로 설치하지 않아도 된다.
```

### 힙 생성하기
- heapq 모듈은 파이썬의 리스트를 최소 힙 형태로 정렬하기 때문에 빈 리스트를 생성한 뒤, 모듈 함수를 호출할 때마다 생성한 리스트를 인자 값으로 넘겨야 한다.
```py
heap = []
```

### 삽입하기
- 모듈의 heappush() 함수를 사용해 원소를 삽입할 수 있다.
- 첫 번째 인자로는 대상 리스트를, 두 번째 인자로는 삽입할 값을 전달한다.
```py
heapq.heappush(heap, 10)
heapq.heappush(heap, 6)
heapq.heappush(heap, 13)
heapq.heappush(heap, 5)

print(heap)

[5, 6, 13, 10]
```

### 삭제하기
- 모듈의 heappop() 함수를 사용해 원소를 삭제할 수 있다.
- 대상 리스트를 인자로 넘기면, 최솟값을 삭제한 뒤에 반환한다.
```py
print(heapq.heappop(heap))
print(heap)

5
[6, 13, 10]
```
- 삭제하지 않고 최솟값을 출력하기 위해서는 heap[0]을 하면 된다.
```py
print(heap[0])
```
- 그렇다면 heap[1]에는 두 번째로 작은 원소가 들어있을까??
- 답은 ❌
- 작은 순서대로 정렬이 되어 있다면 10이 13보다 앞에 위치해야 하는데, 그렇지 않다.
- 최소 힙은 최솟값을 빠르게 찾기 위한 알고리즘이지, 작은 순서대로 정렬하는 알고리즘이 아니다.

### 리스트를 힙으로 변환하기
- 이미 원소가 삽입되어 있는 리스트를 heapq 모듈을 사용해 힙으로 변환하는 것이 가능하다.
- 이때는 heapify() 함수를 사용하고, 인자로 대상 리스트를 전달한다.
```py
heap = [7, 2, 4, 3, 1]
heapq.heapify(heap)

print(heap)
[1, 2, 4, 3, 7]
```

## 백준 알고리즘 1927번

![image](https://github.com/to7485/PYTHON1900/assets/54658614/697bbe92-d402-4e69-98fc-033c9052f462)

```py
import heapq
import sys

N = int(sys.stdin.readline())
heap = list()

for i in range(N):
    x = int(sys.stdin.readline())

    if x==0:
        if not heap:
            print(0)
        else:
            print(heapq.heappop(heap))
    
    else:
        heapq.heappush(heap, x)
```
