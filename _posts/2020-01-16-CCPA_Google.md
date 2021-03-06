---
layout: post
title: CCPA에 대응하는 구글 데이터 서비스 사용자의 자세
---

![](https://media.itpro.co.uk/image/upload/t_content-image-desktop@2/v1577669654/CCPA.jpg?width=800)

국내 회사에 있을 때는 개인정보 보호법을 열심히 읽었고, ISMS나 관련 데이터 보안 규정에 대해서 이해했어야 하는데, 미국 회사에 오게 되니 새로운 것이 등장했다. 바로 CCPA(Califonia Consumer Privacy Act). (미국 회사 뿐만이 아니라 미국에서 수입을 얻는 회사들도 신경써야 한다.)  미국의 일은 늘 예측 불가라 어떻게 될 지 알 수 없지만 해가 바뀌었고 준비는 해두어야 하여 열심히 문서들을 이것저것 열심히 뒤적여 보았다.

[CCPA](http://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&division=3.&title=1.81.5.&part=4.&chapter=&article=) 자체에 대한 내용이야 링크도 해두었고 이에 대한 설명도 여기저기 한글과 영어로 정리된 문서가 인터넷에 잔뜩 있으니 찾아서 읽어볼 수 있다. 이 중에서 가장 (나에게) 중요한 부분은 소비자가 CCPA에 명시되어 있는 사후 권리를 행사했을 때다. CCPA의 경우 선택적 적용 방식이라 사용자가 요청 시에 처리를 하게 되므로, 사용자가 요청했을 때에 처리할 포맷과 프로세스를 만들어두는 것이 필요할 것이다. 특히 신경쓰인 부분은 (많은 서비스가 마찬가지로 사용하고 있을) 구글의 서비스(광고 등)와 구글의 데이터(GA export to Bigquery)에서의 사용자의 개인 정보와 개인 식별 정보 사용 정도, CCPA 요청 시 처리 방안이었다.
다행스럽게도 캘리포니아여서인가,많은 고객을 둔 IT회사(구글이나 아마존 등)에서는 CCPA 가이드라인을 매우 잘 만들어 두었고, 자사 제품에서 어떻게 처리해야 하는 지에 대한 매뉴얼도 잔뜩 있다(찾기 번거로울 뿐이다). 

CCPA관련 대응은 사실 다른 데이터 관련 법안이 그렇듯 약관을 제대로 만드는 것이 일순위고, 이 부분만 해결되어도 반은 해결되는 것과 같다. 또한 데이터 관련해서도 대부분의 PII(개인 식별 정보, Personal Identification Information) 관련 내부 데이터는 내부에서 어케든(이라고는 하지만 프로세스를 정비해 두어야 한다) 처리할 수 있다(지우라면 그냥 지우면 되고...비식별화 처리하라면 그냥 비식별화 하면 된다...). 하지만 외부 서비스는 100% 내 마음대로 할 수 없으며, 웹브라우저 쿠키 등 수동으로 넣는 정보가 아닌 경우에도 개인 식별 정보로 잡히기 때문에 이에 대해서 인지하고 있으면 지피지기 백전불태. 그리고 역시 그 외부 서비스 중 많은 스타트업들이 사용하는 것은 역시 구글 아니겠는가.

## Google Service의 PII

물론 구글 대부분의 서비스의 PII는 구글 계정이다(...). 하지만 많은 서비스에서 사용하는 B2B 서비스로 고객들과 관련된 거라면 역시 Google Analytics와 Google Ad일 것이다. 이 경우에 식별자로 사용되는 것은 역시 구글 계정과 GA 쿠키일 것이다. 특히 로그인하지 않고 사용하는 서비스의 경우 개인 정보 삭제나 이후 수집 금지와 관련한 요청이 들어온다면 GA의 클라이언트 ID를 사용자에게서 받아야 한다. 그러려면 사용자에게 본인의 클라이언트 ID를 요청해야 한다. 각자의 클라이언트 ID는 브라우저 별로 쿠키 데이터 중 _ga 쿠키의 Contents 내역의 string에 나와있다.(클라이언트 ID의 경우 브라우저에서 쿠키를 삭제한 후 새로 만들어진다든가, 쿠키 기간이 만료되어 재생성되는 경우에는 추적해서 관리할 의무는 없는 것으로 알고 있다.)

## Google Ads

Google Ad Manager와 Ad Exchange에서는 다른 구글 서비스와 마찬가지로 CCPA에 대응하고 있다. 광고 퍼블리셔를 위해 약관을 제공하고 있고, 사용자별 광고 제공 방식을 옵션이나 스크립트 처리를 끌 수 있으며, '제한된 데이터 처리' 방식을 제공하여 개인의 기록을 사용하지 않고도 광고를 제공할 수 있다(이 경우에는 개인화된 광고를 제공하지 않는다). 제한된 데이터 처리는 옵션으로 전 사용자에게 적용할 수도 있고, Google Ad에 사용자 리스트를 만들어서 조정할 수도 있다. 상세한 내용은 [매뉴얼](https://support.google.com/google-ads/answer/9614122)을 참고하면 된다.

## Google Analytics

Google Analytics(이하 GA)의 경우에는 주로 클라이언트 ID를 사용한다. 집계 데이터(방문자 수 등)의 경우 삭제하거나 조정할 의무가 없으나, 해당 클라이언트 ID의 데이터가 개별로 GA report에 나타나면 위법이다. 그래서 확인 후 해당 클라이언트 ID 데이터가 있으면 삭제 작업을 해야 한다. 이는 GA의 [User Explorer report](https://support.google.com/analytics/answer/6339208)에서 확인 후 삭제 작업을 진행할 수 있다. 해당 작업이 여러 번 반복될 것으로 보이는 경우 GA [User Deletion API](https://developers.google.com/analytics/devguides/config/userdeletion/v3)를 사용하는 것도 방법이다.

GA 데이터를 Bigquery로 Export해서 사용하는 경우는, 역시 해당 Client ID를 찾아서 해당 데이터를 삭제하거나 비식별화 처리를 해주어야 한다. GA report에서 처리를 했다고 해도 이미 Export한 데이터에 대해서는 반영이 안 되므로 따로 처리를 해주어야 한다.
GA 데이터의 경우 사용 로그이므로 기본적으로는 지우는 것이 원칙이나, 관련 로그를 비즈니스에 필수적으로 사용해야 하는 경우 타 데이터와 마찬가지로 역추적 불가능한 방식의 비식별화 처리 후 내부에서만 안전하게 사용하는 것이 가능하다. 

## 정리

어디든 개인정보 보호법 비스무리한 무언가는 있고, 이런 것은 점점 더 강화될 것이다(물론 최근 데이터 3법 이런 거 보면 아닌 것도 같더라). 가는 방향이 크게 다르지는 않아서, 여러 나라의 변화 흐름과 한 종류라도 직접 경험해보면 그 이후에 다른 비슷한 것을 접해도 도움이 되는 것 같다. 그리고 사실 이런 것 관련은 약관을 제대로 잡는 것이 최고 중요하다. 약관 잡을 때 관심을 가지고 매의 눈으로 지켜보도록 하자. 그리고 우리 서비스에서 만들어지는 데이터가 어떻게 관리되고 있고 그 데이터가 닿는 범위가 어디까지인지, 우리를 거쳐서 다른 데로 가는 데이터가 어떻게 돌고 있는 지 그 흐름을 명확하게 알아두고 대비를 하면 좋을 것이다.

모든 서비스의 사용자에게는 서비스를 사용할 권리 만큼 그 서비스에서 잊혀질 권리도 가지고 있다는 것을 기억해두면 이런 법이 여기저기서 튀어나올 때 도움이 된다. 
