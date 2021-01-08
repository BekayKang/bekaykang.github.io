---
title: A* Algorithm for 3D Path Finding
author: Bekay
date: 2021-01-07 10:25:00 +0800
categories: [Graph Search Algorithm]
tags: [Path Finding,Dijkstra's Algorithm,Breath First Algorithm, A* Algorithm]
math: true
image: /assets/img/post/210107-4.gif
---


---
## A* Algorithm for 3D Path Finding
---
지금까지 **Graph Search Algorithm** 중에서 [**Breath First Algorithm**](https://bekaykang.github.io/posts/Breath-First-Algorithm/), [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/), 그리고 [**A\* Algorithm**](https://bekaykang.github.io/posts/Astar-algorithm/)에 대해서 알아봤다.

이제는 알고리즘을 이용해서 조금 더 흥미로운 문제로 검증해보고자 한다.

이번에는 3D Path Finding 문제를 **A\* Algorithm**을 이용해서 잘 해결하는지 확인해보자.

---
## 3D Path Finding
---
3D Path Finding의 문제 정의는 아래와 같다.
- 30x30x30 크기의 Cubic Grid
- 시작점 (0,0,0), 도착점 (22,29,29)
- 장애물은 전체 크기의 70% (=30x30x30x0.7)

Cubic Grid와 시작/도착점 확인
![Desktop View](/assets/img/post/210107-1.png)

장애물 환경을 포함한 실제 문제 상황
![Desktop View](/assets/img/post/210107-2.png)

---
## Result
---
당연하게도? **A\* Algorithm**을 이용하여 3D Path Finding 문제를 해결하였다.

3D Path Finding 결과
![Desktop View](/assets/img/post/210107-4.gif)

실제 Path Finidng 경로 결과
![Desktop View](/assets/img/post/210107-3.gif)

위와 같은 재밌고 다양한 문제에 **Graph Search Algorithm**을 적용할 수 있을 것 같다.

---
## Code
---
<script src="https://gist.github.com/BekayKang/6b68db39eca39b81fbcf9b1c43567b98.js"></script>