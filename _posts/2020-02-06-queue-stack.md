---
title: "[TID]  Queue, Stack"
date: 2020-02-06 15:03:00 -0400
categories: TID DataStructure Queue Stack
---

## Queue

queue 는 미끄럼틀을 상상하면 쉽다. FIFO( first-in first-out ) 먼저 미끄럼틀을 탄 사람은 그다음 탄사람보다 늦게 나올수없다.

![Queue](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/Queue.jpeg?raw=true)
```
값을 추가할것인지 뺄것인지 묻는다.
  추가한다면
    저장된값.push(추가할 값);
  뺀다면
    저장된값.shift();
```



## Stack

stack 은 하노이타워 이다. LIFO( last-in first-out) 가장 마지막에 들어간것이 가장 먼저 나온다.

![stack](https://github.com/KJoobin/kjoobin.github.io/blob/master/assets/images/Stack.jpeg?raw=true)
```
값을 추가할것인지 뺄것인지  묻는다.
  추가한다면
    저장된값.push(추가할 값);
  뺀다면
    저장된값.pop();
```
