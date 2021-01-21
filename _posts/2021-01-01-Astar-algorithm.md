---
title: A* Algorithm
author: Bekay
date: 2021-01-01 10:25:00 +0800
categories: [Graph Search Algorithm]
tags: [Path Finding,Dijkstra's Algorithm,Breath First Algorithm, A* Algorithm]
math: true
image: /assets/img/post/210101-5.png
---


---
## A* Algorithm
---
Path Finding을 위한 Graph Search Algorithm 중에서 [**Breath First Algorithm**](https://bekaykang.github.io/posts/Breath-First-Algorithm/)와 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)는 이전에 다뤘다. 이제 마지막인 **A\* Algorithm**이다.

[**Breath First Algorithm**](https://bekaykang.github.io/posts/Breath-First-Algorithm/)은 현재 위치에서 갈 수 있는 모든 방향을 다 탐색하면서 경로를 확장해나간다. 경로를 확장하다가 도착지점에 도착할 경우, 그 동안 지나온 경로를 거꾸로 밟아가며 Path를 찾는 방법이다.

[**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)은 Breah First Algorithm에서 각 경로 탐색에 소요되는 Cost term을 추가하였다. Path Finding을 위한 Map에는 함정, 산, 강과 같은 일반 평지와는 다른 특성을 가진 위치가 존재한다. 이러한 곳은 일반 평지보다 지나가기가 힘들므로 Cost Term을 추가해서 Map에 있는 제한 사항들을 극복하여 Path Finding을 할 수 있게 도와준다.

---
## Idea of A* Algorithm
---
**A\* Algorithm**은 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)을 조금 더 효율적으로 수행할 수 있도록 제안된 알고리즘이다. 

만약, [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)에서 같은 Cost를 갖는 후보 방향이 여러방향이라면 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)은 그 모든 방향에 대해 경로 탐색을 통해 확장한다. 다시 말해, 목적지와 상관없는 방향이더라도 Cost가 같은 방향의 후보군이라면 탐색을 하므로 비효율적인 탐색을 수행한다고 생각할 수 있다.

아래의 그림과 같이 End Point가 보라색인 경우, 붉은색인 왼쪽 / 위쪽으로 탐색을 확장하는 것 보다 파란색인 아래 / 오른쪽으로 탐색을 확장하는 것이 효율적이다.

![Desktop View](/assets/img/post/210101-2.png)

탐색의 효율성을 높이기 위해 **A\* Algorithm**은 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)의 Cost Term에 추가적으로 목표 지점까지의 거리를 추가로 사용한다.
![Desktop View](/assets/img/post/210101-3.png)

따라서 효율적인 경로 탐색과 확장을 통해 **빠르게** Path를 찾는 결과를 보여준다.

---
## Comparison Result of Time-Consuming
---
1000x1000의 가상의 맵에서 출발지는 (0,0), 도착지는 (999,999)인 Path Finding 문제를 해결해야 된다. 붉은 점들은 지나가기 힘든 장애물들이다.


![Desktop View](/assets/img/post/210101-4.png)

**A\* Algorithm**과 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)에서 Path Finding에 소요되는 시간이 어떤지 비교 실험을 하였다.

![Desktop View](/assets/img/post/210101-5.png)

그 결과, **A\* Algorithm**은 약 0.1s 소요 되었고 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)은 약 36s 소요 되었다. 무려 360배 정도의 소모 시간의 차이를 보였다. 물론 풀어야하는 문제의 복잡도에 따라서 이는 매우 달라진다. 하지만 이 결과만으로도 **A\* Algorithm**의 효율성은 입증된 것 같다.

**A\* Algorithm**을 통해 실제 Path Finding한 결과

![Desktop View](/assets/img/post/210101-6.png)

---
## Code
---
**A\* Algorithm**의 Code는 대부분 [**Dijkstra's Algorithm**](https://bekaykang.github.io/posts/dijkstra-algorithm/)과 유사하며 **Distance Term** 부분만 추가했다.
[![Github](/assets/img/post/GitHub-logo.png){: width="70"}](https://github.com/BekayKang/pathfinding_algorithms_bekay)
<script src="https://gist.github.com/BekayKang/fd4418716f35dfdcff3ef3cfaf237c43.js"></script>