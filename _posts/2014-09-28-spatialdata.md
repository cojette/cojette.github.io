---
layout: post
title: R로 인터랙티브 공간 데이터 시각화하기
---

공간 데이터 관련 시각화
=============

우리 조상님들께서 일찌기 '백문이 불여일견'이라는 한 마디 명언으로 요약하셨듯이, 내용 전달에는 시각화만큼 효과적인 방법이 드물고, 따라서 데이터 분석 내용도 이를 사람들에게 효과적으로 전달하기 위해서는 데이터 시각화를 잘 하는 것이 중요하다. 그래서 데이터 분석이 흥하면서 데이터 시각화 역시 주목받고 있고, 이런 경향은 점점 더 증가하고 있다. 이에 따라 다양한 시각화 관련 언어 및 많은 Open API가 등장하고 있고, 데이터 분석용 오픈소스 언어인 R에도 많은 능력자 분들께서 이들을 활용하는 패키지를 다양하게 만들어 주고 계신다. 그래서 다른 프로그래밍 언어에 익숙하지 않고 R도 겨우 사용하는 ~~*나같은*  ~~사람들도 이들을 그럭저럭 활용할 수 있다.

이를 통해 다양한 데이터를 다양하게 시각화할 수 있는데, 이 중 점점 더 주목받는 분야가 공간 데이터 시각화다. 아무래도 용이하게 구할 수 있고 다양하게 활용되는 데이터는 로그 데이터일 수밖에 없고, 이 로그가 기존에는 What을 기반으로 Who/When을 중심으로 기록되었고 이를 분석했다면, 모바일기기가 사회에 깊이 안착하면서 여기에 Where/How가 추가되게 되었다. 그리고 이 Where은 5W1H에서 데이터 관점에서 '보여주기' 가장 좋은 요소일 수밖에 없다. 그래서 이에 관련해서도 역시 무수한 API와 자료들이 제공되고 있고, 역시나 R 패키지로도 다양하게 나와있다.

Interactive Map
===============

그런데 공간 데이터를 시각화 하다보면, 다른 데이터의 시각화 이상으로 인터랙션에 예민해지게 된다. 아무래도 지도 데이터인 만큼, 좁은 지역에 대해 나타내거나 하나의 차원에서 간단하게(heat map 등)으로 나타내는 경우에는 좀 덜 하지만, 한정된 화면에서 넓은 지역에 대한 다차원의 데이터를 보여주고자 하면 아무래도 이에 대해서 사용자의 요청을 받고 그에 대한 내용을 보여줄 수 있게 하도록(지도 확대/축소, 범위 선택 등) 만들 필요가 강해지는 것이다. 그래서 지도 위에 데이터를 쉽고 예쁘게 뿌려주고 이를 자유자재로 적당히 움직일 수 있게 하는 기능들이 필요해서 인터랙티브 맵 관련 API들을 열심히 찾았는데, 역시나 이에 대해서도 많은 능력자 분들이 도와주고 계셨다.

MapBox
======

