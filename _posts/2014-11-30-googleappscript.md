---
layout: post
title: GOOGLE SPREADSHEET에서 SCRIPT 사용하기
---

로컬 컴퓨터에서 사용하기 가장 좋은 통계 도구라면 개인적으로는 "MS Excel"이라고 제창하는 바지만, 간혹 회사별 보안 프로그램에 걸린다든가 공유가 불편하다든가 하는 점이 있어서 이에 대한 대안으로 많이 사용하는 것이 Google Spreadsheet이다.  하지만 아무래도 Excel보다는 기능에 제약이 많고 일부 함수의 경우에는 구현이 안 되어 있기도 하며,  Excel을 좀 많이 사용하는 사람들 같은 경우 VBA script를 사용해서 Excel macro 및 custom function을 사용하기도 하는데 이를 Google Spreadsheet에서 import해서 사용하거나 할 수 없어서, 정말 기본적인 스프레드시트의 역할로만 사용하고는 했다.

그러다 오늘 우연히 전혀 뜬금없는 [오리대마왕님의 포스팅](http://kingorihouse.tumblr.com/post/103968211979)을 읽다가  [Google Apps Script](https://developers.google.com/apps-script/)라는 존재를 알게 되었다.  Google Docs 및 기타 Google Apps에 확장/연결 가능한 스크립트로 Javascript 기반으로, 아직 이에 대해서 깊이있게 공부하지는 못했지만 보는 순간 바로 떠오른 것은 Google Spreadsheet에 Excel의 VBA Script 대용으로 쓸 수 있겠다! 라는 것이다.

간단한 예제를 살펴보자.

![](https://raw.githubusercontent.com/cojette/cojette.github.io/master/cap1.jpg)

해당 예제는 누군가가 영국에서 차를 사와서 주변 사람들과 나눴을 때 사용한 Google Spreadsheet의 일부다.  해당 경우 영국에서 카드로 원화로 계산해서 바로 원화로 계산했지만, 이 금액이 파운드로는 얼마 정도 하는 지 가늠하고자 한다고 가정하자. 하지만 Google Spreadsheet에서 환율 계산 기능을 바로 제공하지는 않으므로; 한국 원화에 대응하는 파운드 금액을 알려주는 함수를 작성해 보자.

우선 해당 페이지의 메뉴바에서 Toos -> Script Editor 로 들어간다. 그러면 에디터 창이 열리고, 여기에 함수를 넣으면 된다. 우선 간단히 파운드 환율에 해당 원화를 곱하는 함수를 만들자.

여기에 넣을 변수를 검색한다.

![](https://raw.githubusercontent.com/cojette/cojette.github.io/master/cap31.jpg)

이 값을 함수에 넣고, 파운드 표시를 추가하면 끝이다.

![](https://raw.githubusercontent.com/cojette/cojette.github.io/master/cap2.jpg)

깔끔하게 결과가 잘 나오는 것을 볼 수 있다.

(사실은 환율을 다이나믹하게 변하게 하려고 웹 검색 내역을 계속 갖다 쓰는 방법을 고민했지만 생각보다 그러면 json 처리 등 좀 더 손봐야 할 게 많아서 그런 내용은 천천히 보기로 했다. (...))

물론 계속 발전형이지만 워낙 구글 앱이 여러가지가 많은 데다가 자바스크립트 자체도 쉬운 편이라(나도 자바스크립트 잘 못한다. d3 때문에 이제 겨우 codecademy 랑 책 넘겨가면서 쪼작거리는 편이지만 직관적이어서 금방 익힐 수 있다) 금방 유용하게 사용할 수 있지 싶다. 이 스크립트로 google analytics 결과를 불러와서 google spreadsheet에서 편집해서 사용하는 것도 노리고 있다. 이 외에도 다양한 방법으로 원격으로 스프레드시트를 사용한 분석 작업을 할 수 있을 것으로 기대된다.
