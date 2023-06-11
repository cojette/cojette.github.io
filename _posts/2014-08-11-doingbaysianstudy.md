---
layout: post
title: Doing Bayesian 스터디 (6장)
---


INFERRING A BINOMIAL PROPORTION VIA GRID APPROXIMATION
===================

이 장에서는 사전 분포가 베타 분포로 정의되지 않은 경우의 추론 방법에 대해 다룬다. 전반적으로 분포를 이산적으로 분할한 후, 적분 대신 합으로 구해준다고 생각하면 간단하다.

Bayes' Rule for discrete values of theta
----------------------------------------

이전 장에서는 매개변수( θ)가 [0,1]인 경우를 다루었다면, 이 장에서는 θ가 이산적인 몇 개의 값만을 가지고 있을 때를 살펴본다. 이 경우 Bayes' Rule 은 다음과 같다.\
p(θ|D)=p(D|θ)p(θ)Σθp(D|θ)p(θ)\
이 경우 연속적일 때보다 더 구하기 쉬운 경우도 있고, 이를 활용해서 적분이 어려운 함수가 사전 밀도 함수로 사용된 경우 이산형으로 근사시켜 사용할 수 있다.

Discretizing a continuous prior density
---------------------------------------

연속형 사전 밀도 함수를 이산형으로 근사시켜 위의 식을 활용한다. 연속형 사전 밀도 함수는 다음과 같은 식으로 이산형으로 근사값을 구한다.

[![bay601](http://datum.io/wp-content/uploads/2014/08/bay601-291x300.png)](http://datum.io/wp-content/uploads/2014/08/bay601.png)

Estimation
----------

사후 확률에 대해서 2가지의 요약값을 사용한다. θ의 평균은 주어진 변수에 각 변수가 일어날 확률을 가중치로 곱한 값의 합으로 구할 수 있다. 나머지 하나는 HDI(Highest Density Interval)로, 이산적인 형태의 사후 확률의 경우 95%HDI를 구한다고 쳤을 때 정확히 95%로 떨어지지 않는 경우가 있을 수 있다. 또한 경우에 따라 HDI가 여러 개로 쪼개진 형태로 나올 수도 있다.

Prediction of subsequent data
-----------------------------

후행 데이터값 예측은 각 θ에 사전 믿음에 따른 확률값을 곱해서 나타낼 수 있다.\
p(y|D)=∫dθp(y|θ)p(θ|D)≈∑θp(y|θ)p(θ|D)

Model comparision
-----------------

M1, M2라는 두 개의 모델이 있을 때, 각 모델의 사전 믿음을 p(M1), p(M2)라 하면, 사후 믿음은 p(M1|D), p(M2|D)라고 할 수 있다. 이 때 사후 믿음 역시 앞 장의 모델 비교 식의 Bayes Factor에 나오는 적분 형태를 이산 값의 합의 형태로 치환해서 사용할 수 있다.

FAQ
---

Q. 확률론에서의 우도비검정(likelihood-ratio test)과 베이지안에서의 모델 비교의 차이는?

A.  개념 및 식은 간단히 보면 매우 유사하다. 우도비 검정에서는 가설 H0과 대립가설 H1의 테스트다.  이 경우 가설은  상호 배제(mutually exclusive)와 전체 포괄(collectively exhaustive) 조건을 만족하지만, 모델 비교(베이지안이 아니라고 하더라도) 는 이 조건을 만족하지 않는다. 따라서 이는 무엇의 옳고 그름을 판단하는 검정으로 볼 수 없다.

Q. HDI(Highest Density Interval)이 항상 존재하는가? 또한  CI(Confidence Interval)과의 차이는?

A. 이는 일단 [위키피디아](http://en.wikipedia.org/wiki/Confidence_interval#Comparison_to_Bayesian_interval_estimates)를 참조하자. 가볍게는 최적의 CI라고 볼 수도 있지만, 후자의 경우는 모수의 범위에 대한 거라면, HDI의 경우는 해당 값이 나올 믿음에 대한 것이다. 이에 대해서는 차후에 계속 나타날 것이라고 생각한다.

(FAQ는 스터디때의 난상 토론(?)에 개인 의견을 더해서 정리한 것이므로, 보다 자세한 설명은 언제든 환영합니다.)
