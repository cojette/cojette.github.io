---
layout: post
title: R과 Google이 함께 하는 시계열 예측
---

Overview
========

데이터 분석이 흥하면서, 한동안 잠잠하던 시계열 예측 분석이 다시 주목받고 있다. 이 시계열 예측 분석이 침체기였던 이유는, 보통 실제로 어떤 사건이 발생함에 있어서 수많은 실험에서의 가정처럼 '독립적'인 경우가 많지 않은지라, 단일한 시계열로 그 이후를 예측할 때 그 결과가 믿을 만한 경우가 (실험적으로야 잘 나온다 하더라도) 그다지 많지 않기 때문이다. 그래서 실제로 수요 예측 등의 용도로 시뮬레이션은 그럭저럭 하면서도, 여기에 실제 현상을 어떻게 잘 녹여넣을까에 대한 숙제는 항상 있어왔다. 그리고 보통 시간의 흐름에 따라서 영향을 미치다보니, 이런 영향력을 미치는 인자 간의 '상관성'보다는 '인과성'에 보다 초점을 맞추게 된다. 그래서 이에 대한 다양한 연구가 되고 있는데, Google Analytics라든가 Google Trend 등으로 시계열 데이터를 쉽고 유용하게 사용하도록 도와주-면서 사람들을 낚고있다고 읽-는 Google에서 이에 대해서 신경쓰지 않을 리 없다. 그리고 이번에 베이지안 방식으로 인과 추론(causal inference)을 하는 [예측 모델 방법론](http://research.google.com/pubs/pub41854.html)을 만들었다.

Inferring causal impact using Bayesian structural time-series models
====================================================================

여기서 사용하는 방법을 간단히 설명하면, 각각의 상태를 일종의 state-space model(간단하게 hidden markov chain 같은 모델이라고 생각하면 된다) 로 만든 후에 이에 대한 상태 변화 예측 모델을 만들고, 베이지안 방법론을 사용하여 사후 추론 내용에 대한 신뢰구간을 만들어서 제공하는 방식이다. 일반적으로 예측 요인-결과의 시계열 데이터를 사용하여, 특정 구간을 중심으로 해서 training-test 로 시계열을 나누고, test의 부분을 예측하는, 보통 흔히 사용하는(?) forecasting 방식이다. 다만 여러 변수를 동시에 사용해서 사전 요인으로 사용해서 이 요인들이 실제로 얼마나 영향을 끼치는지, 서로 어떻게 영향을 끼쳐서 이로 인해서 어떤 식으로 움직일 지를 예측할 수 있다고 하니, 일반적으로 실무에서 시계열 예측 분석을 사용하면서 고민하는 중요한 점들이 어느 정도 해소될 수 있을 것이다. (상세한 수식 등은 적기도 힘들고 나도 100% 이해하지는 못한 지라 적지는 않겠다. 간만에 논문 보려니 머리 깨지겠더라.)

R의 CausalImpact Package 와 예제 [#](http://cojette-wiki.appspot.com/time_series_prediction_with_R_and_Google#h_a10cb5401471129dcf6fc69ecfad8dab)
=============================================================================================================================================

그리고 구글에서는 이 논문을 내면서 아주 감사하게도 이 내용을 R Package로도 같이 내 주어서, 여기 나온 어려운 수식을 일일히 함수로 짤 필요 없이 간단하게 사용할 수 있도록 해 주었다. 패키지는 GitHub에 올라가 있고, 다른 패키지와 마찬가지로 devtools 를 사용하여 손쉽게 설치해서 사용할 수 있다.

```
install.packages("devtools")
library(devtools)
devtools::install_github("google/CausalImpact")
library(CausalImpact)

```

그러면 간단한 예제를 실행해보자.

세상은 좋아져서, 인터넷을 뒤지면 수많은 샘플 시계열 데이터들을 구할 수 있다. 혹은 직접 난수를 발생시켜서 쓸 수도 있다. 여기서는 간단히 인터넷의 샘플을 사용해 보겠다.

```
## data load
data <- read.csv("https://stat.duke.edu/~mw/data-sets/ts_data/gdp", header = T, skip = 2, sep = " ")
capita <- data[,c(6, 3)]
colnames(capita)<- c("x","y")
capita[is.na(capita)]<-0 ## null handling

```

그러면 2열짜리 데이터셋이 생긴다. 일단 이 데이터가 어떻게 생겼는지 확인해 보자.

```
matplot(capita, type = "l")

```

[![Rplot1](http://datum.io/wp-content/uploads/2014/10/Rplot1-300x201.jpeg)](http://datum.io/wp-content/uploads/2014/10/cap1.jpg)

그럼 여기서 어느 시점까지를 training으로 두고 이를 기반으로 이후를 예측할 것인지를 결정하자. 물론 가운데 intervention을 두어서 세 부분, 혹은 모델을 여러 번 돌려서 더 잘게 나눌 수도 있겠지만 우선 간단하게 training-test로 나누자. 여기서는 34년간의 데이터이므로 25 시점에서 자르도록 하겠다.

```
pre.period <- c(1, 25)
post.period <- c(26, 34)

```

시점도 나누었으니, 가장 기본적인 causal impact를 구해보자.

```
impact <- CausalImpact(capita, pre.period, post.period)

```

결과를 우선 눈으로 빠르게 확인해 보자.

![Rplot2](http://datum.io/wp-content/uploads/2014/10/Rplot2-300x201.jpeg)

이 그래프를 읽는 법은 다음과 같다. 가장 위의 original은 원 데이터와 예측 데이터의 결과 값을 기본적으로 보여주는 것이고, 가운데는 실제 데이터와 예측 데이터의 차이를 각 시점별로 나타낸 것이고, 마지막은 이런 각 시점의 차이의 누적값을 나타낸다.

이에 대한 결과를 수치로 보고 싶으면 다음과 같이 볼 수 있다.

![cap1](http://datum.io/wp-content/uploads/2014/10/cap1-300x180.jpg)

이는 post.period의 예측 값에 대한 평균과 누적값에 대한 실제 값과 예측값, CI(Confidence Interval) 등을 보여준다. effect의 CI 구간에 0이 포함되는 것으로 볼 때 x 변수가 응답 변수 y에 인과적 영향력을 주지 못한다고도 추정할 수 있다.

물론 모델을 기본형 이상으로 커스터마이징도 가능하다. CausalImpact 함수 자체에도 레벨,데이터 스케일링 등의 전처리, state-machine 진행 횟수 및 크기, 계절성 추가 등의 옵션이 있고, 기본적으로 CausalImpact 함수에서 제공하는 베이지안 모델이 아니라, 가지고 있는 데이터로 직접 시계열 데이터를 베이지안 모델로 만들어서 이를 사용해서 CausalImpact 함수에 적용할 수도 있다.

간단하게 random으로 trend를 만들어서 이 trend에 따라 같은 데이터가 돌아가는 베이지안 모델을 만들어서 돌려보자.

```
post.period.response <- capita$y[post.period[1] : post.period[2]]
capita$y[post.period[1] : post.period[2]] <- NA

ss <- AddLocalLevel(list(),capita$y)
bsts.model <- bsts(capita$y ~ capita$x, ss, niter = 1000)
impact2 <- CausalImpact(bsts.model = bsts.model,post.period.response = post.period.response)

plot(impact2)

```

![Rplot3](http://datum.io/wp-content/uploads/2014/10/Rplot3-300x201.jpeg)

동일한 데이터이지만 살짝 다른 결과가 나옴을 알 수 있다. 살짝 달라보이지만 차이가 난다. 여기서는 실제로 영향력이 있는 것으로 나타났으며, 인과적 효과 역시도 더 유의하게 나타난다. 역시 데이터는 클렌징 모델은 튜닝.(...)

![cap2](http://datum.io/wp-content/uploads/2014/10/cap2-300x189.jpg)

Summary
=======

다양한 시계열 분석 방법이 있지만, 베이지안 구조를 사용해서 요인 변수를 적절히 활용하여 이 요인들의 효과와 이를 활용한 조건부 추론을 간단하게 만들 수 있는 패키지다. 논문 내용은 어렵지만orz 이를 해석하고 사용하는 것은 생각보다도 손쉽게 할 수 있다. 잘 활용하면 간단하고 재밌는 것들을 만들 수 있지 않을까 기대해 본다. (나도 좀 더 공부해야겠다.)

Reference
=========

[Google Blog](http://google-opensource.blogspot.kr/2014/09/causalimpact-new-open-source-package.html)

[GitHub CausalImpact](https://github.com/google/CausalImpact)
