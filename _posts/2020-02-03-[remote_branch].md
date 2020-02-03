---
title: "TID"
date: 2020-02-03 20:52:00
categories: TID
---

remote 를 이용해서 협업을 배우던중 fetch 와 pull 의 차이에대해서 궁금증이 생겼다.

공통점: 새로운 파일에 대한 다운로드가 진행된다.
pull 과 fetch 둘다 다운로드 되는 특성이 있었다

차이점: 병합여부, HEAD 의 위치
pull 의 경우 다운로드와 병합이 되는데 반해 fetch 는 merge 명령어를 한번더 사용해야했다.
HEAD 란 현재 파일의 위치를 말하는데 pull 의 경우 명령어를 쓰면 merge 가 되므로 HEAD 의 위치도 가장앞인 merge된 브랜치 인 반면 fecth 는 merge 되기전
가장 선두에 위치하는 브랜치가 HEAD 가 된다.
