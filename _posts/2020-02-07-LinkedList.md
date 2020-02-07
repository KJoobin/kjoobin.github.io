---
title: "[TID] Linked list"
date: 2020-02-07 13:12:30
categories: TID, Data structure, Linked list
---

## Linked list  
![Linked_list](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/Linked_list.jpeg?raw=true_)
linked list 는 각 노드가 데이터와, 다음 데이터의 주소(포인터)를 가지고 있어 한줄로 연결되어 있는 방식이다.  
### 장점  
'''
데이터 중간에 추가, 중간값 삭제가 쉽다.
'''
이전에 배운 스택, 큐 의 경우 중간에 값을 넣기 위해서 쌓아놧던 데이터를 원하는 위치까지 뺏다가, 데이터를 쌓고, 뺀 데이터를 다시 쌓는 불편함이 있다.  
![liinkedList_stack](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/liinkedList_stack.png?raw=true_)
하지만 linked list 를 사용하면 넣고싶은 index의 노드에서 다른 데이터의 주소값을, 넣고 싶은 데이터의 주소값으로 바꾼뒤, 넣고싶은 데이터의 주소값에 다음 index 의
주소값을 넣으면 된다.
```
//xxxx00 -> '3', xxxx01
//xxxx01 -> '4', xxxx03
  ...
//넣고싶은 data xxx0x03 -> '10', 0000000
```
을 아래와 같이 바꾼다.
```
//xxxx00 -> '3', xxx0x03
//xxx0x03 -> '10', xxxx01
//xxxx01 -> '4', xxxx03
....
```
###단점  
```
원하는 데이터를 찾기 위해서는 처음부터 데이터의 위치까지 O(n) 번 수행해야 한다.
```

---
property | 설명 | method | 설명 |
| --- | --- | --- | --- |
| node | data | next | 다음노드로 진행 |
| head | 모든 노드의 맨 앞 |
| before | 현재 위치 전 |
| current | 현재 탐색 위치 |
|tail | 모든 노드의 맨 뒤 |
---

![liinkedList_property](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/liinkedList_property.png?raw=true_)

```
- 추가하기 ( 데이터 )
  tail 을 이용해 추가하고 싶은 값의 주소값을 마지막 노드의 다음 데이터 주소값( 포인터 ) 에 넣는다.
  tail 을 추가한 데이터의 노드의 주소값으로 변경한다.
  
- 삽입하기 ( 삽입할 위치의 데이터, 삽입할 데이터 )
  current 를 head 로 설정,
  next 를 이용해 삽입할 위치의 데이터와 current 노드의 데이터값이 같은지 비교,
    다르면 
      before <- current
      current <-- current.next
      데이터를 다음으로 바꾼고, 반복
    같다면
      before.next 를 삽입할 데이터의 주소값으로 변경,
      삽입할 데이터.next 를 current 주소값으로 변경

- 삭제하기 ( 삭제할 데이터 ) 
  currnet 를 head 로 설정
  next 를 이용해 삭제할 위치의 데이터와 currnet 노드의 데이터값이 같은지 비교,
  다르면
    반복..
   같으면
    before.next 를 current.next 값으로 변경
```
