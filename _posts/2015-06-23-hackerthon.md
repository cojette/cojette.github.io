---
layout: post
title: Data Hackerthon-단기 데이터 분석에 대한 소고
---

Strata Conference가 끝나고, 메일로 질문을 몇 개 받았는데 그에 대해 답을 주다가 어찌어찌 하다보니 한 메일을 준 분과 그 메일 쓰레드에 같이 참조되었던 사람들과 동시에 짧은 시간에 데이터를 뒤져서 인사이트를 뽑아내는 작업을 할 기회가 있었다. 대략 시간은 10시간. JSON으로 된 로그 파일과 간단한 로그 설명 파일을 넘겨받고 이를 멋대로 분석해서 time check와 결과와 분석 코드를 끝내고 공유하는 방식으로. 그래서 한 1주일 가량, 퇴근 후 1-2시간씩 붙들고 늘어지는 식으로 진행했었다. (그 주에는 정말 피곤해서 죽을 뻔 했다. 그나마 회사에서 야근이 없었기에 망정이지...)

굳이 이 것을 명명하지는 않았지만, 이런 방식은, 소위 말하는, 외국에서 왕왕 있는 것 같은 Data Hackerthon(이라고 쓰고 학교 텀프로젝트 라고 읽는다-아 아닌가) 이었다. 물론 팀플이 아니라 개인플이었고, 모여서 하지는 않았지만. (하지만 덕분에 시간과 장소예 제약을 받지는 않으니-물론 time checker가 있긴 하지만 어느 정도 신뢰의 문제다- 조금 더 발전된 방식이 아닌가! 하는 생각도 든다.)

그리고 결과는 좋지 않았다. 내 결과에 무슨 문제가 있냐고 요청해서 피드백을 받으니, '접근 방식은 흥미로웠지만 거기서 도출된 결과에 깊이가 부족하다'라는 것이었다. 별로 그에 대해 이견을 달 것은 없었다. 솔직히 시간이 부족해서 '이런 식으로 접근해서 더 자세히 살펴보면 좋을 것이다'라고 결과 정리를 해서 내면서도 별로 기분이 말끔하지는 않았으니까. 아니, 사실 하면서도 내내 새로운 경험이라 재밌기도 했지만 어딘가 마음 한 켠이 영 불편했다.

아마도 이런 작업이, 내 관점과 맞지 않아서리라.

차라리 제품을 만드는 것이라면, 아이디어가 있다면 그 아이디어를 간단하게 바로 프로토타이핑해서-이른바 린 스타트업에서 주창하는 MVP- 내놓을 수 있을 것이다. 그리고 아이디어가 주어진 상태에서 이를 보다 빠르게 개발하기 위해 짧은 시간 제한을 주는 것도 좋은 방법이라고 생각한다.

하지만 처음 접하는 데이터를 던져주고 여기서 명확한 인사이트가 있는 결과와 시각화까지 도출하는 것은 영 어려운 일이다. 물론 어느 정도의 듀 데이트는 필요하겠지만 내가 했던 10시간, 혹은 해커톤같이 하루 이틀동안 바짝 하는 방식은, 나로서는 잘 모르겠다. 사실 가뜩이나 처음 보는 형태의 데이터다보니 이게 어떤 식으로 접근해야 실제로 해당 비즈니스에 도움이 되는 데이터일 지도 잘 모르겠고, 날 로그를 가공하고 간단히 이리저리 뒤적거리면서 데이터를 이해하는 데에 거의 반 이상의 시간을 소모해야 했고(사실 이 것도 영 부족하다고 생각되었지만 시간 없어서 일단 그냥 했다. 아마 여기서 가장 기분이 좋지 않았을 것이다) , 거기다 이런 데에서 쓰게 되는 데이터는 아무래도 여러 제약이 있다보니 아이디어가 있어도 통계적으로 의미가 없어서 손을 못 대보는 것들도 왕왕 있었다. 이런 건 그냥 이러이러한 게 있다고 코멘트만 달기는 했지만, 그러면서도 영 찜찜하고.

어떤 피드백 중에서는 데이터 처리할 때 왜 대문자로 기록된 것과 소문자로 기록된 것을 같다고 처리하지 않았냐 라는 피드백도 있었는데, 이 것도 마음에 들지 않았다. 내가 거기서 대문자와 소문자로 쓰인 게 다르게 사용되는 지, 같이 사용되는지, 어떻게 알겠는가. 일단 해당 서비스에서 이 데이터가 어떤 식으로 사용되는 지 모를 때는 날 것으로 처리하는 게 나한테는 당연한 것이고, 그러다보니 서로 다르게 처리된 것인데. 이런 면들이 영 유쾌하지 않았다.

결국 데이터 해커톤이란, 경험치와 열정 페이-잘 되는 사람에게야 약간의 물질적 보상이 있겠지만-를 지불하고 주최 측에서 아이디어와 코드 초안을 얻을 수 있는 좋은 집단지성 경제 모델 아닌가 싶은 생각도 든다. 사실 이 짧은 시간동안 한 것 가지고, 특히 데이터 바닥에서는, 실제로 쓸 수 있는 것이 얼마나 나올 수 있을 지 의문이다. 대신 많은 아이디어 프로토타입을 얻을 수 있을 것이고, 비즈니스와 데이터에 익숙한 사람들이 여기서 힌트를 얻어서 정말 유용한 무언가를 만들어낼 수 있는.

이렇게 삐딱해진 것은 어쩌면 나 자신의 문제리라. 세상이, 이 업계가, 이런 식으로 점점 빠르게, 단타로 변해가고 있는 데 내가 아마 변화에 뒤처지고 손이 느리고 창의력이 부족해서, 적응을 못 해서, 이해력이 부족해서 부정적인 시선이 앞서는 것이라는 생각도 든다. 하지만, 아직은, 이런 시도는 당연히 재밌고 한 번 해 볼 만한 것이지만 이 게 주류 방향이 맞는 것인지는 여전히 의문이다.

뭐, 어쨌든 새롭고 재밌는 경험이었다. 생각도 좀 많고 개인적으로는 정신적 스크래치가 큰 작업이기는 했지만, 그래도 분명 얻은 게 있었을 것이다. 하지만 앞으로도 이런 기회를 접했을 때 또 참여를 할 지는 미지수다. 아직은.