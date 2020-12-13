---
title: Github Blog - Google Analytics 연동
author: Bekay
date: 2020-12-01 20:25:00 +0800
categories: [Github Tip]
tags: [Github Blog, Google Analytics, Tip]
math: true
image: /assets/img/post/201201-1.png
---


---
## GitHub Blog와 Google Analytics 연동
---
Github Blog 자체적인 조회수에 대한 통계를 제공하지 않는다.

Github Blog에 대한 통계를 도출하고 싶을 때 Google Analytics를 이용하면 가능하다.


---
## 연동 방법
---
먼저 Google Analytics에 가입을 해서 아래 그림의 순서대로 수행한다.

![Desktop View](/assets/img/post/201201-2.png)

4번 스트림 추가에서 "웹"을 선택하고 본인의 Github Blog 주소를 입력하면, 5번과 같이 데이터 스트림 항목이 생긴다.

![Desktop View](/assets/img/post/201201-3.png)

5번을 클릭하면 웹 스트림 세부정보가 나오게 되는데, 거기서 측정 ID를 복사한다.

![Desktop View](/assets/img/post/201201-4.png)

Github Blog directory의 root에 _config.yml에 아래와 같이 추가하면 끝!

![Desktop View](/assets/img/post/201201-5.png)

본인의 Github Blog 방문 후, Google Analytics를 확인하면 아래와 같이 통계 정보를 확인할 수 있다.

![Desktop View](/assets/img/post/201201-6.png)