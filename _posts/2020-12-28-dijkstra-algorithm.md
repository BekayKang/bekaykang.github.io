---
title: Dijkstra's Algorithm
author: Bekay
date: 2020-12-28 10:25:00 +0800
categories: [Graph Search Algorithm]
tags: [Path Finding,Dijkstra's Algorithm,Breath First Algorithm, A* algirhtm]
math: true
image: /assets/img/post/201228-1.png
---


---
## Dijkstra's Algorithm
---
Graph Searching Algorithm 중에서 [**Breath First Algorithm**](https://bekaykang.github.io/posts/Breath-First-Algorithm/)을 **Cost** 기반으로 알고리즘을 제안한것이 **Dijkstra's Algorithm**이다.

Cost라는 것은 아래 그림과 같이 에베레스트산과 같은 극한 지형이 있을 때 산을 가로 질러가는 것보다 산아래를 둘러가는 것이 효율적인 방법이다.
![Desktop View](/assets/img/post/201228-2.png)

이렇듯 길찾기를 할 때 위치마다 소모되는 체력?이 다를 수 있기 때문에 이러한 제약을 Cost로 적용하여 Path Finding하는 알고리즘이 **Dijkstra's Algorithm**이다.

**Dijkstra's Algorithm**을 이용하여 위의 문제를 풀었을 때 결과는 아래와 같다.
![Desktop View](/assets/img/post/201228-3.gif)

예상처럼 산의 극한지형은 피하면서 둘러서 최적 Path를 찾는다.

같은 문제를 Cost를 고려하지 않으면 [**Breath First Algorithm**](https://bekaykang.github.io/posts/Breath-First-Algorithm/)에서 도출된 것 처럼 전혀 다른 결과가 나온다.


---
## Code
---
**Dijkstra's Algorithm**의 Code는 대부분 [**Breath First Algorithm**](https://bekaykang.github.io/posts/Breath-First-Algorithm/)과 유사하며 **Cost** 부분만 추가했다.
<script src="https://gist.github.com/BekayKang/e04aec25fcb5a7288c312a62b4c55129.js"></script>