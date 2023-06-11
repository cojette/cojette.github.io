---
layout: post
title: Data Lineage
---

요즘 데이터 처리 엔진 중 하나인 Apache Spark 가 주목을 받으면서 여기서 나온 기능 중 하나인 Lineage Graph 역시 주목을 받고 있다. 그러면서 data lineage에 대해서도 이야기가 들려온다. 하지만 data lineage는 DB 엔지니어들에게는 좀 켸켸묵은(?) 이야기일 수도 있다. DB 뿐만이 아니라 데이터 쪽을 업으로 가지고 있는 사람들이라면 기본적으로 '메타 데이터 관리'는 귀에 못이 박히도록 들었을 것이고, data lineage 역시 메타 데이터 관리 쪽 개념의 일환으로 한 때 IBM 등의 업체에서 열심히 밀었던 개념 중 하나다.  (그리고 물론 본인은 Spark는 실제로는 구경도 못하고 관련 문서 몇 개만 뒤적거려 본 것이 다지만) 기본적인 개념은 이 때와 그다지 달라진 것 같지는 않다.

사실 'Lineage'라는 거창한 이름을 붙일 것도 없고, 이는 일종의 데이터의 히스토리 관리다. 데이터의 출처, ETL, 변경 관련 procedure 및 현재 데이터로 파생된 다른 데이터까지, 해당 데이터의 life process를 통합적으로 관리하는 것이다. 이는 당연히 관리해야 하는 정보들로, 해당 정보들이 있어야 데이터의 오류 보정이나 정합성 파악, 감사 등이 제대로 이루어질 수 있다. 하지만 일반적으로 현재의 data snapshot만 관리하는 것만으로도 버겁기 때문에, 이런 metadata를 일목요연한 process 형태로 관리하는 것은 늘 버거운 일이다. 그래서 많은 솔루션 업체에서 data lineage라는 용어를 내세우고, 자동화 및 시각화 관련 기능을 내놓았다.

![Flow diagram highlighting Extension Mapping stored procedures and its description.](http://www.ibm.com/developerworks/data/library/techarticle/dm-1001datalineageinfosphereworkbench/fixed-lineage-joblineage.jpg)

IBM Data Lineage Report (@IBM DevelopersWork 2010. 09)

하지만 데이터를 모으고 써먹는 것에는 관심을 두면서, 이를 기본적으로 관리하는 데에는 관심을 많이 두지 않아서, 이런 부분에는 그다지 사람들이 시선을 주지 않았다. 그러다가 요즘처럼 대용량 데이터를 다양한 엔진에서 다양한 방식으로 관리하고, 이를 다양한 시스템에서 다양한 용도로 사용하게 되고, 데이터 정합성의 중요성과 관련된 metadata 관리 문제가 더욱 크게 급부상하면서, lineage graph 같은 data lineage 관련 내용이 다시 주목을 받고 있는 것은 아닌가 생각한다.

데이터를 잘 활용하고, 유용한 인사이트를 얻고, 이를 통해 새로운 비즈니스 기회를 창출하는 것은 데이터 활용의 가장 이상적인 모습이지만, 자고로 모든 데이터 활용에서 명심해야 할 문장은 'Garbage in, Garbage out'이다. 그리고 이 문장의 기저에는 데이터의 원천과, 이 원천에서 지금의 snapshot까지 다다르는 과정에 어떤 일이 있었는지를 이해하고, 관리하는 것이 필요하다는 것이 깔려있다. 이를 자동으로 할 것인지, 완벽하게 수동으로 할 것인지는 각각의 문제이지만, 이에 대한 관리 없이, 데이터를 완전히 소유했다/이해했다고는 말할 수 없을 것이고, 자신이 사용하는 데이터에 대해 충분히 소유권을 주장할 수 있을 때, 이를 활용하고 분석해야 좋은 가치를 얻을 수 있지 않을까 생각한다.
