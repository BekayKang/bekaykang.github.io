---
title: Python - super() 클래스 상속
author: Bekay
date: 2021-04-15 20:25:00 +0800
categories: [Python]
tags: [Python, Class, super]
math: true
image: /assets/img/post/210415-1.png
---


---
## Python: super() 클래스 상속 :clipboard:
---
Code를 작성하다보면 먼저 작성한 Class를 활용하면 좋을 때가 있다.
예를 들면, 기존에 작성한 Class에서 구현한 함수를 지금 작성하는 Class에서 끌어다가 쓰고싶을 때이다.

이럴떄 사용하는 방법이 클래스 상속 <mark style='background-color: #ffdce0'>super()</mark>이다.


예제를 하나 만들어보면,
먼저 더하기, 빼기, 나누기, 곱하기의 기능을 구현할 수 있는 calculator()라는 정의했다.

![Desktop View](/assets/img/post/210415-3.PNG)

<mark style='background-color: #fff5b1'>calculator Class의 기본 기능이 앞으로 작성할 다른 여러 Class에서 사용해야할 때, 작성하는 매 Class마다 더하기,빼기, 나누니, 곱하기의 기능을 새로 작성한다면 매우 비효율적이다.:scream:</mark>

따라서 calculator Class를 상속받아 활용하면 효과적으로 Code를 작성할 수 있다.:+1:

calculator_printer라는 Class를 생성하여 calculator Class를 상속 받아서 기본 기능을 다시 구현하지 않고 사용이 가능하다.

아래는 print_all의 결과이다.

![Desktop View](/assets/img/post/210415-2.PNG)


---
## Code
---
<script src="https://gist.github.com/BekayKang/b74035f2c4b77906431cced13fe593bc.js"></script>