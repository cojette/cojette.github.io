---
layout: post
title: 데이터 계산 언어로서의 R
---

업무에서 주로 R을 사용하고, R 번역서를 두 권 냈음에도 불구하고, R이라는 언어에 대해서는 항상 의구심과 애증이 존재한다. 다른 프로그래밍 언어와는 좀 다르다보니, 이게 관점에 따라서는 불완전하다는 느낌도 들고, 지저분하다는 느낌도 들며, 특히 다른 프로그래밍언어의 개념에 조금이라도 익숙하다면 불편하고 답답하기 그지 없어진다. 그래서 이제는 굉장히 보편화되었음에도 불구하고, R에 대해서는 여전히 찬반양론도 높고 다른 프로그래밍언어로 웬만한 계산을 처리하고 싶어하는 경우도 많다.

하지만 생각해보면, '프로그래밍'관점이 아니라 '데이터' 및 '계산' 관점에서 보면 R만큼 적합한 언어도 아직까지 찾기 힘들다.

1. 일반적인 R의 장점: 무료고, 패키지도 다양하고, (물론 GUI 가 잘 갖춰진 다른 통계 도구들보다는 어렵지만) 스크립팅 언어 식이라 다른 프로그래밍 언어보다는 허들이 낮은 편이다. (데이터 타입이나 포인터나 객체 등의 개념이 녹아있지 않아 선 이수 과정이 적다. 물론 이로 인해서 보다 깊은 핸들링이 어려워서 불편해하는 사람들도 있지만, 이는 '계산'이 아닌 '구현'이나 '튜닝' 관점에 가깝다.)

2. 다양한 데이터 '형태'를 처리할 수 있다.
수학 계산을 위해 기본적으로 필요한 벡터 및 matrix가 시간대 성능비 가장 효과적으로 구현되어 있고, RDB의 테이블, key-value 구조마저도 list 형태로 만들면 된다. (...) 그리고 이런 다양한 형태의 데이터를 수학적으로  쉽게 처리할 수 있고, 수많은 패키지 덕분에 이를 DB table이나 XML이나 JSON 등으로 바꾸기도 쉽다.
프로그래밍 언어의 기본도 못 한다고 생각하는 포인터 1부터 시작하는 점도, 프로그래밍이 아니라 데이터 관점에서 생각하면 당연한 일이다. 1번 행을 부르면 첫 번째 행이 나오는 게 데이터 관점에서는 굉장히 당연한 것 아닌가.

3. 기본 연산이 메모리 상에서 처리되는 것.
메모리가 아무래도 대용량 처리에는 무리인지라(서버 성능이 낮을 수록 더더욱) 요즘처럼 '빅데이터'가 흥하고 대용량 데이터를 간단히 처리해야 하는 경우에는 그다지 R이 유용한 언어가 아님에도 불구하고 어쩌다 R이 빅데이터 분석 도구로 떠오르면서 이 문제에 대해서도 비난을 듣고는 한다. 하지만 어느 정도 전처리로 정제되어 양이 줄어든 수치 데이터를 다양하고 복잡하게 연산(메모리가 따라주는 한)처리하는 것은 메모리에서 하는 것이 적절하다.

SQL이 좀 복잡한 연산처리를 하려면 굉장히 번거롭고 불편하고 생긴 것도 프로그래밍 언어와는 거리가 멀지만 '데이터 처리' 영역에서는 자신의 일을 충분히 수행하고 있고 이 영역에서는 인정하는 것처럼, R도 '데이터 계산' 영역에 한정해서 생각한다면 단점으로 보이는 것들이 보다 적어질 수도 있고, 거부감도 좀 더 적어지지 않을까 하는 생각을 한다.
