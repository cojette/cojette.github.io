---
layout: post
title: 세상에서 가장 이해받지 못하는 영웅, 데이터 과학자 (1/3)
---

이 글은 구글의 Chief Data Scientist인 [Cassie Kozyrkov](https://twitter.com/quaesita)의 글([Part 1](http://bit.ly/quaesita_analysts), [Part 2](http://bit.ly/quaesita_bsides))을 저자의 허가 하에 번역한 것으로, 번역 본의 약 1/3에 해당하는 내용이다. 그림 및 링크는 모두 저자가 제공한 내용을 그대로 사용하였으며, 본 번역 내용은 [저자의 번역 글 블로그](https://medium.com/@kozyr_91350/korean-analytics-7ba0b7f48be3)에도 게재되었다. 

개인적으로 동의하는 내용이 많아 굉장히 흥미롭게 읽어서 번역을 하게 되었으며, 자신을 돌아보며 위치를 다듬는 계기도 되었다. 
긴 내용이지만, 데이터 관련 일을 하는, 혹은 같이 일하는 사람들이 읽어보고 동의를 떠나서 한 번 이런 저런 것에 대해 생각을 해 보았으면 좋겠다. 

_(해당 내용에 들어있는 링크들은 원문의 링크를 사용한 관계로, 영어이니 탐색 시 참고 부탁드립니다.)_ 

----
> 부제: 분석을 이등 시민으로 취급하다가 큰 코 다치는 이유

![](https://lh5.googleusercontent.com/lYa-qgmFemwnDoFxWNTrYfC02tymqH2kiRKNhmMlXyg0v5c9y3tw4k92WZr1oU1UPDflOVZA987VTgGiAMHW0LPtHoGnr4kVPCtocMidTUVeEBm-TRyFnKfoiCFSB_teQIV5Dv7H)

당신이 어떤 기술을 숭상할 것인지 결정할 때는 매우 조심해야 한다. 잘못된 선택이 미치는 영향은 손 쓸 수 없이 커져 버릴 수도 있다. 팀도 잘못 이끌게 되는 데다 불필요한 사람을 고용하게 되는 데다가, 진정한 영웅들이 회사를 그만두거나 최근 인기에 편승하는 당신의 우선 순위에 맞추기 위해 새로운 것을 배우는 일을 목도하게 될 것이다. 

## 트로피 쇼핑용 채용

[데이터 과학](http://bit.ly/quaesita_datasci) 분야의 최고 능력자를 고용한다는 것은 굉장히 어려운 일이고, 사실 그다지 놀랄 일도 아니다.  “풀스택" 데이터 과학자는 [머신러닝](http://bit.ly/quaesita_emperor), [통계](http://bit.ly/quaesita_statistics), [분석](http://bit.ly/quaesita_datasci)을 통달한 사람이다. 이런 삼위일체를 이룬 사람을 찾지 못한 팀의 경우, 이 중 가장 구미가 당기는 [한 가지 분야의 전문가](http://bit.ly/quaesita_bubble)에게로 눈을 돌리게 된다. 과연 단상에 오를 기술은 어떤 것일까?

[오늘날 데이터 과학 분야의 대세](http://bit.ly/quaesita_bubble)는 SF적인 요소를 살짝 가미한 세련된 형태로, 고용 시장에서 사랑하는  [AI와 머신 러닝](http://bit.ly/quaesita_ai)을 사용하는 것이다.  일등석을 노리는 또 다른 도전자로는 견고하고 수학적인 우수성으로 역사와 전통을 자랑하는 [통계](http://bit.ly/quaesita_statistics)가 있다.  그렇다면 분석가는 어떨까?

![](https://lh4.googleusercontent.com/8nGmmfK6hSQ3v68w7QFaHMrtkW2BfJsAHDGdkNl9AIGnZIL-WyTMtvNe8-zPg2N7sXqtlmxUjbcKdbiDVSox58RNYv_giSGf3NtOp9KszPOu_VXP4PO-lpwNxmg7RZ9_U0I0ArRL)

만약 당신의 주전공 분야가 데이터 [분석](http://bit.ly/quaesita_datasci) (혹은 데이터 마이닝이나 비즈니스 인텔리전스)이라면, 앞서 말한 동료들이 당신 앞에서 뻐기거나 취업 시장에서 이들과 같이 일하기 위해서는 관련 분야 실력을 키워야 한다는 말을 면전에서 듣게 되면서 자존감이 무너지는 일을 겪게 될 수 있다. 

이 분야에 익숙하지 않은 사람들이 잘 인지하지 못하는 것은 앞서 말한 [데이터 과학 산하](http://bit.ly/quaesita_datasci)의 세 직업이 각각 완전히 다르다는 것이다.  세 직업 모두 동일한 방식을 사용하기는 하지만 이 직업들의 유사성은 이 것이 끝이다.  훌륭한 분석가란 다른 데이터 과학쪽 혈통의 적자 버전이 아니라, 효과적인 데이터 활용을 위한 전제 조건이다. 그들이 회사를 그만두는 것은 분명 위험한 일이지만, 만약 당신이 이들을 과소평가한다면 그들은 당신을 떠날 것이다. 

![](https://lh5.googleusercontent.com/cBFgHYNV8AINonlehiLeUBwChVOavjINmP8aGcnMlZ4jJvy_-TkKUpdwdFg1y_XgJwu4kbTUqAXM_6UfmN9JuLnhxQVmHRi3O3a--tPfeLMT_drSmE-eHhtnEol7DQOwCF8JFpX8)

## 일종의 존엄성

데이터 분석가에게 통계나 머신 러닝 실력을 기르라고 하는 대신, 본인 분야의 실력을 더 높이라고 격려해 주는 것은 어떨까. 데이터 과학은  한 분야에서 탁월한 것이 두 분야를 적당히 하는 것을 이기는 괴수와 같다. 

_세 가지 데이터 과학 분야 각각 모두 나름의 우월한 면이 있다. 통계학자는 정확성을, ML 엔지니어는 성능을, 분석가는 속도를 높인다._

각 분야에서 최고의 전문가라면, 세 분야 모두 동등하게 단상에 오를 자격이 있지만 서로 매우 다른 서비스를 제공한다. 이 미묘한 부분을 이해하기 위해 데이터 과학 각 분야에서 제대로 탁월한 경우, 무엇을 얻게 되고, 각 직무에서 살아남으려면 어떤 성격이 필요한 지를 살펴보도록 하자. 

![](https://lh4.googleusercontent.com/1_uaEN5ZrQjB2dyY5xrmn2RMODL6w-RDTbuMInU8ArQA9L1tmD08KOLxm5_sxcybQN4m7gmFgF2KIwSphw4Kyl5IlsZaClFyZ2qdb3fb)

## 통계의 강점: 정확도

데이터를 넘어서서 결론에 도달할 때의 전문가로서 [통계학자](http://bit.ly/quaesita_statistics)는 불확실한 세상에서 자신을 속이는 것으로부터 최고의 보호 수단이다.  그들에게 있어서, 무언가를 대충 추론하는 것은 백짓장처럼 아무런 생각을 하지 않는 것보다 더 큰 죄여서, 훌륭한 통계학자가 당신의 부풀은 꿈에 제동을 걸어줄 수 있을 것이다. 그들은 까치발을 선 채로 문제에 방법론이 제대로 확인되었는지 깊숙이 들여다 볼 것이고 주어진 정보로부터 어떤 추론이 유효할 것인지를 끊임없이 고민할 것이다. 

많은 사람들은 [통계학자](http://bit.ly/quaesita_statistics)가 본질적으로 인식론자라는 것을 생각지 못한다. 확실성이나 불확실성은 마법으로 이루어지는 것이 아니므로, 그들의 역할은 진실을 만들어내는 것이 아니라 가능한 정보를 통해 구미에 맞는 가정을 합리적으로 통합하는 것이다. 

**결과**: 리더가 위험을 제어하는 방향으로 중요한 결정을 내릴 수 있도록 도와주는 통찰력을 제공할 수 있다.

놀라운 일은 아니지만, 많은 통계학자는 어떠한 철학도 없이 방정식만 갖다 쓰려는 “신생 기업"에 대해 독설을 하는 경향이 있다. 통계학자를 대하기 힘들게 느껴진다면, 다음의 응급처치를 적용해 보자: 데이터 이상의 어떠한 결론도 내지 말자. 이런 경우 그들이 애초에 필요하지 않다. _( 행동보다 말이 쉽지 않나? 특히 중요한 시작 결정을 할 때는 더욱 그렇다.)_

## 머신 러닝의 강점: 성능

만약 당신이 " _넌 99.99999% 정확성 테스트를 통과하는 모델을 만들지 못할 거야_ " 라는 말에 " _두고 봐_ " 라고 대답한다면 당신은 [머신 러닝 응용](http://bit.ly/quaesita_realitycheck) /AI 엔지니어일 것이다. 머신러닝 전문가는 프로그래밍 코드로 돌아가는 프로토타입과 실 서비스 단계까지 만들어봤고 몇 년 동안 매년 실패를 겪으면서 단련된 회복성을 가지고 있어서, 그들은 교과서에는 완벽한 해답이 없다는 것을 알고 있다. 대신 그들은 [시행 착오의 마라톤](http://bit.ly/quaesita_emperor)에 뛰어든다. 각각의 새로운 옵션을 시도하는 데 [얼마나 오래 걸릴지에 대한 직감](http://bit.ly/quaesita_roles)이 뛰어난 것은 엄청난 이점이며 이는 알고리즘이 작동하는 방식에 대해 자세히 아는 것보다 소중하다(두 가지 모두 가지고 있는 것이 좋지만).

![](https://lh6.googleusercontent.com/kRVA9QM2X0VN8qx0ePGDXyYggh53jqVfMn8v-WcbvfmnZXYZSymXmlFOSM88F6Im1hY-bIKrvOZ_ag7z1nVV7BVhZbUu0A5HmWfFNd-avRrtXR7D4oZxgHUSmJxjh4Ch9jGQ5KTc "'돌아가게 할 거야.' -엔지니어")

**결과**: 통계학자의 엄격한 테스트 기준 통과하고 비즈니스 리더가 요구하는 대담한 성과를 전달할 수 있는 까다로운 작업을 자동화하는 시스템을 만들어낸다.

성능은 지표를 완수하는 것 이상을 뜻한다 - 믿을 만 하고, 확장 가능하며, 실 서비스에서 잘 작동하는 유지보수가 쉬운 모델을 뜻한다. 엔지니어링 능력이 우수해야 하는 건 필수다. 

## 넓이 대 깊이

앞의 두 역할의 공통점은 이 둘은 특정 문제에 대해 손이 많이 가는 해결책을 제공한다는 것이다. 만약 문제가 풀리기만 해도 되는 거라면, 굳이 그들의 시간과 당신의 돈을 낭비할 필요가 없다. 비즈니스 리더 간에 종종 회자되는 한숨 섞인 이야기로, [“우리 데이터 과학 그룹은 쓸모가 없어.”](http://bit.ly/quaesita_dsleaders) 가 있는데, 보통 이런 경우 이런 집단에는 분석 전문가가 없다는 문제가 도사리고 있다. 


----


_(다음에 계속...)_
