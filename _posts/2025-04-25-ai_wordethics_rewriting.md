---
layout: post
title: LLM AI와 대화 윤리
date: 2025-04-25 22:00:00 +0900
categories: [Data, Concepts]
tags: [데이터, LLM, AI 윤리, 다시 쓰기, 편향, Grok, chatGPT, AI, 아웃스탠딩]
---

[![](https://cojette.wordpress.com/wp-content/uploads/2025/04/image.png?w=960)](https://cojette.wordpress.com/wp-content/uploads/2025/04/image.png)

(출처: [forbes](https://www.forbes.com/sites/lanceeliot/2023/04/19/solving-the-mystery-of-how-chatgpt-and-generative-ai-can-surprisingly-pick-up-foreign-languages-says-ai-ethics-and-ai-law/))

대형 언어모델(Large Language Model, LLM) AI는 마치 사람처럼 자연스러운 대화를 만들어내며 폭발적인 인기를 얻고 있다. 실제로 2022년 말 출시된 ChatGPT는 두 달 만에 월간 1억 명 이상이 사용할 정도로 가장 빠르게 성장한 서비스 중 하나가 되었다 . 하지만 이러한 뛰어난 언어 생성 능력의 이면에는 윤리적인 물음표들이 붙어 있다. 대화에서 파생되는 윤리란 타자(他者)에 대한 고려와 말하는 이의 책임을 강조하는 관점으로, LLM을 적극적으로 쓰는 이면에는 이런 부분에 대한 고려가 분명 필요하지만 제대로 이루어지지는 않고 있는 것처럼 보인다.

과연 AI의 대답에는 인간 대화에서 기대되는 타자성에 대한 존중과 의미에 대한 책임이 담겨 있는가? 혹은 그럴 필요가 있을까?

이를 고려하기 위해 LLM이 제공하는 응답의 구조적 한계와 편향성, 책임 회피 문제, 그리고 지나치게 긍정적이고 질문에만 몰입하는 경향 등을 살펴보고 LLM의 '말의 윤리'에 대해서 한 번 생각해 보고자 했다.

## 확률적 예측 기계가 만드는 무의미한 말

LLM의 언어 모델은 기본적으로 거대한 텍스트 데이터를 바탕으로 다음에 나올 단어를 확률적으로 예측하도록 되어 있다 . 다시 말해 문장의 맥락을 보고 가장 그럴듯한 단어 시퀀스를 출력하는 방식이다. 이러한 작동 원리 때문에 연구자들은 LLM을 가리켜 [확률적 앵무새(stochastic parrot)](https://en.wikipedia.org/wiki/Stochastic_parrot)라고 부르기도 한다 . 앵무새가 소리를 흉내낼 뿐 그 의미는 이해하지 못하는 것처럼, 언어모델 역시 통계적 패턴에 따라 그럴싸한 문장을 만들어낼 뿐 정작 그 말에 담긴 의미나 진실성에 대해서는 이해하지 못한다는 것이다 .

실제로 대부분의 언어모델도 언어의 형태만 학습할 뿐, 거기에 수반되는 현실적 의미는 고려하지 않는다 . 예를 들어 chatGPT에서 출력되는 문장은 매우 유창하고 그럴듯해 보이지만, 때때로 사실과 다르거나 말이 되지 않는 정보를 사실처럼 만들어내곤 한다. 이를 가리켜 흔히 환각(hallucination)이라고 하는데, ChatGPT가 이런 식으로 겉보기에는 그럴듯하지만 완전히 거짓인 단정적 응답을 내놓는 사례는 이미 널리 알려져 있다 . 이렇게 모델이 문장의 진위나 의미에 책임지지 않고도 그럴싸한 결과를 생성해내는 , 애초에 진실이나 의미보다는 확률상의 그럴듯함을 목표로 학습되었기 때문이다. 결국 워낙에 그럴 듯해서 쉬이 받아들여지지 않으나, 사실 LLM은 발화의 주체로서 '내가' 무슨 말을 하고 있는지 자각하지 못한 채 단어만 나열하는 형태에 가까우며, 이런 구조에서는 자기 발언의 의미에 책임을 지는 윤리까지 기대할 수는 없는 노릇이다.

## 편향된 학습 데이터가 낳은 치우친 시각

AI 언어모델은 인간이 만들어낸 방대한 텍스트로부터 학습하기 때문에, 그 데이터에 담긴 편향(bias) 또한 고스란히 배운다. 인터넷의 공개 텍스트는 문화권(특히 서구권)과 사용자 층이 편중되어 있고, 사회적 소수자의 목소리는 상대적으로 적게 포함되는 경향이 있다 . 또한 인터넷 언어에는 각종 편견과 차별적 표현이 다수 섞여 있기 마련인데, 모델은 이러한 유해한 패턴까지 그대로 흡수할 위험이 있다 . 그 결과 언어모델이 생성하는 문장에도 사회문화적 편향이 드러나, 소수자를 더욱 배제하거나 선입견을 강화하는 방향으로 작용할 수 있다는 지적이 나오고 있다 .

예를 들어 한 연구에서는 훈련 데이터에서 '흑인 여성(black woman)'이라는 표현이 부정적 맥락에서 더 자주 등장한 결과, 모델이 이러한 인종적 편견을 답변에 재생산할 수 있음이 확인되었다 . 마찬가지로 젠더 편견, 예를 들면 특정 직업에 남성이나 여성을 자동 연결하는 고정관념 등이 모델의 출력에 나타날 수 있다.

챗봇은 정치적으로 중립적인 듯 보이지만 실제로는 미묘한 편향을 보이기도 한다. 2023년 한 연구는 ChatGPT의 응답 성향을 분석한 결과 '[친환경 성향의 자유주의적(left-libertarian) 경향'이 있다고 발표](https://arxiv.org/abs/2301.01768)했다 . 실제 사례로, [출시 초기에 ChatGPT에게 대통령에 관한 시를 쓰게 하면 트럼프 전 대통령에 대해서는 거절하면서 바이든 대통령에 대해서는 시를 써주는 편향이 관찰](https://www.forbes.com/sites/ariannajohnson/2023/02/03/is-chatgpt-partisan-poems-about-trump-and-biden-raise-questions-about-the-ai-bots-bias-heres-what-experts-think/)되었고 이는 논란이 되었다 . 이후 업데이트로 수정되긴 했지만, 이러한 사례는 AI 모델이 정치적으로 민감한 주제에서 완벽히 중립적이지 않을 수 있음을 보여준다. 또한 정책 견해를 묻는 일련의 질문에서, 불법 이민자는 사회에 이익이 된다와 총기 규제를 강화해야 한다 등의 진술에 ChatGPT가 일관되게 '찬성' 입장을 보이는 등 전반적으로 진보적 응답을 내놓는 경향이 확인되었다 . 이는 보수적 입장의 진술에 대해서는 반대로 "반대" 답변을 한 것과 대조적이다. 또한 기업의 개입 역시 무시할 수 없다. xAI의 Grok의 경우, 대화에 필터링이 안 되는 것과는 관계없이 자유주의적 성향이 매우 높다고 판단되자 기업에서 특정 인물에 대한 대화에 직접[ 검열 로직을 개입](https://techcrunch.com/2025/02/23/grok-3-appears-to-have-briefly-censored-unflattering-mentions-of-trump-and-musk/)시키기도 했다.

언어 측면의 편향 역시 고려해야 할 문제다. 영어 기반으로 학습된 거대 언어모델은 서구 중심적 세계관을 담고 있을 가능성이 높다. 실제로 상당수의 LLM의 경우 '모델이 서구적 관점에 기울어 있으며 영어에서 가장 성능이 좋다'고 언급하고 있고 [이를 고려하고 있다](https://aclanthology.org/2023.c3nlp-1.7/). 그럼에도 불구하고 여전히 사용자들은 비서구권에 대한 이해 부족이나, 비영어권 사용자에 대한 상대적 불이익을 감안해야 한다. 예를 들어 같은 질문이라도 영어로 물을 때 가장 풍부한 답이 나오고 다른 언어로는 영어가 기계번역되어 어색한 답변이나,[ 해당 지역적 특성이 고려되지 않은 답변을 들을 가능성이 언제나 내포되어 있다.](https://theconversation.com/artificial-intelligence-needs-to-be-trained-on-culturally-diverse-datasets-to-avoid-bias-222811)

이처럼 훈련 데이터의 편향은 곧 AI 응답의 편향으로 이어진다. 문제는 이러한 편향이 사용자가 확연히 인지하는 경우도 있지만, 눈에 띄지 않게 은연중에 영향을 미칠 수도 있다는 점이다. AI의 자연스러운 언어 활용과 AI라는 '권위' 로 인해 사용자는 그 응답을 값비싼 진리로 오인하기 쉽고, 편향된 내용 역시 무비판적으로 받아들여질 위험이 있다. 실제 OpenAI도 '[ChatGPT가 사용자의 편견을 강화할 수 있다'](https://help.openai.com/en/articles/8313359-is-chatgpt-biased)며, 사용자가 강한 의견을 가진 정치 이슈에 대해 물을 때 모델이 이에 동조함으로써 그 믿음을 더욱 공고히 해버리는 것도 가능하다고 경고한다 . 그러므로 AI를 사용할 때는 이러한 편향성을 항상 경계하고, 중요 사안에서는 출처를 교차 확인하는 비판적 태도가 필요하다 .

## 발화 주체 부재와 책임 회피

대화에서 말을 한다는 행위는 보통 그 말에 대한 책임이 따라오기 마련이다. 우리가 누군가의 발언을 인용하거나 비판할 때 "누가 그렇게 말했다"를 중요하게 여기는 것처럼, 말에는 그것을 한 주체가 있고 그에 따른 책임이 존재한다. 그러나 생성형 AI의 응답에서는 이 발화 주체가 모호해진다. 겉보기에는 AI 챗봇이 "나"를 주어로 말을 하고 있지만, 사실 그 "나"는 인간처럼 자율적 의지를 가진 것도 아니고 말을 알고 하는 것도 아니다. 결국 AI가 한 말에 문제가 있을 때, 그 책임을 누구에게 물어야 하는지 불분명한 상황이 벌어진다.

예를 들어 챗봇이 잘못된 정보를 사실인 양 전달하거나 편향된 표현으로 누군가를 비하했다고 하자. 이때 그 말을 한 AI 자신은 법적-도덕적 책임을 질 수 없는 비인격적 존재다. 개발한 기업이나 모델을 훈련시킨 사람이 일정 부분 책임질 수는 있겠지만, 일일이 생성되는 모든 문장을 사전에 통제할 수는 없다. 이렇듯 LLM은 근본적으로 비(非)주체적(non-agentive)인 존재이기 때문에, 궁극적으로는 그 도구를 만든 연구자나 사용하는 이용자의 윤리 의식이 중요하다. AI에게 윤리를 기대하기보다는 그것을 어떻게 활용하고 감독할지에 대한 인간의 책임에 초점을 맞출 필요가 있는 것이다.

그럼에도 일반 사용자 입장에서는, 나보다 유려하게 문장을 써내는 AI 챗봇을 보면서 마치 실제 사람이 말하는 것처럼 착각하기 쉽다. 인간은 상대방의 말이 유창하고 일관되면 거기에 화자의 의도와 권위를 부여하는 경향이 있고, AI 챗봇과의 대화 역시 유사한 효과를 불러일으킨다. 실제로[ 2022년에는 구글의 챗봇 LaMDA와 대화하던 엔지니어가 그 AI가 자아와 감정을 가진 생명이라고 믿어버린 일화](https://www.washingtonpost.com/technology/2022/06/11/google-ai-lamda-blake-lemoine/)도 있었다 . 이처럼 AI 발화에 대한 과신은 사용자로 하여금 AI를 책임 있는 지식 공급자로 여기게 만들 수 있다. 하지만 앞서 살펴봤듯이 AI 모델은 말의 진위나 파급 효과를 스스로 판단하지 못하며 아무런 윤리적 책임 의식도 없다. 결국 AI의 말을 그대로 신뢰하기보다는, '이 대답은 결국 통계적 산물일 뿐'이라는 점을 인지하고 필요한 의심을 해보는 것은 사용자의 몫이다.

## 과도한 긍정과 피상적 중립성

많은 사용자들이 AI 챗봇과 대화하면서 느끼는 인상 중 하나는 '참 친절하고 긍정적이다'라는 점일 것이다. 가끔은 '보살의 현신이 AI가 아닐까' 하는 생각마저 든다. 실제 생성형 AI는 사용자에게 최대한 도움이 되고자 하는 방향으로 튜닝되어 있어서, 부정적이거나 충돌을 일으킬 만한 답변을 회피하고 긍정적이고 공손한 어조를 유지한다. 질문자의 요청에 웬만하면 '네, 물론이지요', '걱정마세요, 도와드리겠습니다.' 같은 식으로 긍정적이며 호의적으로 반응하고, 사용자의 감정에도 공감하는 듯한 문구를 (가끔은 과도할 정도로) 종종 삽입한다. 겉보기에는 매우 잘 훈련된 것 같은 친숙하고 인간적인 대화 태도이지만, 그 이면에는 몇 가지 문제점이 숨어 있다.

첫째, 과도한 긍정성은 때로 부실한 비판의식을 동반한다. 사용자가 어떤 잘못된 전제나 편견을 가진 질문을 하더라도 AI는 이를 정면으로 지적하기보다는 에둘러 답하거나 아예 해당 전제를 사실로 받아들이고 답변하기도 한다. 이는 앞서 설명한 바와 같이 모델 자체가 문장의 참/거짓을 이해하지 못한 채 학습된 패턴대로 따라가기 때문이기도 하고 , 또 한편으로는 사용자와의 불필요한 갈등을 피하도록 설계되었기 때문이기도 하다. 결과적으로 AI 챗봇은 사용자가 듣고 싶어하는 방향으로 답을 맞춰주는 경향이 있으며, 사용자가 답변에 반박하면 '말씀하신 대로 ~일 수도 있습니다' 식으로 지나치게 수용적인 태도를 보인다. 그러나 이런 무비판적 동조는 오히려 사용자로 하여금 자신의 편견이나 오해를 강화하도록 만들 수 있다는 점에서 윤리적으로 바람직하지 않다 . 대화 상대가 '답정너'를 위한 '예스맨'이라면 사용자의 기분은 좋겠지만 대화의 질은 떨어지고 잘못된 확신만 커질 위험이 있다.

둘째, AI의 중립적인 태도 역시 피상적인 경우가 많다. 물론 중립성 자체는 중요한 가치이지만, 모든 문제에 중립을 지키는 것이 능사는 아니다. 때로는 한쪽 입장이 명백히 사실에 부합하거나 도덕적으로 옳은 경우도 있기 때문이다. 하지만 챗봇은 누군가의 요청이 들어오면 일단 중립적인 서론을 깔고 가는 경향이 있다. 예컨대 '~는 좋은 대통령인가?'라는 질문에 ChatGPT는 먼저 '저는 중립을 지키며 객관적으로 답변하겠습니다'라고 운을 떼지만, 이어지는 내용에서는 묘하게 한쪽에 유리한 정보를 더 언급하는 불균형을 보이기도 한다. 이는 AI가 형식적으로만 중립을 표방할 뿐, 실제 내용에서는 훈련에 사용한 데이터나 내부 지침의 편향을 완전히 배제하지 못함을 보여준다. 또한 질문자가 기대하는 답을 만족시키려다 보니 두루뭉술한 양비론이나 교과서적인 일반론으로 답을 채우는 일도 있다. 이러한 답변은 큰 문제가 없어 보일 수 있으나, 정작 질문자가 궁금했던 핵심은 피해 가며 의미 있는 조언이나 통찰을 제공하지 못하는 한계가 있다.

결국 지나치게 긍정적이고 무난한 답변 일색이 되면, 사용자 입장에서는 AI를 사용해서 생각을 벼린다든가 새로운 시각을 얻기 어렵다. 말의 윤리 관점에서 보자면, 진정으로 상대방을 고려한 대화란 때로 상대의 잘못을 지적해주고 불편한 진실도 말해주는 것을 포함할 것이다. 그런데 현재의 AI는 사용자 비위를 거스르지 않는 데 치중한 나머지 필요한 비판이나 개선의 기회를 무시해버리는 셈이다. 이는 대화의 진정성을 해칠 뿐 아니라, AI에게 도덕적 나침반을 기대하기 어렵게 만든다.

## 질문이 만들어내는 답변

생성형 AI와 대화해보면, 놀랄 만큼 다양한 주제에 답을 하면서도 한 가지 분명한 한계를 느끼게 된다. 그것은 바로 질문의 '프레임(frame)'을 좀처럼 벗어나지 못한다는 점이다. 다시 말해 묻는 대로는 대답하지만, 묻지 않은 것은 스스로 짚고 나서지 않는다. 이러한 질문 중심의 몰입적 응답 구조는 AI가 사용자의 의도를 충실히 따르는 장점도 있지만, 동시에 대화의 창의성과 비판적 사고를 제한하는 요인이 된다.

예를 들어 어떤 질문 자체에 잘못된 전제나 함정이 숨어 있다고 하자. 인간 대화자라면 '그 질문에는 이러한 전제가 깔려 있는데, 그것이 옳은지 먼저 따져보자'라고 대응할 수 있다. 그러나 현 단계의 AI는 질문 내용을 액면 그대로 받아들이는 경향이 강하다. 앞서 언급했듯 AI 모델은 문장의 의미를 이해하고 사실 여부를 판단하는 능력이 제한적이어서, 잘못된 전제가 있어도 이를 인지하거나 반박하지 못한 채 답변을 이어가는 경우가 많다 . [한 연구](https://aclanthology.org/2023.acl-long.309/)에서도 '태양은 눈을 몇 개 가지고 있나요?' 같은 질문에 대해, 사람이라면 질문 자체를 이상하게 여기겠지만 언어모델은 주어진 단어에 맞춰 '태양에는 눈이 없다'라고만 답하는 식이라고 지적한다 . 즉, 질문 자체를 재구성하거나 의문을 제기하는 능력이 부족한 것이다.

또한 AI는 사용자가 제공한 정보 이상을 자발적으로 추가하지 않는다. 가령, 사용자가 어떤 상황을 설명하며 조언을 구할 때 그 상황의 배경이나 전후 관계를 따져 더 근본적인 문제를 지적하기보다는, 주어진 내용 범위 안에서만 해결책을 제시하는 경향이 있다. 이는 마치 말 잘 듣는 조수처럼 행동하는 것으로, 어디까지나 사용자가 던진 틀 안에서만 사고하도록 설계되었기 때문이다. 그 결과 대답의 범위도 질문의 범위를 넘지 못하고, 사용자가 미처 인식하지 못한 쟁점이나 구조적인 문제점은 드러나지 않은 채 넘어갈 수 있다.

이러한 프레임 갇힘 현상은 복잡한 사회 문제나 윤리적 딜레마를 논의할 때 특히 두드러진다. [질문자가 편향된 시각을 가지고 질문하면 AI는 그 프레임 안에서만 논리를 전개하여 답을 주기 때문](https://cojette.github.io/posts/infcon2024/)에, 초점 바깥에 있는 중요한 가치나 대안적인 시각은 배제될 수 있다. 윤리적으로 바람직한 담론이라면 서로의 프레임을 확장하고 숨은 전제를 드러내며 논의를 깊게 만들겠지만, AI와의 대화에서는 그런 메타인지적 소통이 어려운 것이다. 이로 인해, AI 답변을 그대로 받아들이는 사용자는 문제에 대한 편협한 시야를 벗어나기 힘들어질 수 있다.

## Epilogue -- 상대방과 대화의 책임을 고려하는 AI

지금까지 살펴본 것처럼, 생성형 AI의 놀라운 언어 능력에도 불구하고 말의 윤리 관점에서 보면 여러 문제점이 드러난다. 요약하자면 다음과 같다.

-   **의미에 대한 책임 부재** : AI는 확률적으로 가장 그럴듯한 응답을 생성할 뿐 그 내재적 의미를 이해하거나 진실성을 담보하지 못한다. 그 결과 보기엔 그럴싸해도 잘못된 정보가 포함될 수 있고, 이에 대한 책임 주체가 모호하다.
-   **학습 데이터 편향** : AI가 배운 데이터에 담긴 편향이 그대로 답변에 스며든다. 인종-성별 편견부터 정치적 편향, 문화적 편향까지 다양한 편향이 나타날 수 있으며, 이는 사용자가 인지하지 못한 경우에도 영향을 끼쳐 잘못된 인식을 강화할 위험이 있다.
-   **발화 책임의 공백** : AI는 말은 하지만 스스로 그 말에 책임지지 않는다. 사용자들은 종종 AI를 지식과 의견의 주체로 혼동하지만, 실제로는 일종의 도구일 뿐이다. 이 간극에서 발생하는 윤리적 책임의 공백은 아직까지 완전히 해결되지 않은 과제다.
-   **비판 없는 무조건적 동조** : 생성형 AI는 사용자를 만족시키기 위해 지나치게 긍정적이고 중립적인 태도를 취한다. 이로 인해 필요한 경우에도 반론이나 비판을 제시하지 않고, 모든 전제를 고스란히 수용해버리는 일이 생긴다. 이런 응답 태도는 대화를 피상적으로 만들고, 사용자에게 잘못된 확신을 줄 우려가 있다.
-   **질문 프레임의 한계** : AI의 답변은 철저히 질문 프레임 안에서만 이루어진다. 스스로 문제를 재해석하거나 숨은 전제를 밝히는 능력이 부족하기 때문에, 질문 자체의 오류나 한계를 넘어서지 못하는 답변이 반복될 수 있다.

이러한 문제들을 인식한다면, 우리가 앞으로 나아가야 할 방향도 어느 정도 명확해진다. 기술적 측면에서는 모델의 사실 검증 능력을 강화하거나, 훈련 데이터의 편향을 줄이는 정교한 필터링과 지속적인 모델 개선이 지속적으로 진행되고 있고, 계속되어야 할 것이다. 현재도 AI가 어떤 주장을 답변할 때 신뢰할 만한 출처를 함께 제시하도록 하거나, 질문의 논리적 타당성을 평가하는 모듈을 추가하는 연구들이 진행되고 있다. 또한 정책적으로는 AI 기업들이 모델의 한계와 위험성을 투명하게 공개하고, 사용자 교육을 통해 비판적 활용을 장려하는 것이 필요하다.

무엇보다도, 말의 윤리 관점에서 핵심은 타자에 대한 배려와 책임이다. 비록 AI 자체는 책임을 질 수 없지만, 그 AI를 제작하고 사용하는 인간은 이를 활용했을 때 타인에게 미칠 영향을 항상 염두에 두어야 한다. AI를 통해 정보를 얻거나 조언을 구할 때도, 그 답변이 가진 한계를 이해하고 최종 판단은 인간의 몫으로 남겨두는 지혜가 필요하다. 언어는 원래 서로 의미를 주고받으며 함께 진리를 찾아가는 공동 활동에 사용된다 . 그러한 본래의 소통 도구가 가지는 윤리가 오늘날의 AI 시대에도 훼손되지 않도록, 우리는 기술의 발전에 윤리의 나침반을 함께 세울 필요가 있다. 사용자는 AI의 말을 맹신하기보다는 성찰적으로 받아들이고, 개발자는 AI가 더 책임있는 말하기를 할 수 있도록 고민해야 한다. 이것이야말로 생성형 AI 시대에 요구되는 새로운 말의 윤리, 즉 기계와 인간이 모두 존중받는 책임 있는 소통 문화로 가는 길일 것이다.

## 참고 읽을거리 

-   <https://tech.bertelsmann.com/en/blog/articles/on-human-responsibility-in-dealing-with-large-language-models>
-   <https://www.brookings.edu/articles/the-politics-of-ai-chatgpt-and-political-bias/>

---------------------

이 글은 [연재글 다시 쓰기 프로젝트](https://cojette.github.io/posts/outst_rewriting_project/)의 일환으로 쓰게 된 글로 사실 [이 글](https://cojette.github.io/posts/xai/) 을 다시 쓰는 과정에서 만들어진 글입니다. 주제가 많이 벗어나서 산으로 가기는 했지만 자료 조사를 하다 보니 그렇게 됐습니다... 다시 쓰기란 게 그런 거죠(먼 산).
(이전 연재 글을 읽으신 분도 아마 알 수 없겠지만 최종 연재 편집 전의 모든 원본 글은 풍부한 참고자료와 풍부한 길이로 작성되었습니다. 그러다보니 글이나 문체도 바뀐 거 아닌가 싶겠지만 연재 원본과는 거의 유사한 문체와 스타일입니다.)


-----
장기적인 비전을 가지고 즐겁게 일할 수 있는 곳을 찾고 있습니다.
관련하여 이야기를 해보고 싶으신 분, 혹은 그 외에도 다양한 이야기를 나누고자 하시는 분은 저에게 편하게 메일이나 댓글 등으로 연락을 주시면 좋겠습니다. 
