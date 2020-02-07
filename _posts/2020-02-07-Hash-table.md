---
title: "[TID] Hash table"
date: 2020-02-07 14:32:00
categories: TID HashTable LinkedList
---


![정리](https://t1.daumcdn.net/cfile/tistory/274FB54553240D7007)   
*색깔별로 정리한 옷의 사진이다.*
## Hash table  
Hash table 은 데이터를 규칙에 따라 정리한것 이다.  
---
| property | 의미 |
| --- | --- |
| key | 원래 데이터의 값 |
| hash value | 데이터를 hashing 한 값 |
| buckets | hashing 한 데이터를 저장하는 곳 |
| Hash function | key 를 어떠한 규칙에 의해서 매핑하는 함수 |

| method |
| --- |
| 삽입 |
| 탐색 |
| 삭제 |
---

### 왜?  
hash table 을 사용하는 이유는 원하는 데이터를 빠르게 탐색하기 위해서 이다. Queue, stack, linked list에서
데이터를 탐색하기 위해서는 처음부터 끝까지 차례대로 돌아야한다면, hash table 을 이용하면 hashing 을 통해 한번에 찾을수 있다.  

![HashTable](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7d/Hash_table_3_1_1_0_1_0_0_SP.svg/440px-Hash_table_3_1_1_0_1_0_0_SP.svg.png)

### 사용방법  
john 의 전화번호를 알고 싶다면 Jonh 을 hashing 해서 얻은값 02(hash value) 를 bucket 에서 탐색을 하면 된다.  

### Collision  
hashing 을 하다보면 다른 데이터가 같은 hash value 를 갖는 Collision 이 생기는데   
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Hash_table_5_0_1_1_1_1_1_LL.svg/900px-Hash_table_5_0_1_1_1_1_1_LL.svg.png" width="70%" height="70%" ></img>   
*john 과 sandra 가 hashing value 가 같아 생기는 Collision*

1. Separate chaining   
- linked list 를 이용해서 hashing value 에 이미 데이터가 들어있다면, 이미 들어있는 데이터와 연결해주면 된다.   
- 최악의 경우 시간복잡도가 O(n) 이 된다. ( 모두가 같은 hashing value 를 가지게 될 경우)
- 더 많은 메모리를 사용하게 된다.   
2. Open addressing linear probing   
-    
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Hash_table_5_0_1_1_1_1_0_SP.svg/760px-Hash_table_5_0_1_1_1_1_0_SP.svg.png" width="70%" height="70%" ></img>   
