---
title: Pytorch GPU Out of memory Issue
author: Bekay
date: 2021-08-12 20:25:00 +0800
categories: [Issue Fix]
tags: [Pytorch, GPU, Out of Memory]
math: true
image: /assets/img/post/2021-08-12-1.PNG
---
``

---
## GPU Out of Memory Issue
---
Pytorch를 이용하여 모델을 개발하면 아마 한번쯤은 "GPU Out of Memory"를 마주친다.  

GPU에 대한 이해가 깊다면, 금방 해결할 수 있지만 그렇지 않으면 당황하기 딱 좋은 Error다.  

나의 경험은 강화학습을 학습을 할 때, Policy Gradient 기반 Learner를 학습할 때 학습이 진행되면서 GPU Memory도 지속적으로 커지는 현상을 만났다.

다양한 해결방법이 나와있지만, 나의 경우에 해결법은 `torch.cuda.empty_cache()` 이다!


<script src="https://gist.github.com/BekayKang/38b3226a999db4a52ba0a8715b333898.js"></script>
