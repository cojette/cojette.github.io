---
layout: post
title: Business Analyst와 데이터 추출
---

> **A business analyst (BA)** is someone who analyzes an organization or business domain (real or hypothetical) and documents its business or processes or systems, assessing the business model or its integration with technology.
>(출처: [위키피디아](https://en.wikipedia.org/wiki/Business_analyst))

내가 처음 회사에 들어갔을 때, 내 명함에 찍혀서 나온 직함은 ‘Business Analyst’였다. 기업용 솔루션회사였던 그 회사에서, 보통 레벨이 0인 사람들에게 할당한다는 직함. 
처음에는 그 묵직한 직함에 당황했지만, 하게 된 일이 기술 컨설팅이었고 데이터와 기업 솔루션이다보니 비즈니스 도메인을 알아야 하고, 프로세스를 알아야 하며, 시스템을 이해해야 했으니 아주 관계없는 직함은 아니었다.

그러다 좀 더 ‘분석’에 초점이 맞춰진 일을 하게 되고, 자연스럽게 내 직함도 ‘Data analyst’로 넘어갔다(그 이후 나의 혼란스러운 직함들에 대해서는 생략한다). 
그러면서 저 BA라는 직함도 자연스럽게 잊혀져갔다. 사실 다시 볼 일이 없는 직함이라고 생각했다.

요즘 저 직함이, 다시 슬금슬금 들린다. 내가 다시 듣게 된 것은 작년 즈음이었다. 
나와 데이터 분석가에 대해 이야기하던 어떤 분이 말씀하셨다(필요에 의해 A라고 부른다).


> A: 아니, 우리에게 필요한 건 DA(Data Analyst)가 아닌 BA에요. 당신은 DA고, 그래서 당신은 우리와 어울리지 않아요.’
> 나: BA요? 여기서 BA가 왜 나오나요? BA는 무슨 일을 하는 사람이라고 생각하시나요?
> A: **DA는 그, 데이터 사이언티스트라고 하는… 자체적으로 어떤 주제에 대해 데이터를 분석하는 사람이라면, BA는 비즈니스에서 필요한 데이터를 경영진이나 마케터 등에게 가져다 주는 사람이지요.**

나는 이게 무슨 소리인가 어안이 벙벙했다. 언제부터 BA의 정의가 이렇게 되었던가.  이 말은 나에게는 여러 모로 이상하다.

1. 그 BA, 내가 아는 BA는 아닌 것 같고.
2. 데이터 분석가가 비즈니스에서 필요한 데이터를 만들지 않으면 왜 있어야 하며.
3. 저 BA라는 정의, 이상하게 이 쪽에서 흔히 말하는 ‘데이터 추출하는 사람’의 정의와 매우 비슷합니다…?!

도대체 이 해괴망측한 정의는 어디에서 나왔는가 궁금해진 나는 주변 사람들에게 비슷한 내용을 물어보았다. 
어디서부터인지는 모르겠으나, 이런 개념이 유명해진 것은 c모 회사에서 의사 결정이나 경영진에서 데이터와 지표를 매우 열심히 사용하고, 여러 부서에서 여러 사람이 빠르게 데이터를 보고 의사 결정을 하게 되었고, 각각의 사람들에게 맞는 (주로 단순한) 데이터를 여기저기서 빠르게 추출해서 만들어줄 사람이 필요하게 된 것이다. 그래서 비즈니스에서 필요한 데이터를 준다는 의미에서 DA와는 다른 BA라는 이름을 붙이게 되었다나.

나 이거 뭔지 알아. 이거 뱅만년전부터 있던 '데이터 추출하는 사람' 이야.

별로 할 말이 없어졌다. 그리고 나는 이에 관련해서 다시 대화를 하게 되었다.


> 나: 네, 그렇다면 원하는 BA의 자격 요건이 뭔가요?
> A: 빠른 커뮤니케이션이요. 일반적인 정의같은 것보다, 같이 일하는 사람들이 말하는 것을 빠르게 알아듣는 게 필요하지요.
> 나: …네? 그러면 A님이 ‘콩’이라고 하면 알아서 ‘콩떡’으로 알아듣고 관련 데이터를 뽑아야 하는 건가요?
> A: 비약하자면 틀린 말은 아니네요.
> 나: ….

난 더더욱 할 말이 없어졌다.


1. 기본적으로,  **자신이 보는 데이터는 추출부터 결론까지 최대한 한 곳에서 내는 것을 지향해야 한다**고 생각한다. 
늘 이야기하지만, 데이터 분석에서 7-9할이 데이터 끌어오고 가공하는 일이다.  
물론, 안 익숙한 사람들이 처음에 데이터에 직접 접근하기에는 어려울 수도 있고, 도움을 요청할 수도 있다. 
하지만 도움을 받는 정도가 아니라, 아예 주로 원하는 기술적, 수학적으로 정돈된 지표, 혹은 지표보다는 조금 덜 가공된 시계열 등의 데이터, 이런 걸 전문으로 할 사람을 뽑다니 이건 무슨 개념인지 모르겠다. 
이걸 남을 시키고 가져온 데이터 가지고 단물만 뽑아먹겠다는 것은 무슨 재주는 곰이 넘고 돈은 서커스 단장이 받는 소리 하고 있는 것인가.
늘 이야기하지만, **데이터 분석가는 데이터 추출하는 사람이 아니다.** 
다만 자신의 본업이 분석이고, 이를 위해 본인이 쓸 데이터를 본인이 가공할 줄 아는 것일 뿐이다.
아, 그래서 이 사람들이 데이터 분석가가 아닌 **“BA”**를 찾는 거지.

2. **데이터를 다루는 사람에게 기본적인 수학적, 기술적 지식 만큼 중요한 것이 논리력**이라고 생각한다. 그리고 그 논리의 밑바탕을 이루는 것은 정확한 정의다. 
이 정의를 자기들 멋대로 꼬아버리는 바람에 무수한 궤변과 말도 안 되는 비약과 결론들이 횡행하고, 데이터를 다루는 사람들이라면 이런 일이 최대한 일어나지 않도록 밑바탕의 정의를 명확하게 잡아두고 그 위에 적합한 데이터로 논리를 쌓아야 하는 것이다.
문제를 명확히 정의하고, 논리적으로 주어진 조건을 명시하고 그 안에서 최대한의 해법을 끌어내는 게 분석가의 일이다. 
그런데 이런 일을 해야 하는 사람들에게, ‘같이 일하는 사람들의 말’을 사전 정의로 깔아두라고 하면 이걸 뭐라고 해야 할 지 모르겠다. 
물론 어느 정도의 공감대는 빠른 일처리에 도움이 된다는 것은 인정한다. 하지만 정제되지 않은 정의는 상황에 따라서 왜곡되기도 쉽고, 이미 객관화된 정의가 있는 경우 이와 내부의 정의가 충돌했을 때 후자를 더 우선시해야 한다는 것은 쉽게 받아들이기 힘들다. 
더불어 이렇게 만들어진 문제, 정의를 사용하던 사람이 과연 다른 데에서는, 특히 데이터 분석가를 하게 되었을 때 과연 그 일을 잘 할 수 있을까?
모르겠다. 이런 일을 하는 사람이 하고 싶어하는 일을. 
물론 단기간의 데이터 추출 업무는 그 회사의 비즈니스나 데이터를 이해하는 데에 도움이 된다고 생각한다. 
하지만 장기적으로 이런 업무만 하는 것은 그 사람의 업무를 대하는 자세나, 전반적인 분석 업무를 고려하는 경우에는 도움이 되지 않을 것이라고 생각한다. 일단 (대부분의 경우) 재미도 없을 것이고.

내가 이 바닥에서 n년 일하면서 ‘데이터 추출자’를 따로 두었을 경우 이 사람들이 어떻게 되는 지에 대한 폐해는 무수히 봐왔고, 그럼에도 불구하고 사람들의 욕심은 끝이 없고 매번 같은 실수를 반복하는 일도 잘 보고 있다. 
시간이 지나면 이런 일은 없어지겠거니 했는데, 전혀 없어지지 않고 이제는 아예 다른 직함까지 붙여가면서 돌아가는 것을 보면 이쯤 되면 별로 할 말도 없다. (비단 BA를 따로 정의하지 않더라도 이런 경우 매우 허다하고 솔직히 이런 거 이제 좀 지겹습니다)

나는 **‘자주 봐야 하는 데이터는 지표로 정의해서 구글 스프레드시트부터 태블로까지 다양한 도구를 사용해서 대시보드화하고, 최대한 본인이 보고자 하는 것은 본인이 뽑을 것이며, 이보다 어려운 분석은 분석가에게~~(약은 약사에게 진료는 의사에게)~~ 결과까지 맡길 것’** 이라고 생각하고, 아직까지는 이 생각이 틀렸다고 생각한 적은 없다. 
물론 세상에는 다양한 상황이 존재하고, 급한 경우라든가 사람들이 모두 데이터를 볼 줄 모르는 상황인 경우 등이 있다. 
하지만 이럴 때 ‘데이터는 필요한 사람이 볼 수 있도록 최대한 노력하되 급할 때나 어려울 때는 할 줄 아는 사의 힘을 조금 빌리자’ 가 아닌 ‘우리는 우리의 일을 할테니 데이터를 뽑아주는 일을 맡길 사람을 찾자’라는 생각은 그 당사자에게도, 회사에게도 장기적으로 그다지 좋은 일은 아닐 것이라고 생각한다.불행히도, 아직도 많은 회사는 데이터의 오멜라스다.

 