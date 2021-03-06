---
layout: post
title: 사회통계학 관점에서의 A/B 테스트
---

이전에 실무에서 트랜잭션이나 로그 관련 데이터로 분석을 시작한 지 얼마 되지 않았을 때는 이에 대해서 찾아볼 자료도 그다지 많지 않았고 지금처럼 실무 사례나 방법론도 다양하지 않았다. 그래서 그나마 설문이나 극히 적은 데이터로 분석을 하던 분야의 이론들도 같이 살펴봤고 그 때 어설프게나마 접했던 것이 사회조사분석론이었다. 

그럭저럭 도움이 되었지만 아무래도 사용하는 데이터나 시스템의 성격도 다르고 이론적인 배경지식이 많아서 정말로 그냥 참고만 했다. 그리고 그 때 보았던 것들은 기술적이지도 않고, 근사해보이지도 않으며, 조금은 고루해보이기까지 하는 것들이었고, 그 내용을 나도 다른 사람도 한동안은 다시 볼 일이 없었다. 

하지만 서비스에서의 분석이란 결국은 사용자를 대상으로 하게 되고, 데이터의 성격만 조금 달라졌을 뿐이고 그에 대한 불확실성이나 궁극적인 목적이 달라진 것은 아니고, 그러다보니 결국 이전에 보았던 사회조사 분석론 내용 같은 것이 조금씩 여기저기서 다시 보인다. 그리고 우리는 그런 곳에서 참고할 것이 굉장히 많다. 이런 것이 뻔히 있음에도 무시하고 다시 고민하는 것은 흔히 말하는 바퀴 재발명밖에 되지 않는다. 

그 중의 하나가 A/B테스트다. 

A/B테스트는 기본적으로는 두 보기를 주고 사용자의 보기에 따라 달라지는 행동 변화를 추적하는 무작위 추출 실험 방식으로, 예전에는 아주 작은 UX 상에서만 사용되는 정도였고, 아주 조금의 여유만 있으면 가볍게(?) 시도할 수 있었다. 하지만 이제는 그 범위도 굉장히 넓어지고 일반적인 '비교 실험'을 통칭하는 말이 되어 버렸고, 중요하게 되었음에도 불구하고 여전히 너무나도 가볍게 사용한다. 그리고 '이건 좀 더 실험을 상세히...'라고 이야기하면 '이건 실험실이 아니고 현실의 실험이고 어쩌고...' 라고 한다.

하지만, 과연 예전에도 실험실에서 하는 실험 설계만 있었을까.

그럴 리 없다. 기본적으로 처음 '실험설계'라는 것이 나오게 된 것의 배경을 이해해보면 이는 더욱 쉽다. 통계적 실험 설계에 대해 처음 연구한 사람이 통계학의 아버지라고도 불리는 피셔고, 그 배경에는 밀크티 이야기가 있으며, 피셔는 통계학자이자 농학자였다는 것을 생각해봐도 더욱 그렇다. 

그렇다. 상관관계와 인과관계는 다른 것이고, 우리가 알고 싶어하는 것은 인과관계가 대부분이다...라는 말도 최근 와서 생겨난 말이 아니다, 라는 것도 이미 알고 있는데, 현재처럼 데이터를 사용하기 전에 이에 대해 고민하는 사람이 없었는가, 라고 하면 너무나도 우스운 이야기 아닐까. 그렇다면 옛날에는 현실에서 실험을 안 했을까. 역시 그럴 리 없지 않은가. 그런데도, 이런 관점을 가지고 있는 사람들이 보여서 조금 안타깝다.

이공계열의 많은 경우 실험실에서 일어나는 실험 외에도, 조금만 시선을 돌리면 다양한 사회과학쪽의 실험이 있다. 많은 사람들에게 [밀그램 실험](https://ko.wikipedia.org/wiki/%EB%B0%80%EA%B7%B8%EB%9E%A8_%EC%8B%A4%ED%97%98)이라든가 마시멜로 실험 같은 것은 꽤 친숙할 것이다.  이런 경우는 사람들을 모아두고 잘 통제한 후 하는 실험이었지만, 모든 경우가 그렇지 않고, 이를 위한 다양한 실험 방식이 이미 기존부터 있어왔다. 

![](https://cojette.github.io/slide1.png?w=600)

여기서 A/B테스트는 일종의 유사실험조사설계에 들어간다. 그리고 이에 대한 실험 설계라든가 주의사항 같은 것들도 이미 충분히 존재한다. 그래서 이야기했던 것들이 [서비스 실험 설계](https://cojette.github.io/experiments/)나 [서비스 실험 윤리](https://cojette.github.io/experimentalethics/)다. 더불어 서비스의 사용자 대상으로 하는 실험이므로 사용자 관점에서 좀 더 주의해야 하는 부분이 있다. 사용자는 실험 데이터 생산자로만 존재하는 것이 아닌, 모든 서비스를 존재하게 해주는 대상이다. 

![](https://cojette.github.io/slide2.png?w=600)

데이터를 통한 서비스 개선, 사용자의 행동 및 선호도 반영이라는 관점에서 A/B테스트의 활성화에 대해서는 데이터 분석이 주 업무인 입장에서 대단히 환영하고 있다. 하지만 의외로 많은 곳에서 '통계적 가설'과 흔한 '가정' 간에도 구분을 하지 못하고, 주의해야 할 점도 고려하지 않고 남용하는 경우가 보이고 있어서 아쉬운 마음도 든다. 어떤 것이든 매뉴얼 이상의 남용이 이루어지면 탈이 나는 법이고, 그래서 이에 대해서 주의를 환기하면 좋겠다는 마음이 든다.

관련해서 발표했던 자료가 있어서 같이 공유한다. 

[슬라이드쉐어](https://www.slideshare.net/cojette/ab-150118831)
