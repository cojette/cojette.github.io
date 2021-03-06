---
layout: post
title: 머신 러닝에서 알고리즘 공부를 말할 때 내가 하고 싶은 이야기
---

AI Conference에서 인상 깊게 들은 talk으로 머신 러닝 계의 전설이 아닌 레전드 피터 노빅느님의 키노트가 있었다. 무수한 딥러닝/머신 러닝 프레임워크들이 등장하면서 AI 프로그램도 공장제;; 가 되었지만 여기서 간과되는 것이, 머신러닝을 일반 프로그래밍처럼 다루게 되는 것이다. 그래서 모델을 프로그램 짜는 양 만들고, 데이터 training을 디버깅마냥, training 반복을 프로그램 패치하는 것과 유사한 개념으로 받아들이게 되는데 실제로 이런 경우 간과하게 되는 것들이 많다는 것이다. 특히 결과가 명확하게 떨어지는(그리고 그렇게 되기를 지향하는) 프로그램들과는 달리, 기본적으로 머신 러닝 알고리즘은 불확실성을 최소화하려고 할 뿐 모든 과정에서 불확실성과 확률이 존재하는데, 이 존재를 고려하지 않는다는 것이다.

많이 돌려서 말씀하신 것이겠지만, 사실 피터 노빅느님이 작년 상반기까지만 하더라도 ‘프로그래머들이여 머신 러닝을 배워라’ 라는 talk 를 주구장창 하셨던 걸 생각해 볼 때, 1년 사이에 많은 한숨과 빡침을 겪었을 것이라는 것은 안 봐도 비디오인 것이다.

그리고 이런 오해는, 실제로 ‘제대로 된 공부를 하지 않고 도구 사용에만 익숙한 사람들이 많기 때문’에 오는 것이라고 생각한다.


최근, ‘프로그래머가 알고리즘을 알아야 하느냐’ 라는 주제로 개발자와 (나 포함) 주변 사람들 사이에서 아주 많이 회자되었다. 많은 의견들이 있었고, 흥미로웠지만 조금은 서글픈 이야기들이었다. 뭐랄까, 다들 공부해야 할 것이 너무 많아서 피로감이 늘어난 상태랄까.

그러다보니 요즘 머신 러닝에서도 똑같이 작용하는 것 같다. ‘수학 배경이나 알고리즘 이런 거 복잡하게 알 필요 없고 어떤 기능이 어떤 용도에 사용되는 지만 알면 된다’ 뭐 이런 것. 이해를 못 하는 건 아니다. 사실 이런 이야기는 머신 러닝 이전부터 그런 알고리즘을 계속 사용하던 데이터 분석(데이터 마이닝/고급 분석/데이터 사이언스 등등등- 이후 머신 러닝으로 통칭한다)에서도 늘 듣던 말이기 때문이다! 하지만 이 담론이 이제는 머신러닝이 흥하고 만인이 알아야 할 것 같다보니 관심있는 사람들 모두에게 퍼졌을 뿐이다. 피터 노빅 같은 레전드분들도 배워야 한다 막 이러니 배워야 할 것 같은데 이건 개념부터 다르게 들어가는 것 같고, 그러다보니 생긴 것도 비슷한데 일단 간단하게 쓰는 법과 용도만 알아도 충분하지 왜 속의 복잡한 수학 내용까지 우리가 알아야 하는가, 이거 말고도 공부해야 할 게 뱅만가지인데, 같은  생각. 오죽하겠는가. 이 쪽의 업을 하고 사는 나도 공부하기 싫고, 그나마 익숙하지만 그럼에도 불구하고 봐야 할 게 뱅만가지여서 질리고 피로감이 몰려오는데.

하지만, 피터 노빅의 말을 그대로 옮기지 않더라도, 대충 어떤 데이터가 들어가고 어떤 결과가 나오며, 이걸 어떤 용도로 사용한다, 만 수박 겉핥기 식으로 안다고 해서 그걸 사용할 수 있냐면, 그건 아니라고 생각한다. 특히 머신 러닝처럼 ‘불확실성’을 안고 사는 경우에는 더욱 그러하다.

