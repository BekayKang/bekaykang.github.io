---
title: Policy Gradient
author: Bekay
date: 2021-05-16 10:25:00 +0800
categories: [Reinforcement Learning,Policy Gradient]
tags: [Policy Gradient, Reinforce]
math: true
image: /assets/img/post/210516-1.jpg
use_math: true
---


## Objective Function
Policy gradient의 objective는 결국 exptected return의 maximization!   

$$
\begin{equation}
J(\theta_\pi) = \underset{\tau \sim \pi_\theta}{\mathbb{E}} [R(\tau)] \tag{1} \\ \\
\end{equation}
$$

만약 objective function $J(\pi_\theta)$의 derivation을 구할 수 잇다면 policy를 gradient ascent 방향으로 업데이트하면 expected return을 maximization하는 poicy로 업데이트할 수 있다.   

$$
\begin{equation}
\theta_{k+1} = \theta_k + \alpha\nabla_\theta J(\pi_\theta)|_{\theta_k} \tag{2} \\ \\
\end{equation}
$$

$\nabla_\theta J(\pi_\theta)$가 바로 policy graident이고, poicy gradient를 이용하여 optimal policy를 찾는 알고리즘을 **Policy Gradient Algorithm 혹은 Policy-based Method**라고 한다. 그 대표적인 알고리즘은 PPO, DDPG 등이 있다.   

## Policy Gradient인 $\nabla_{\theta}J(\pi_\theta)$를 어떻게 구할 것 인가?
Policy gradient의 계산을 위해서는 식의 변형이 필요하다. 우선 expected return인 $\underset{\tau \sim \pi_\theta}{\mathbb{E}} [R(\tau)]$를 계산 가능한 형태로 변환하고, 강화학습을 진행하면서 얻는 sample based로 추정이 가능하게 해보자.   

$$
\begin{align}
J(\theta_\pi) &= \underset{\tau \sim \pi_\theta}{\mathbb{E}} [R(\tau)] \tag{3} \\ \\
&=\nabla_\theta \int_\tau\nabla_\theta P(\tau|\theta)R(\tau) \quad (\because Expand \ expectation) \tag{4} \\ \\
&=\int_\tau \nabla_\theta P(\tau|\theta)R(\tau) \tag{5} \\ \\
&=\int_\tau P(\tau|\theta) \nabla_\theta log P(\tau|\theta) R(\tau) \quad (\because Log-derivative \ trick) \tag{6} \\ \\
&=\mathbb{E}_{\tau \rightarrow \pi_\theta}[\nabla_\theta log P(\tau|\theta)R(\tau)] \tag{7} \\ \\
\end{align}
$$

(7)번 식의 $P(\tau|\theta)$에 대해서 풀어보면
Probability trajectory는 $\tau =(s_0,a_0,s_1,a_,1,....,s_{T+1})$으로 정의할 수 있고 action은 $\pi_\theta$로 구할 수 있다.   

$$
\begin{align}
P(\tau|\theta) &= p_0(s_0)\prod_{t=0}^T P(s_{t+1}|s_t,a_t)\pi_\theta(a_t|s_t) \tag{8} \\ \\
logP(\tau|\theta) &= logp_0(s_0) + \sum_{t=0}^T(logP(s_{t+1} | s_t,a_t) + log\pi_\theta(a_t|s_t)) \tag{9} \\ \\
\nabla_\theta logP(\tau|\theta) &= \sum_{t=0}^T \nabla_\theta log\pi_\theta(a_t|s_t) \tag{10} \\ \\
\end{align}
$$

(10)번 식을 (7)번 식에 대입하면 (11)번 식으로 정리된다.   

$$
\begin{align}
\therefore \nabla_\theta J(\pi_\theta) = \mathbb{E}_{\tau \rightarrow \pi_\theta}[\sum_{t=0}^T \nabla_\theta log\pi_\theta(a_t|s_t)R(\tau)] \tag{11} \\ \\
\end{align}
$$


## 강화학습시 Policy Gradient 계산법
강화학습에서 Env.와 Agent가 interaction을 통해서 sample을 수집한다. 수집된 sample based로 policy gradient를 계산해보자.   

수집된 smaple trajectory가 $D = \tau_i \mid_{i=1,...,N}$이고 action이 policy $\pi_\theta$를 따른다면 plicy gradient $\hat{g}$는 아래와 같이 구할 수 있다.   

$$
\begin{align}
\hat{g} = \frac{1}{N}\sum_{\tau \in D} \sum_{t=0}^T \nabla_\theta log\pi_\theta(a_t|s_t)R(\tau) \tag{12} \\ \\
\end{align}
$$
   

현재 policy인 $\pi_\theta$를 이용하여 $log \pi \theta(a_t \mid s_t)$를 계산할 수 있으므로, policy gradient도 sample based로 계산할 수 있다. 추정된 gradient를 기반으로 현재 policy를 **gradient ascent방향**으로(expected return을 maximization하는 방향) 업데이트하면 된다. 












<!-- ## Policy Gradient의 High-Variance 문제를 해결할 수 있을까?

Policy Gradient의 문제점은 $R(\tau)$를 얻기 위해서 batch of episodes만큼을 수행해야한다.
이는 학습을 느리게할 뿐만아니라 Gradient 추정에서도 High-varaince로 인한 unstable learning을 유발한다.

High-varaince 문제 해결을 위해서 Gradient 추정 과정에서 baseline을 빼줌으로 variance를 줄이고자한다.

기본적인 Policy Gradient는 아래와 같이 구할 수 있다.
```math
\nabla_\theta J(\pi_\theta) = \mathbb{{E}}_{\tau\rightarrow\pi_\theta}[\sum_{t=0}^{T}\nabla_\theta log\pi_\theta(a_t|s_t)R(\tau)]
```


Baseline을 위한 식 전개를 해보자

```math
\nabla_\theta J(\pi_\theta) = \mathbb{{E}}_{\tau\rightarrow\pi_\theta}[\sum_{t=0}^{T}\nabla_\theta log\pi_\theta(a_t|s_t)R(\tau)]
```

```math
\nabla_\theta J(\pi_\theta) = \mathbb{{E}}_{\tau\rightarrow\pi_\theta}[(\sum_{t=0}^{T}r_t)\nabla_\theta\sum_{t=0}^{T} log\pi_\theta(a_t|s_t)]
``` -->
