---
layout: post
title: BigQuery ML을 활용한 다변량 시계열 예측(feat. GDG DevFest 2022)
date: 2023-07-13 16:10:00 +0900
categories: [Data, Skill]
tags: [데이터, BigQuery, BQML, Machine Learning, Time-series, ARIMA, ARIMA_PLUS_XREG, ARIMA_PLUS]
---


## More predictable time-series model with BQML

작년 겨울에 우즈베키스탄의 수도 타슈켄트에서 열린 [GDG DevFest Tashkent 2022](https://gdg.community.dev/events/details/google-gdg-tashkent-presents-devfest-tashkent-22/)에서 'More predictable time-series model with BQML'이란 주제로 발표를 했었다.

원래는 발표에 사용한 자료와 코드도 좀 정리해서 같이 공유하려고 했지만, 나의 게으름으로 인해 시간이 흘렀고, 그 사이에 BQML에 내용이 일부 겹치는 새로운 기능이 나와서, 괜히 인터넷에 유효기간이 지난 정보를 추가하는 쓸데없는 일은 하지 않기로 했다.

대신에 새로운 기능과, 여전히 유효한 일부 내용을 간단히 언급해 보려고 한다.

[![아쉬운 마음에 공유해보는 슬라이드 표지](https://cojette.files.wordpress.com/2023/07/image.png?w=1024)](https://cojette.files.wordpress.com/2023/07/image.png)

## 시계열 모델과 BQML

시계열 데이터는 수많은 기업에서 다양한 용도로 활용하고 있으며, 흔히 '고급 분석'이라고 말하는 '예측 분석'이란 결국 시간 상의 '미래'를 다루는 것이다보니, 여기에서 중요하게 다뤄지는 데이터이기도 하다. 시계열 예측 분석은 단기, 중기, 장기로 다양하게 활용되어 왔고, 부정확성과 위험성 등이 많지만 그만큼 계속 꾸준히 개선되어 오기도 했다.

워낙에 '예측'이란 게 유용하면서도 있어보이다 보니, 시계열 데이터가 있다면 시계열 예측 모델을 적용해보고 싶은 경우도 많을 것이다. 이 경우 많은 시계열 데이터에 예측 모델을 적용해 보는 시도를 할 수 있겠지만 기본적으로 시계열 예측 모델은 대개 연산량이 많은 편이고, 데이터가 많이 쌓여있다면 그 연산량은 더 할 것이다. 그래서 이를 처리하고, 데이터 저장소와 분석 환경으로 옮기고 처리하는 것도 번거롭고, 분석 환경을 구축하는 것만으로도 힘들다.

데이터 관리에 BigQuery를 쓰고 있는 기업의 경우, BQML(BigQuery ML)을 사용해서 간단하고 쉽고 빠르게 데이터에 기계학습 알고리즘을 적용해 볼 수 있다(BQML에 대해서는 [예전에 쓴 글](https://cojette.github.io/posts/bqml/)을 참고하자). 그리고 BigQuery를 쓰는 경우는 상당수는 많은 데이터를 처리하기 위해서고, 많은 데이터가 있는 경우의 상당수는 시계열 데이터인 경우가 많다. 그리고 BQML에서는 시계열 모델도 지원한다.

현재 BQML에서 지원하는 시계열 모델의 기반은 ARIMA(AutoRegressive Integrated Moving Average) 모델이다. ARIMA 모델은 기존의 시계열 데이터만을 사용해서 예측하며, 단기 예측 성능도 높은 편으로 알려져 있으며, AR과 MA가 결합한 모델인 만큼 많은 범위의 시계열 모델을 아우를 수 있어 많이 활용되는 모델이다.

하지만 이 모델의 경우 전반적으로 계산량이 많고, 정상성을 가진 시계열 데이터만을 활용하다보니 추세나 계절성이 있는 경우에는 활용이 어려운 문제가 있다. 그래서 BQML의 `ARIMA_PLUS`에서는 몇 가지 추가 기능을 옵션으로 포함하고 있다. 시계열 분해, 계절성 관련 요인, 급상승 및 급 강하 지점 처리, 계수 변경 등등의 요인을 모델에 추가로 반영하고 처리하거나, 따로 살펴보면서 모델을 수동으로 조율할 수 있다. 또한 개인적으로는 휴일 옵션을 자동으로 반영해서 주기성을 조율할 수 있는 것도 좋았다. 일일이 날짜를 넣지 않아도 되는 것은 역시 플랫폼을 사용하는 것의 장점 아니겠나 싶고.

![](https://lh3.googleusercontent.com/km1BjJliIm1IaD8EW1lpIEtKXQT5uM1NpSCVVQfFY546pVxeJZV0FldZIZiq6XlMj-MNsN_oGdSMBvXVyI5zxLqTgaSNfPhvy1KyAWwB9_dt8JI3SS-wo4lRY3Z2XgefCidJ5Rwh7NCn6ftLTNcU2iWvzA=s2048)

자세한 내용은[ 여기](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-time-series)를 참고하자.

하지만 실제로 이를 활용할 때는, 이렇게 간단하게(?) 시계열 예측이 가능하지 않은 경우가 대다수다. 물론 여러 주기를 파악하고 여러 시계열에 개입 가능한 부분을 추가할 수 있도록 했지만, 현실의 시계열에는 많은 경우 이 외의 외부 요인들이 등장하기 마련이고, 독립적으로 일어나는 사건은 거의 없다고 해도 과언이 아닐 것이다. 시계열 모델의 정상성이란 것은 실제는 지키기 너무 어려운 것.

그래서 발표에서는 이런 시계열 분해를 한 후에 그 데이터만 정제해서 파이썬으로 가지고 온 다음에 다른 변수와 엮어서 다변량 시계열 함수를 따로 만들어 본다든가, 인과성을 추정해서 예측 모델에 반영한다든가, 이벤트의 변화에 따라 효과가 달라지는 정도를 추정하는 방안도 같이 살펴보았지만.

## New Feature: ARIMA_PLUS_XREG


...몇 달 사이에 외부 변수와 다변량 시계열 함수를 만드는 모델이 아예 피처로 나왔다.

자세한 내용은 [여기](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-multivariate-time-series) 에 다 나와있으니까 자세한 내용까지는 굳이 설명할 필요는 없겠다. (2023년 7월 현재 미리보기 버전이지만 올해 안에는 정식으로 나오지 않을까.)

그래서 [튜토리얼](https://cloud.google.com/bigquery/docs/arima-plus-xreg-single-time-series-forecasting-tutorial?hl=ko)에 나온 내용으로 기존의 단변량 시계열 모델과의 성능 차이를 확인해 보았다.

진행 내용은 튜토리얼과 동일하기 때문에, 굳이 중복해서 사용하지는 않을 것이고, 만든 두 개의 모델만 써보면 다음과 같다. 우선 기존의 `ARIMA_PLUS`를 만든 후, 동일한 데이터에 당시의 온도와 풍속을 추가한 `XREG` 모델을 만들었다.

```
# ARIMA_PLUS
CREATE OR REPLACE MODEL test_dt_us.seattle_pm25_plus_model
 OPTIONS (
  MODEL_TYPE = 'ARIMA_PLUS',
  time_series_timestamp_col = 'date',
  time_series_data_col = 'pm25') AS
SELECT date, pm25
FROM test_dt_us.seattle_air_quality_daily
WHERE date BETWEEN DATE('2012-01-01') AND DATE('2020-12-31')
```

```
#ARIMA_PLUS_XREG
CREATE OR REPLACE  MODEL test_dt_us.seattle_pm25_xreg_model
  OPTIONS (
    MODEL_TYPE = 'ARIMA_PLUS_XREG',
    time_series_timestamp_col = 'date',
    time_series_data_col = 'pm25') AS
SELECT  date, pm25, temperature, wind_speed
FROM test_dt_us.seattle_air_quality_daily
WHERE  date BETWEEN DATE('2012-01-01') AND DATE('2020-12-31')
```

그리고 이렇게 포함된 데이터를 같이 사용하는 모델은 다음과 같은 형태로 구성된다.

[![](https://cojette.files.wordpress.com/2023/07/image-1.png?w=1024)](https://cojette.files.wordpress.com/2023/07/image-1.png)

두 모델을 간단히 `ML.Evaluate `를 사용해서 비교해 보았다.

```
SELECT  *  
FROM  ML.EVALUATE      
      (  MODEL test_dt_us.seattle_pm25_plus_model, 
      (  SELECT  date,  pm25   
         FROM  test_dt_us.seattle_air_quality_daily   
         WHERE  date > DATE('2020-12-31')  ))
```

```
SELECT  *  
FROM  ML.EVALUATE    
      (  MODEL test_dt_us.seattle_pm25_xreg_model,
      (  SELECT  date,  pm25,  temperature,  wind_speed   
         FROM  test_dt_us.seattle_air_quality_daily  
         WHERE  date > DATE('2020-12-31')  ),
      STRUCT(  TRUE AS perform_aggregation,  30 AS horizon))
```

결과는 다음과 같다.

ARIMA_PLUS

[![](https://cojette.files.wordpress.com/2023/07/image-2.png?w=1024)](https://cojette.files.wordpress.com/2023/07/image-2.png)

ARIMA_PLUS_XREG

[![](https://cojette.files.wordpress.com/2023/07/image-3.png?w=1024)](https://cojette.files.wordpress.com/2023/07/image-3.png)

XREG 쪽의 모델이 MAE, MSE, MAPE 등의 기본 성능 지표에서 살짝 앞선다는 것을 직접 확인해 볼 수 있다. (당연히도 이 것은 모든 경우에 다 해당하지 않고 데이터에 따라 다르니 필요한 경우에 취사선택해야 한다는 당연한 말은 굳이 덧붙일 필요가 없겠다.)

* * * * *

다변량 시계열 분석은 많은 경우에 굉장히 필요한 옵션인데 여러 가지 이유로 적용하기 힘든 경우가 많다. 그럴 때에 활용 가능한 좋은 옵션이 생긴 것 같으니, 알아두면 많은 경우에 활용 가능할 것이라고 기대하고 있다.

(English: [Link](https://medium.com/@cojette/multivariate-time-series-prediction-with-bqml-feat-devfest-2022-5eb584872055) )

