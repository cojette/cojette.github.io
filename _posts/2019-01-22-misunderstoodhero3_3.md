---
layout: post
title: 세상에서 가장 이해받지 못하는 영웅, 데이터 과학자 (3/3)
---


이 글은 구글의 Chief Data Scientist인 [Cassie Kozyrkov](https://twitter.com/quaesita)의 글([Part 1](http://bit.ly/quaesita_analysts), [Part 2](http://bit.ly/quaesita_bsides))을 저자의 허가 하에 번역했다. 
그림 및 링크는 모두 저자가 제공한 내용을 그대로 사용하였으며, 본 번역 내용은 [저자의 번역 글 블로그](https://medium.com/@kozyr_91350/korean-analytics-7ba0b7f48be3)에도 게재될 예정이다. 
이 내용은 [세상에서 가장 이해받지 못하는 영웅, 데이터 과학자 (1/3)](https://cojette.github.io/misunderstoodhero1_3/), [세상에서 가장 이해받지 못하는 영웅, 데이터 과학자 (2/3)](https://cojette.github.io/misunderstoodhero2_3/)에 이어지는 글이다. 

_(해당 내용에 들어있는 링크들은 원문의 링크를 사용한 관계로, 영어이니 탐색 시 참고 부탁드립니다.)_ 

----
## 만성적인 과소 평가의 위험성

*분석 전문가는 머신 러닝 엔지니어의 싸구려 형태가 아니며, 그들의 코딩 스타일은 속도의 목적에 맞춰진 것이다. 분석가도 불확실성에 기대지 않고 사실을 사용하는 사람들로 통계학자의 덜 된 형태도 아니다. "이게 우리 데이터에 나온 내용입니다. 현재 데이터에서 보여질 수 있는 것 이상으로 이야기하는 것은 제 업이 아닙니다. 하지만 아마 이걸 보면 의사 결정자가 통계학자가 이 문제를 좀 더 진행해 보게 하고 싶어질 겁니다…."*

초보자는 이런 일에 다른 두 [응용쪽 혈통](http://bit.ly/quaesita_roles)보다 데이터 과학의 수학을 더 잘 이해하는 상위 [분석가](http://bit.ly/quaesita_datasci)가 필요하다는 사실을 깨닫지 못한다. 이런 일에 새로운 가설 검정이나 알고리즘([연구자](http://bit.ly/quaesita_roles)의 일)을 만들어내는 게 필요한 게 아니라면, 통계학자나 ML 전문가는 다 만들어진 패키지와 검정 방식이 이 일에 적합한 지 확인한 후 이를 사용할 수는 있지만, 방정식과 직접 대면하는 것을 잊어버리곤 한다. 

한 가지 예로, 통계학자는  간혹 t 검정의 [p값](http://bit.ly/quaesita_statistics)을 구하는 식을 잊어버리지만(소프트웨어 패키지를 실행하면 된다), 이를 어떻게 사용하고 언제 사용해야 하며, 이에 대한 결과를 정확하게 해석하는 방식은 잊지 않는다. 하지만 분석가는 이를 바로 해석하려 들지 않는다. 분석가는 거대하고, 거친 다차원의 데이터셋의 형태를 먼저 살펴본다. 그리고 원본 데이터셋에서 어떤 패턴을 통해 p값 등의 숫자가 만들어졌는지 역으로 구한다. 수학에 대해 제대로 인지하고 있지 않으면, 그런 견해를 확보할 수 없다. 미묘한 차이지만, 이는 매우 중요하다. 

통계학자는 데이터 외부의 것들을 처리할 때, 분석가는 데이터 내에 있는 것에 천착한다. 각 분야에서 우수한 사람들의 경우, 양쪽 모두 수학을 심도있게 다루며 많은 경우 동일한 방정식을 다루지만, 그들의 일은 완전히 달라진다. 

마찬가지로, 분석가는 데이터를 나누고, 그룹을 정의하고, 이상 탐지를 할 때 머신 러닝 [알고리즘](http://bit.ly/quaesita_emperor)도 종종 사용한다. 분석가의 목적은 성능이 아니라 통찰을 얻기 위함이므로, [ML 엔지니어](http://bit.ly/quaesita_roles)와는 접근 방식이 다르고 간혹 잘 못하는 것처럼 보일 수도 있다. 역시나, 이는 다른 일에서 동일한 도구를 사용하는 경우일 뿐이다. 

이를 비유를 들어 요약해보면 다음과 같다. 외과의, 양복 재단사, 회사원 모두 핀을 사용한다. 하지만 그렇다고 이 사람들의 일이 모두 동일하거나 비교 가능한 것은 아니며, 모든 양복 재단사들과 회사원에게 역량 향상을 위해 외과 수술 기술을 익히라고 하는 것은 위험한 일이다. 

모든 비즈니스에서 필요로 하는 역할은 의사 결정자와 분석가 뿐이다. 만약 분석가가 없어진다면, 어떤 문제를 풀어야 할 필요가 있을 지를 고민해야 할 때 이를 누가 도와줄 수 있을까?

머신 러닝과 통계 기술을 가진 사람을 고용하고 높은 보상을 주는 것을 과하게 강조하다 보면 [분석가](http://bit.ly/quaesita_datasci)를 놓쳐버릴 수 있다. 그럼 어떤 문제를 풀어야 할 필요가 있을 지를 고민해야 할 때 이를 누가 도와줄 수 있을까? 당신은 원치 않는 불필요한 프로젝트나 분석 일을 하라고 요구 받게 된 비참한 전문가 집단과 덩그러니 남겨질 뿐이다. 당신의 데이터는 쓸모없게 된다. 

## 연구자를 보살피고 돌보는 것

이렇게 이야기 해도 그다지 귀에 들어오지 않는 많은 리더들은 (앞서 말한 것과 반대로) 통계와 ML 엔지니어 버전의 PhD를 고용하고 [연구](http://bit.ly/quaesita_roles)에 대한 중요성을 매우 강조한다. 물론 그들에게는 가치있고 중요하며 기존의 모든 알고리즘을 사용하여 해결하는 것이 불가능하다고 알려진 문제따위는 없을 것이다. 

![](https://lh4.googleusercontent.com/MYHtQfsKo__HYnq_z2V1qaxsph-3BOs335QMlEFEqethEWoe6NwPsWQLbXZBWWPNdGlNoEJI4PhL7qX253KEWlO8HRV8mTocjvcooQ2RdqINw-TEv8jqE2Rd3RHvrWzbbmp33f5k)

일단 [연구 부서](http://bit.ly/quaesita_roles)에 투자하고 있고 연구자에게 최근에 한 일에 대해 물어볼 계획이 없다면 괜찮다. [연구를 위한 연구](http://bit.ly/quaesita_fail)는 고위험성 투자로, 현실적으로 가치가 없다고 나올 가능성이 농후하기 때문에 정말 일부 회사만 이에 대해 투자해도된다.  

연구자는 당신이 문제 해결을 위해 적절한 문제가 있는 경우에만 연구 부서 외부에 속하게 된다. 그들의 기술은 이미 바로 돌릴 수 있는 형태로 만들어져 있지 않은 경우 새 알고리즘을 밑바닥부터 만들고 테스트하는 것이다. 만약 당신이 제시한 문제가 적절하지 않은 경우, 연구자는 암울한 시지프스의 굴레에 갇히는 경험을 하게 될 것이다(이것은 전적으로 연구자가 아닌 당신의 책임이다). 연구자는 대개 데이터 훈련 과정에 한 세월을 들이게 되는데, 이건 완전히 쓸데없는 일은 아니라는 점에서 그나마 존중받을 만 하다.

결과적으로, 적합한 프로젝트를 위해 다른 역할들을 고용하기 위한 적기는 분석가가 프로젝트를 명확하게 정의하고 그들이 이를 직접 해 보았다가 실패한 것으로 판명난 후다. *이 때*가 전문적인 발명가를 발굴할 시점이다.

## 핵심 내용 요약

이런 게 걱정이라면, 다른 [역할](http://bit.ly/quaesita_roles)들보다 먼저 분석가를 고용하라. 그들을 존중하고 충분한 보상을 해라. 그들이 가진(그리고 다른 사람에게는 없는) 역량을 보다 높이 키우도록 힘을 북돋아주자. 이 이야기에서 언급 된 등장 인물 중 데이터가 필요한 모든 비즈니스에 필요한 역할은[ 의사 결정자](http://bit.ly/quaesita_dmleaders)와 분석가 뿐이다. 다른 역할은 당신이 무엇이  필요한 지 정확히 알고있을 때만 사용할 수 있다. 분석가와 함께 데이터 관련 일을 시작하여 당신의 앞에 펼쳐진 풍부하고 아름다운 정보에 눈을 뜨게 되는 새로운 능력을 얻게 된 것에 감사하자. [영감](http://bit.ly/quaesita_damnedlies)은 매우 강력하고 쉽게 무시할 만한 것이 아니다.  

![](https://hbr.org/resources/images/article_assets/2018/12/Dec18_5_641662678.jpg?w=500)
_VICKI JAURON, BABYLON AND BEYOND PHOTOGRAPHY/GETTY IMAGES_ 

이 이미지는 HBR에 실린 글([ HBR article](http://bit.ly/quaesita_analysts))에 실린 것이다. 이 그림에 대해 가장 좋아하는 해석은 이 그림의 사람이 대세인 직업 명을 쫓아다니느라 분석가 무리를 쫓아내는 비즈니스 리더라는 것이다. 