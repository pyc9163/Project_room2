# Tensorflow Probability

### Regression and Probability
  회귀는 예측 문제에 적용 할 수 있는 머신러닝 기법중에 가장 기본적인 방법이다. 그러나, 회귀 분석에 기초한 많은 분석은 문제에서 요구하는 복잡성의 정도 때문에 예측의 불확실성에 대한 적절한 정량화를 생략한다.
  불확실성을 정량화하기 위해, 한가지 방법은 회귀모델의 입력 변수(x) 및 일부 매개변수(w)에 주어진 라벨(y)의 확률 분포로 쓰는것이다. P(y | x, w)
  이는 라벨의 확률을 최대화하거나 nagative log-likelihood loss를 최소화함으로써 이 모델을 데이터에 적삽시킬 수 있다.
  
  여기서 회귀 모델로 다양한 손실 함수를 사용 할 수 있다. 
  Mean squared error loss(연속형 라벨), 예를 들어 P(y | x, w) 는 표준 편차를 가진 정규분포임을 의미한다. 
  Cross-entropy loss(분류),  P(y | x, w)는 범주현 분포이다.
  
  TFP 섹션에서는 TensorFlow Probability(TFP)의 Probabilistic layers를 사용 할 것이다. 이를 이용해 불확실성을 어떻게 정량하는지 보여주고, 사용의 예시들을 보여줄 것이다.

![0_k-Fm4zKV1r1epmi5](https://user-images.githubusercontent.com/46980536/77918279-9cf39b80-72d6-11ea-8fb9-fbdc9908be71.gif)