지도 API 관련해서, 구글맵 API의 기업 유료화에 힘입어 요즘 흥하는 스타트업이 [MapBox](https://www.mapbox.com/)라는 곳이다. 이 곳에서는 [OpenStreetMap](http://www.openstreetmap.org/)을 기반으로 지도 서비스를 제공하고 있다. 포스퀘어나 에버노트 등 유명한 서비스업체에서 구글 API를 버리고 OpenStreetMap으로 갈아타면서 이를 효과적으로 활용하기 위해 MapBox와 제휴하고 있는 것으로 알려져 있다.

Leaflet
=======

[Leaflet](http://leafletjs.com/)은 OpenStreetMap 기반으로 인터랙티브 지도를 만들 수 있는 대표적인 자바스크립트 라이브러리로, '인터랙티브'에 초점이 잘 맞춰져 있어서 지도 위에 데이터를 뿌린 후에 이를 다양하게 돌려볼 수 있다는 점이 장점이다. 컨트롤하기 쉽고 매뉴얼도 잘 되어 있으며, 기능도 지속적으로 추가되고 있다. 기존부터 워낙에 훌륭하여 많이들 사용하고 있었으며([예](http://www.texastribune.org/library/data/us-senate-runoff-results-map/) )또한 이 라이브러리의 개발자가 MapBox에 들어가면서 이 라이브러리의 지속성이나 기능 추가도 꾸준히 이루어질 것으로 기대하고 있다.

Leaflet + R
===========

R의 훌륭한 구루님들께서, 이런 훌륭한 데이터 시각화 소스를 그냥 두고 넘어갈 리가 없는 관계로, Shiny같은 패키지를 사용해서 JavaScript를 허술하게나마 R에서 사용하게 했던 것과 비슷한 이치로 이 Leaflet 역시 R에서 사용하게 하였다. 이 역시도 여러 사람이 달려 들어주신 덕분에 몇 가지(일단 내가 아는 것만 두 가지)가 나와있는데, 이 중 각자 입맛에 맞는 것을 골라서 사용하면 될 것 같다.

rCharts
-------

사실 [rCharts](http://rcharts.io/) 패키지의 경우에는 기존에 js용으로 나온 다양한 라이브러리를 R에서 손쉽게 구현하고 공유하거나 Shiny와 연동할 수 있도록 해주는 어마무시하게 아름다운 패키지인지라, leaflet에만 한정해서 이야기하기에는 너무나도 아까운 보석같은 존재다(...요즘 제가 격하게 아끼는 R 패키지 중 하나임). 그래서 이에 대해서 이야기할 기회는 다음에 또 있으리라 믿어 의심치 않으며, 우선은 여기서 leaflet 역시도 구현할 수 있도록 해준다는 것이 포인트. github에 올라가 있는 패키지이므로, devtool패키지의 install을 사용해서 패키지를 다운로드 받을 수 있다.

다음은 미국의 비만 인구 데이터를 사용해 지역별(주별) heat map을 나타낸 것이다.

```
# read data and replace dots in names with underscores
obesity = read.csv(
  'http://www.stat.berkeley.edu/classes/s133/data/obesity.csv',
  stringsAsFactors = F
)
names(obesity) = gsub("\\.", "_", names(obesity))
# add column with two letter state names and
obesity = plyr::mutate(obesity,
  State = str_trim(State),
  state = state.abb[match(State, state.name)],
)
rCharts::choropleth(
  cut(Adult_Obesity_Rate, 5, labels = F) ~ state,
  data = obesity,
  pal = 'PuRd'
)

```

결과는 [여기](http://rcharts.io/viewer/?6735051#.VCbYS14TlcQ)서 확인해 보자.

leafletR
--------

이 패키지는 이름 그대로 leaflet라이브러리를 R에서 사용하는 용도에 특화된 라이브러리로, CRAN에서 바로 다운로드 받을 수 있다.(물론 [Github](https://github.com/chgrl/leafletR)에도 올라가 있다.) 공유나 Shiny등과의 연동 면에서는 아주 조금 떨어지지만, rCharts보다 아무래도 가볍고, 지도 위에 올릴 그래프 속성을 세세하게 정의하는 면이 보다 R-직관적이고, 간단한 데이터는 JSON으로 연동해서 페이지에 넣어버려도 되다보니 페이지 단위로 뿌린 후에 간단히 데모 등으로 보여주기에는 더 용이하여, 다른 차트들과 연동할 필요가 없고 간단히 빨리 보는 용도로는 이 쪽을 좀 더 선호한다(다만 아직 스타일 관련해서는 좀 아쉬운 점들이 있다).

다음은 R의 지진 데이터를 사용해서 이를 시각화한 내용이다.

```
 # load example data (Fiji Earthquakes)
data(quakes)
# store data in GeoJSON file (just a subset here)
q.dat <- toGeoJSON(data=quakes[1:99,], dest=tempdir(), name="quakes")
# make style based on quake magnitude
q.style <- styleGrad(prop="mag", breaks=seq(4, 6.5, by=0.5),
  style.val=rev(heat.colors(5)), leg="Richter Magnitude",
  fill.alpha=0.7, rad=8)
# create map
q.map <- leaflet(data=q.dat, dest=tempdir(), title="Fiji Earthquakes",
  base.map="mqsat", style=q.style, popup="mag")
# launch map
q.map

```

결과는 다음과 같다. (이는 스샷이니 실제로 실행해보기를 추천한다)![](https://raw.githubusercontent.com/chgrl/leafletR/master/man/figures/quakes.png)

정리
==

공간 데이터 분석 내용을 R에서 한 번에 시각적으로 잘 전달할 수 있는 패키지들이 다양하게 개발되고 있는데, 물론 가장 만만한(?) GoogleVis나 ggmap 패키지의 지도 기능을 사용해도 좋지만, 여기서 지도 기능의 경우 interaction 부분이 좀 떨어져서,dynamic variable 기능을 제공하는 다른 패키지들을 연결하는 식으로 꼼수를 사용해야 했다. 그런데 목마른 자가 우물을 파고 필요한 자가 검색을 한다고, 찾아보니 이에 대해서 기존부터 많은 분들이 기여를 하고 계셨고, 그 중에서는 leaflet같이 훌륭한 라이브러리도 있고, 이를 R사용자가 쉽게 활용할 수 있도록 하는 패키지도 있었다. 이를 사용해서 나도 최근 한가지 일도 간단하고 재밌게 하기도 했고, 앞으로도 다양하게 사용할 수 있을 것이라고 기대하고 있다.
