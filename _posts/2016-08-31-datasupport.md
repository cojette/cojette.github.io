---
layout: post
title: 데이터로 말하기에서 종종 잊는 것
---

기업 환경에서 궁극적인 데이터의 목적은 의사 결정이라고들 한다. 이 말은 오래 전 경영학 때부터 지금까지, 기업환경은 무수한 탈바꿈을 하는 와중에도  빳빳하게 목을 치켜들고 존재감을 뽐내고 있다. 물론 기업환경의 변화에 따라 구체적인 활용에 대한 이론도 역시 계속 허물을 벗고 새로운 모습을 뽐내 왔지만, 그 안의 뼈대는 항상 동일하다.
회사의 중요한 수치의 변화를 확인하고,  그것에 대해서 결정을 내리는 것.

요즘은 데이터라는 개념이 많은 사람들에게 익숙해지고, 그 데이터가 '객관적'인 수치를 보여줄 수 있다는 것을 많은 사람들이 깨달아서, 데이터와 객관적 의사 결정은 더 이상 뗄래야 뗄 수가  없는 관계가 되었다. 그래서 데이터를 조금 더 많이 들여다보는 기업에서는, 기본적인  매출 등  기초  지표 외에도  다양한 것에 대해서 데이터를 활용해서 보다 객관적으로 판단하려고 시도하기 시작했다. 
그러면서 많이 시도되는 것이 **'가설'을 세우고 이를 '실험'해서  결과 '데이터로 증명'**하는 것이다.

하지만 여기서 많은 사람들이 종종 놓치는 것이  있다.

## 가설 설정
많은 사람들이  '가설'을 이미 자신의 머릿속에  있는 생각이라고 생각하고 이를 그대로 '가설'이라고  꺼내놓는다.  '강남  신세계가  강북  신세계보다  매출이  더 높을 거야.'  '관악구는  책이  많이 팔리니 술도  많이 팔릴거야.'  등등.
하지만 원래의 가설은, 특히 데이터로 수치를 만들 때  쓰는 통계학에서의 가설은 그런 것이  아니다.
가설과 함께 흔히 쓰이는 '실험', 그 '실험계획법'을 발전시킨 통계의 대부격인 로널드피셔가 실험 계획법을 만들때 정의되었던 가설은, 특히 실험의  주 가설인 귀무가설은 그런 것이 아니었다. 실험에서 가운데에 두고 사용하는 귀무가설,  혹은 영가설은 오히려 실험에서의 원래의 추측과 '반대되는 가설'을 영가설로 두고 이를 반증하는 방식으로  실험을 설계하고  진행하는 것이다.
이렇게 설정한 이유는 논리학에서 'A이면 B이다'가  참인 경우, 이에 대한 대우인 'B가  아니라면 A가 아니다'가 참인데, '지금 A인지 모르겠는데 B인 것 같다'라고 생각해서 이를 증명하고 싶다면 대우인 'B가  아니라고 했을 때 A가  아니어야겠는데...정말  그런가?' 를 확인하는 것이 맞기 때문이다. 또한 이미 B가 아닐 리가 없다는 확신이 있다면  굳이 실험을 할 필요가 없기 때문이다.
하지만 요즘  많은 사람들이 데이터를  통한 의사결정이라고 하는 것들을 볼 때, '실험' 혹은 '데이터로  증명'한다고 하면서 'B다' 라는 가정 자체를 그대로  '가설'이라고 부르고 이를 위한 데이터 분석을 하는  것을 왕왕 보게 된다. 심지어 그게 매우 성공적인 데이터  활용인 양 떠들어대고 있는 것들을 보게  되면  짜증을 넘어서서 안타깝다.
상세한 가설을 세우고  실험을 하는 것은  참  중요하고,  좋은 접근이기도 하다. 하지만  '가설'과, 개인의 '추측'  혹은  '확신'을  구분하지  못한다면  이런 가설은  그냥  없는 것이 낫다. '가설'을 빙자해서 자신의 '추측'에 대한 답을 만들려고 하지 말자. 이런 식은 '데이터 기반'이라는 탈을 쓴 '답정너'일 뿐이다. 차라리  '일단 잘 모르겠으니  A의  상태를   확인하자. 그 이후에 B를  정해야겠어.' 라는 방식이  훨씬  더  논리적이면서 데이터 기반의 접근일   것이다.

