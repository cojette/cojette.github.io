---
layout: post
title: 세상에서 가장 이해받지 못하는 영웅, 데이터 과학자 (1/3)
---

이 글은 구글의 Chief Data Scientist인 [Cassie Kozyrkov](https://twitter.com/quaesita)의 글([Part 1](http://bit.ly/quaesita_analysts), [Part 2](http://bit.ly/quaesita_bsides))을 저자의 허가 하에 번역한 것으로, 번역 본의 약 1/3에 해당하는 내용이다.
본 내용은 저자의 번역 글 블로그에도 게재 예정이다. 

개인적으로 동의하는 내용이 많아 굉장히 흥미롭게 읽어서 번역을 하게 되었으며, 자신을 돌아보며 위치를 다듬는 계기도 되었다. 
긴 내용이지만, 데이터 관련 일을 하는, 혹은 같이 일하는 사람들이 읽어보고 동의를 떠나서 한 번 이런 저런 것에 대해 생각을 해 보았으면 좋겠다. 

(해당 내용에 들어있는 링크들은 원문의 링크를 사용한 관계로, 영어이니 탐색 시 참고 부탁드립니다.) 

----
> 부제: 분석을 이등 시민으로 취급하다가 큰 코 다치는 이유

![](https://lh5.googleusercontent.com/lYa-qgmFemwnDoFxWNTrYfC02tymqH2kiRKNhmMlXyg0v5c9y3tw4k92WZr1oU1UPDflOVZA987VTgGiAMHW0LPtHoGnr4kVPCtocMidTUVeEBm-TRyFnKfoiCFSB_teQIV5Dv7H)

당신이 어떤 기술을 숭상할 것인지 결정할 때는 매우 조심해야 한다. 잘못된 선택이 미치는 영향은 손 쓸 수 없이 커져 버릴 수도 있다. 팀도 잘못 이끌게 되는 데다 불필요한 사람을 고용하게 되는 데다가, 진정한 영웅들이 회사를 그만두거나 최근 인기에 편승하는 당신의 우선 순위에 맞추기 위해 새로운 것을 배우는 일을 목도하게 될 것이다. 

##트로피 쇼핑용 채용
[데이터 과학](http://bit.ly/quaesita_datasci) 분야의 최고 능력자를 고용한다는 것은 굉장히 어려운 일이고, 사실 그다지 놀랄 일도 아니다.  “풀스택" 데이터 과학자는 [머신러닝](http://bit.ly/quaesita_emperor), [통계](http://bit.ly/quaesita_statistics), [분석](http://bit.ly/quaesita_datasci)을 통달한 사람이다. 이런 삼위일체를 이룬 사람을 찾지 못한 팀의 경우, 이 중 가장 구미가 당기는 [한 가지 분야의 전문가](http://bit.ly/quaesita_bubble)에게로 눈을 돌리게 된다. 과연 단상에 오를 기술은 어떤 것일까?

[오늘날 데이터 과학 분야의 대세](http://bit.ly/quaesita_bubble)는 SF적인 요소를 살짝 가미한 세련된 형태로, 고용 시장에서 사랑하는  [AI와 머신 러닝](http://bit.ly/quaesita_ai)을 사용하는 것이다.  일등석을 노리는 또 다른 도전자로는 견고하고 수학적인 우수성으로 역사와 전통을 자랑하는 [통계](http://bit.ly/quaesita_statistics)가 있다.  그렇다면 분석가는 어떨까?

![](https://lh4.googleusercontent.com/8nGmmfK6hSQ3v68w7QFaHMrtkW2BfJsAHDGdkNl9AIGnZIL-WyTMtvNe8-zPg2N7sXqtlmxUjbcKdbiDVSox58RNYv_giSGf3NtOp9KszPOu_VXP4PO-lpwNxmg7RZ9_U0I0ArRL)

만약 당신의 주전공 분야가 데이터 [분석](http://bit.ly/quaesita_datasci) (혹은 데이터 마이닝이나 비즈니스 인텔리전스)이라면, 앞서 말한 동료들이 당신 앞에서 뻐기거나 취업 시장에서 이들과 같이 일하기 위해서는 관련 분야 실력을 키워야 한다는 말을 면전에서 듣게 되면서 자존감이 무너지는 일을 겪게 될 수 있다. 

이 분야에 익숙하지 않은 사람들이 잘 인지하지 못하는 것은 앞서 말한 [데이터 과학 산하](http://bit.ly/quaesita_datasci)의 세 직업이 각각 완전히 다르다는 것이다.  세 직업 모두 동일한 방식을 사용하기는 하지만 이 직업들의 유사성은 이 것이 끝이다.  훌륭한 분석가란 다른 데이터 과학쪽 혈통의 적자 버전이 아니라, 효과적인 데이터 활용을 위한 전제 조건이다. 그들이 회사를 그만두는 것은 분명 위험한 일이지만, 만약 당신이 이들을 과소평가한다면 그들은 당신을 떠날 것이다. 

![](https://lh5.googleusercontent.com/cBFgHYNV8AINonlehiLeUBwChVOavjINmP8aGcnMlZ4jJvy_-TkKUpdwdFg1y_XgJwu4kbTUqAXM_6UfmN9JuLnhxQVmHRi3O3a--tPfeLMT_drSmE-eHhtnEol7DQOwCF8JFpX8)

## 일종의 존엄성

데이터 분석가에게 통계나 머신 러닝 실력을 기르라고 하는 대신, 본인 분야의 실력을 더 높이라고 격려해 주는 것은 어떨까. 데이터 과학은  한 분야에서 탁월한 것이 두 분야를 적당히 하는 것을 이기는 괴수와 같다. 

세 가지 데이터 과학 분야 각각 모두 나름의 우월한 면이 있다. 통계학자는 정확성을, ML 엔지니어는 성능을, 분석가는 속도를 높인다.

각 분야에서 최고의 전문가라면, 세 분야 모두 동등하게 단상에 오를 자격이 있지만 서로 매우 다른 서비스를 제공한다. 이 미묘한 부분을 이해하기 위해 데이터 과학 각 분야에서 제대로 탁월한 경우, 무엇을 얻게 되고, 각 직무에서 살아남으려면 어떤 성격이 필요한 지를 살펴보도록 하자. 

_(다음에 계속...)_
