---
title: Install Python3.11 in WSL
author: Bekay
date: 2022-12-13 10:25:00 +0800
categories: [Issue Fix]
tags: [Python3.11, Install]
math: true
image: /assets/img/post/2022-12-13-1.png
---

---
## Python 3.11
---
Python3.11 release되면서 많은 관심을 받고있다. 가장 큰 이유는 속도 측면에서 큰 개선이 있다.
> The Faster CPython Project is already yielding some exciting results. Python 3.11 is up to 10-60% faster than Python 3.10. On average, we measured a 1.22x speedup on the standard benchmark suite. See Faster CPython for details.

![DeskView](/assets/img/post/2022-12-13-2.png)

---
## Install Python 3.11 in WSL
---
Python3.11을 사용하기 위해서 WSL에 설치하는 방법은 아래와 같다.
**WSL Terminal**
1. `>> sudo apt update`
2. `>> sudo apt install software-properties-common`
3. `>> sudo add-apt-repository ppa:deadsnakes/ppa`
4. `>> sudo apt update`
5. `>> sudo apt install python3.11`

