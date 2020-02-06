---
title: "[TID]  Queue, Stack"
date: 2020-02-06 15:03:00 -0400
categories: TID DataStructure Queue Stack
---

## Queue

queue 는 미끄럼틀을 상상하면 쉽다. FIFO( first-in first-out ) 먼저 미끄럼틀을 탄 사람은 그다음 탄사람보다 늦게 나올수없다.  

---
front : 데이터를 get 할 수 있는 위치  
rear : 데이터를 put 할 수 있는 위치  
overflow : 큐가 꽉 차서 더이상 자료를 넣을 수 없는 경우  
underflow : 큐가 비어 있어 자료를 꺼낼 수 없는 경우  

---

Array.push(value) : Array 에 value 를 가장 마지막 index + 1 에 추가한다.  
Array.shift() : Array 의 0번째 index 를 pop() 한 후 나머지 index 를 -1 해 준다.  
Array.length() : Array 의 길이 ( index 의 갯수 ) 를 반환합니다.  

![queue](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/Queue.jpeg?raw=true)

```
값을 추가할것인지 뺄것인지 묻는다.
  추가한다면
    overflow인가?
      yes -> overflow 출력
      no -> 저장된값.push(추가할 값);
  뺀다면
    underflow 인가?
    yes ->  underflow 출력
    no -> 저장된값.shift();
```



## Stack

stack 은 하노이타워 이다. LIFO( last-in first-out) 가장 마지막에 들어간것이 가장 먼저 나온다.

---

top : 저장된 데이터에서 가장 마지막에 들어온 값  
bottom: top 과 반대되는, 저장된 데이터에서 가장 처음 들어온 값  

---

Array.pop() : 저장된 배열에서의 마지막 index 값을 뺀다.  
![stack](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/Stack.jpeg?raw=true) 


```
값을 추가할것인지 뺄것인지  묻는다.
  추가한다면
    overflow인가?
      yes -> overflow 출력
      no -> 저장된값.push(추가할 값);
  뺀다면
    underflow 인가?
    yes ->  underflow 출력
    no -> 저장된값.pop();

```
