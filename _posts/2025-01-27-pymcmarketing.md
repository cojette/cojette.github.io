---
layout: post
title: PyMC와 마케팅 믹스 모델
date: 2025-01-27 21:38:00 +0900
categories: [Data, Concepts]
tags: [데이터, MMM, 마케팅 믹스 모델, 마케팅, 어트리뷰션, ROI, PyMC, PyMC-Marketing, CausalPy]
---

마케팅 믹스 모델링(Marketing Mix Modeling, 이하 MMM)은 여러 광고 채널과 프로모션 활동의 기여도를 정량적으로 평가할 수 있는 접근방식이다 (자세한 내용은 [작년에 썼던 글](https://cojette.github.io/posts/mmm1/)을 참고하자). MMM을 구축할 때 베이지안 방식을 적용하면 확률 모델을 현실에 적용할 때 필연적으로 발생하는 불확실성을 계층적 구조로 분석에 자연스럽게 녹일 수 있어 구현이나 예측, 해석에 있어서 장점이 많아, 이를 적용한 다양한 MMM 모델들이 나오고 있다(역시 또다른 [작년의 글](https://cojette.github.io/posts/mmm2/) 참고).

하지만 이전에는 일단 유명한 MMM 중심의 라이브러리에 대해서 살펴보았다. 하지만 이쯤되면 자연스럽게(?) 떠오르는 궁금함이 있다. 베이지안 계산용 라이브러리인 [PyMC](https://www.pymc.io/welcome.html)를 사용한 MMM은 없을까?

그리고 늘 그렇듯이, '이런 게 아직 없을까?' 하고 생각하는 것의 90% 이상은 대개 있기 마련이다. 있다는 것은 작년에 알았지만 이제야 좀 정신차리고 며칠 살펴보니 정신이 하나도 없다.

PyMC의 주요 개발자들이 만든 베이지안 컨설팅 서비스인 [PyMC Labs](https://www.pymc-labs.com/)라는 조직이 있다(여기에 관한 자세한 것은 잘 모른다. 아마도 베이지안이 참 현실에서 쓰기 좋은 건데...이게 참 좋은데 어떻게 사람들에게 알려서 쓰게 할 방법이 없네... 같은 고민을 하다가 만들어진 게 아닌가 추측한다. 물론 여러가지 상업적인 이유도 있겠지만.). 
여기에서 만든 것이 거칠게 말하자면 인과 추론 라이브러리로 유명한 CausalImpact같은 [CausalPy](https://github.com/pymc-labs/CausalPy)라는 라이브러리가 있다. (이에 대해서는 좀 더 자세히 살펴볼 예정이다. 글로 쓸 지는... 그 때 봐서.)

또한 다양한 마케팅 관련 분석에 적용할 수 있는 [PyMC-Marketing ](https://github.com/pymc-labs/pymc-marketing)을 제공하고 있다. 관련하여 많은 모델과 방법론을 [홈페이지](https://www.pymc-marketing.io/en/stable/index.html)에 개시해 두었는데, 꽤 오래 전부터 쌓아둔 리소스가 많아서 볼 것들이 잔뜩 있다. 
시간에 따른 미디어 기여도, A/B 테스트에 적용하기 및 실험 조율, 인과 모델 비교 등 실제로 쓸만한 주제들에 활용할 수 있도록 만들어 두었고, 그에 대한 내용들도 정리된 것이 많다. 볼 게 많은 것은 좋은 일이다 (다만 유튜브 클립이 너무 많다...(동영상에 약한 자의 한숨) 그리고 사실 내용이...쉬운 편은 아니다 ~~이러니 사람들이 많이 안 쓰지~~).

각설하고, PyMC-Marketing은 이름에서 알 수 있듯, PyMC(베이지안 모델링 라이브러리)를 기반으로 마케팅 분야에 특화된 기능을 제공하는 라이브러리다. 특히, 광고 효과 모델링이나 시장 반응 분석 등 MMM의 내용들을 거의 구현할 수 있도록 해두어서, MMM을 커스텀으로 만들 경우 꽤 괜찮은 도구이지 않을까 생각된다.

## pymc-marketing

-   PyMC 기반의 마케팅 분석 도구: PyMC의 강력한 베이지안 추론 엔진과 자동 미분, 확률적 프로그래밍 능력을 그대로 물려받았습니다.
-   광고/마케팅 도메인에서 필요한 함수를 사전 내장: 광고 효과 모델에서 자주 쓰이는 adstock 변환, 누적 효과(diminishing returns) 등의 함수를 미리 정의해둔 덕분에, 사용자 입장에서 코드를 단순화할 수 있습니다.
-   개발 편의성: 데이터 전처리, 모델 정의, 사후 분석 등 일련의 프로세스를 간편하게 연결할 수 있는 API를 제공합니다.

즉, `pymc-marketing`은 "베이지안 MMM 코드를 처음부터 직접 짜기엔 부담스럽고, 그렇다고 R 패키지나 다른 언어로 넘어가기는 귀찮다" 할 때 유용한 Python 도구일 것이다.


## pymc-marketing의 장점

### 베이지안 MMM 개발 최적화

-   표준화된 광고 효과 함수: MMM에서 흔히 사용하는 adstock, hill(포화 곡선), 누적 반응 함수 등을 기본 제공하여, 광고 효과 모델을 빠르게 구성할 수 있음
-   계층적 구조 지원: 지역별, 채널별, 브랜드별로 다른 파라미터를 추정하면서도, 전체적으로는 일정한 패턴 공유(partial pooling 등) 모델링 용이
-   사전 지식(Prior) 활용: 비즈니스 상의 도메인 지식(예: "TV 광고 효과는 너무 크지 않을 것"과 같은 prior)을 자연스럽게 녹일 수 있는(물론 이를 데이터로 표현 가능해야 함) 방안을 제시함

### Python 생태계와 친화적

-   PyMC와 호환: PyMC 4.0 이후 JAX 백엔드, 개선된 변이형 추론(VI) 등을 그대로 반영할 수 있음
-   데이터 전처리/시각화: Pandas, NumPy, ArviZ 등 주요 라이브러리와 결합이 용이하므로, 파이썬의 데이터 분석 프로세스를 그대로 적용할 수 있음
-   유연한 커스터마이징: 필요하다면 `pymc-marketing`이 제공하는 블록들을 재조합하거나, 내부 PyMC 모델을 직접 수정해가며 원하는 형태로 확장이 가능합니다.

###  진입장벽 낮춤 + 확장성 높임

-   직관적인 함수 설계: "`build_adstock_transform()`" 같은 함수를 불러와 곧바로 적용 가능하므로, MMM 초심자라도 핵심 아이디어를 빠르게 실험할 수 있습니다.
-   에코시스템 확장: GitHub 이슈나 커뮤니티를 통해 다양한 예제가 공유됨




## 다른 MMM 도구 대비 강점

이전에 소개했던 Facebook의 Robyn(R 패키지), Google의 LightweightMMM (Python), stan 기반의 Prophet 변형(직접 스크립트 작성) 등과 비교했을 때의 pymc-marketing의 강점을 살펴보면 다음과 같다.

### Robyn(R) 대비
    -   Python 친화: Robyn의 [python 버전이 정말로 최근에 나왔다](https://developers.facebook.com/blog/post/2024/12/19/announcing-the-python-version-of-project-robyn/?locale=ko_KR)(그렇다 이 분야는 요즘 열심히 발전하고 있다). 하지만 오리지널 python과 R->python 포팅은...아무래도 차이가 있을 수 밖에 없다.
    -   베이지안 추론의 유연성: Robyn도 베이지안 기법을 일부 차용하지만, `pymc-marketing`은 PyMC의 확률적 프로그래밍 능력을 그대로 사용할 수 있어, 복잡한 구조(계층적-맞춤 분포 등) 적용에 더 용이할 것으로 보인다.

### LightweightMMM 대비
    -   고급 모델링 기능: LightweightMMM은 쉽고 빠른 MMM을 보여주지만, 복잡한 모델을 구현해야 하거나 커스터마이즈를 해야 하는 경우 소스 코드를 뜯어보아야 하는 경우가 종종 발생할 수 있따다. 반면 `pymc-marketing`은 필요할 경우 PyMC의 기능을 적재적소에 활용할 수 있을 것으로 보인다.
    -   변이형 추론(VI)-MCMC 혼합 사용: 경우에 따라 PyMC에서 제공하는 추론 기법을 적재적소에 넣을 수 있다.

### 직접 Python으로 구현 대비
    -   어차피 베이지안 쓰려면 PyMC를 써야 할 거고...그러면 굳이...이걸 안 쓰고 바닐라로 구현할 필요가...있을까요(...)



## 개념 예제

pymc-markeing에도 다양한 예제와 코드를 제공하는데, 일단 가장 쉬운 예를 만들어 보았다. 예를 들어, 시계열 광고비 지표(`ad_spend`)와 판매량(`sales`) 데이터가 있는 경우, 다음과 같은 과정을 진행하려고 한다.

1.  adstock 변환: TV 광고처럼 노출 이후 서서히 효과가 감소한다고 가정할 수 있음.
2.  동시 노출 영향: 여러 채널이 동시에 운영될 때, 서로 간에 상승/상쇄 효과가 있을 수 있음(계층적 구조).
3.  추론 및 예측: PyMC의 MCMC나 VI로 파라미터를 추정하고, 특정 채널의 비용 대비 매출 기여도를 예측.

`pymc-marketing`은 이런 과정을 간단한 함수 호출로 구현할 수 있다.

```
import pymc as pm
import pandas as pd
import numpy as np

#pymc-marketing import
from pymc_marketing.mmm.delayed_saturated_mmm import DelayedSaturatedMMM
from pymc_marketing.mmm.transformations import adstock_weibull, saturation_hill

# 예시 데이터프레임(df)에 광고비('tv', 'search')와 매출('sales')가 있다고 가정
tv = df["tv"].values
search = df["search"].values
sales = df["sales"].values

# DelayedSaturatedMMM 모델 사용
with DelayedSaturatedMMM(
    media=[tv, search],
    target=sales,
    adstock=adstock_weibull,      # 광고 효과가 서서히 감소하는 Weibull adstock 사용
    saturation=saturation_hill,   # 포화 곡선(Hill 함수) 사용
    # 기타 파라미터 설정 가능
) as mmmodel:
    trace = pm.sample(
        draws=1000,
        tune=1000,
        chains=2,
        cores=2,
        target_accept=0.9
    )

# 추론 결과 시각화
pm.plot_trace(trace)

```

이런 식으로 "광고 효과 변환 + 베이지안 추론 + 결과 시각화"가 묶여 있어서, 기존에 PyMC 코드로 일일이 설정하던 것보다 훨씬 쉽게 코드를 쓰면서도 이 내용을 구현할 수 있다.



## 결론


`pymc-marketing`은 Python을 사용해서 활용하고자 하는 목적에 맞게 마케팅 믹스 모델링을 빠르게 시작하고, 베이지안 추론의 강점을 최대한 활용할 수 있도록 돕는 유용한 라이브러리로 보인다. 의외로(?) 다양한 실제 활용 사례를 고민하고 진행해왔던 것으로 보이고, 게다가 PyMC의 능력을 적극적으로 활용할 수 있다는 것은 굉장한 강점이다. 물론 베이지안 계산 자체가 좀 느린 점이 없잖아 있었으나(...) JAX 등을 활용하면서 계산 능력에서 많은 발전이 있었던 것으로 알고 있다.

물론 이마저도 너무 블록화되어 있어서 더더더더 커스터마이징이 필요하다거나, 혹은 반대로 이 것도 어려운 경우도 많이 있겠으나, 이 정도면 꽤 쉬우면서도 본격적인 MMM용 도구가 아닐까 싶다. 진작에 좀 더 봤어야 하는데 이제라도 간간히 보면 재미있지 않을까.