물론 재미로 무해한 실험용 데이터를 가지고 ‘우와 뭔가 신기한 그림이 그려진다’ ‘뭔가 돌렸더니 결과가 나온다’ 정도만 이해해도 충분하다면 정말 그냥  공부 안 하고 그냥 함수들만 돌려봐도 충분하다. 하지만 이걸 가지고 머신 러닝을 쓸 줄 안다, 이해했다 라고 하면 그건 아니지 않을까.

알고리즘을 실제로 구현할 수 있으면 정말 좋겠지만 (나를 비롯하여) 모두가 그럴 수는 없을 것이라고 생각한다. 하지만 알고리즘을 구현하는 것과, 내부 구조를 이해하는 건 천차 만별이다.  구조를 이해하지 않고, 단순히 입력값, 출력값, 용도만 알아서 사용하면 결과가 나와도 이 것이 얼마나 제대로 된 결과인지, 사용해도 되는지, 혹은 이걸 사용하기 어렵다면 왜 어려운 지, 어느 부분을 수정해야 하는 지를 알 수 없다. 더불어 머신 러닝 알고리즘은 변수라든가 튜닝해야 하는 부분들도 다수 있고, 데이터마다 결과가 달라지기 때문에, 일반적으로 구현된 것을 그냥 기본값으로 가져다 쓴 다음에 ‘이게 성능이 좋다 나쁘다’ 판단하기마저 어렵다. 특히 결과만 보고 틀렸다는 것을 바로 알 수 있는 다른 프로그래밍보다 더 위험한 것은, 그 특유의 ‘불확실성’ 때문이고, 이를 이해하기 위해서는 최소한의 확률적 지식과 알고리즘의 배경과 개념 자체에 대한 이해가 선행되어야 한다. 더불어 데이터 같이 각각의 도메인과 컨텍스트를 함의하는 데이터를, 형태가 동일하다고 같은 곳에 동일하게 사용할 수 있는 것도 아니므로 입력하는 데이터에 대한 사전적 이해도 필요하다. 실제적으로 이를 ‘다루는’ 사람이 과정과 결과에 대한 이해가 없이 생긴 형태와 흔히 말하는 큰 범위의 용도만 알아도 된다고 생각하는 건 굉장한 오만이다. 그리고 실제로 이런 오만으로 나오는 결과를 우리는 이미 몇 가지의 실제 사례(와 수많은 SF)에서 보지 않았는가.

더불어, 역시 다른 알고리즘이나 다른 학문에서도 마찬가지지만, 머신 러닝 내용들도 보면 별 거 아니고 실제 효용성도 없는 것들을 그나마 꾸역꾸역 하겠다고 많은 훌륭하신 분들이 만들언 놓은 것들을 천천히 보노라면 사람이 매우 겸손해지고, 해야 할 것은 한도 끝도 없어진다. 그래서 나는 요즘의 ‘이것만 알면 되고, 이것만 쓰면 되고, 다른 건 알 필요 없다’는 말이 매우 오만하게 들리고, 불편하다. 물론 세상에 배워야 할 것은 넘쳐나고, 불필요한 것들을 공부하느라 당장 급한 걸 공부를 못 하고 있을 수도 있으니 그런 경우 일단 급한 것부터 먼저 공부하는 것이 좋겠다. 하지만 난 그 누구라도, ‘이것만 알면 되지, 더 알 필요 없어’ 라고 단정짓는 건 좋지 않다고 생각한다(그리고 정말 레전드이신 분들일 수록 이런 말을 안 하지).


**배움이란 ‘낯선 것에서 익숙함을 찾고’ ‘익숙함에서 낯섦을 찾는 것’**이라는 말에 공감한다. 그래서 배움의 시작은 일단 ‘낯선 것에서 익숙함을 찾는 것’이고, 그래서 처음 접하는 분야라도 익숙한 형태가 있으면 그걸 쓰면 되지! 라는 접근도 매우 좋다고 생각한다. 하지만 여기서 ‘낯설었던’ 그 배경과 내용을 조금도 생각하지 않고 그냥 끝내고, 그런 후에 이 익숙한 형태만으로 만족하고 사용해도 괜찮을까. 나는 이런 식의 배움은 단순히 dark side라고 생각한다. quicker, easier, more seductive. 그리고 우리는 그 끝을 알지 않는가. 특히 머신 러닝처럼 파급력은 점점 더 커져가고, 불확실성도 더욱 더 커지기만 하는 분야에서는 더더욱.