## 효과 분석
 요즘의  기업 환경은 빠르게 변하고,  많은  회사의 제품  또한  빠르게  변한다. 그리고 그런 변화가 실제로  고객에게  어떤  영향을 미쳤는지를  지속적으로  확인하고자  한다. 그리고 이제는 많은 곳에서 여러 데이터를 다양하게 수집하고 있으므로, 데이터를  이런 변화  파악에  활용하기도  좋을 것이다. 그리고 실제로 그렇게 하고 있고, 이런 효과 분석  방식을  조금  틀어서  A/B  테스트 등에도  활용하고는 한다.
그런데 여기서도  많은  사람들이 놓치고 있는 것이  있다. 이건 당연한  이야기라고  생각하지만 실제로  데이터를 보다  보면 자꾸  망각하는 사람들이  나온다.
어떤 이벤트와 어떤 것의  효과를 볼 때는 데이터를 **'시계열'**로 봐야  한다는 것이다. 

모든  일에는 전후가 있고, 모든 사건은 발생한 시간이 있으며, 무언가의 효과는 그 이후의 시간을 타고  흐른다.  그래서  어떤 일에 대한 반응을 살필 때는  시계열  데이터를  보고, 전후를 봐야 한다.  그리고  시계열로  데이터를 들여다보게 되면  더욱 많은 것이 눈에  들어올 것이다. 지금 시계열이 전천후로 치솟는 상태여서(trend) 이벤트가 잘 된 것  처럼 보이는지,   혹은 안드로이드  사용자가  원래 많았어서 업데이트 후에도  안드로이드  사용자가  더 많았는지(실험군 및  실험 환경  설정)  말이다.  단순히  안드로이드 업데이트  후  안드로이드  사용자가  더  많았다고 '이  업데이트는 성공적이야'  라고  말할  수는 없는 것이다.
물론 이렇게 말로 할 때는 '당연한 이야기를 왜  이렇게  구태여  하고 있나'라고  생각하지만,  나는  여러  환경을 접하면서 이런 사람들을,  시간이  지나가도  안  만난  적이 없다. 심지어는 그 중에는 나보다 실험도 훨씬  많이  하고  논문도 많이  쓰신  박사분들도 계셨다. 물론, 나도 언젠가 그러지 않는다는  법은 없다.
사람은 자신이 보고자  하는 것만 보게 되기 때문이다. 특히 아는 것이  많은 사람일 수록,  더욱  지적으로.


 요즘 '빅데이터' 등의 데이터가  논리적이고 객관적이라고  추앙받는 분위기고, 실제로 제대로  활용되는 데이터는 매우 강력한 힘을 가지고 있지만,  데이터도 없는데 있는 양 흉내낸다거나, 이런  식으로 데이터를 '답정너'로 활용하고,제대로 설정하지도 않은 '실험'을 운운해서  데이터를  바보로  만드느니, 제대로  된 '직관적  의사 결정'이 훨씬  나을 것이다.   직관적  의사 결정이  나쁜 것만은 아니고, 데이터를   볼 수 없거나  제대로  사용하지 않는 불확실한 환경에서는 오히려  더 나을  수도  있다.( 직관의 유용성에 대해서는 기거렌처 박사가 많은 책에서 설명했으니  그 쪽을  참고해보자(책들도  재밌다).)
데이터는 '객관적  의사 결정'의 도구다. 데이터를 활용해서 객관적인 의사  결정을 하고자  한다면,   데이터 만큼 의사 결정자나 분석가 역시도  해당  주제에 대해 객관적이  되어야 한다. 우선 자신도 모르게 한 쪽으로 치우쳐 있는 결과에 대한  확증을  최대한  걷어내야 할  것이다.  

