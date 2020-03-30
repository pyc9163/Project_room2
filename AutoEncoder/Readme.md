# AutoEncoder
![autoencoder_schema](https://user-images.githubusercontent.com/46980536/77914044-42efd780-72d0-11ea-8100-b68ba8f6ca6a.jpg)

### Autoencoder란 데이터 압축 알고리즘으으로 세가지 특징을 갖는다.
1. data specific
  Autoencoder는 훈련된 데이터와 비슷한 데이터로만 압축될 수 있다.
  예를 들어 얼굴 사진에 대해 학습된 autoencoder는 나무의 사진을 압축하는 데에는 좋은 성능을 내지 못한다. 그 이유는 autoencoder가 배우는 특징은 얼굴 특유의 것이기 때문이다.
2. 손실
  압축 해제된 결과물은 원본보다 좋지 않다.
3. 예제 데이터로부터 자동적으로 학습한다.
  특정 종류의 입력값에 대해 잘 작동하는 특별한 형태의 알고리즘을 쉽게 훈련시킬 수 있다. 
  
  
 ### Autoencoder는 데이터 압축에 좋을까?
 일반적으로는 그렇지 않다. 사진압축(JPEG)과 같은 알고리즘보다 나은 성능을 내는 autoencoder는 개발하는 것이 어렵다. autoencoder가 data specific하다는 점 때문에 실제 데이터 압축문제에 적용하기 실용적이지 않다. 따라서 autoencoder는 훈련된 것과 비슷한 데이터에서만 사용될 수 있고, 일반적인 데이터에 대해 사용하기 위해서는 많은 훈련데이터가 필요하다. 
 
 
 ### Autoencoder는 어디에 쓰일까?
  Autoencoder는 실제 응용에서는 거의 사용되지 않는다. 
  2012년, autoencoder를 응용할 수 있는 방법이 deep convolutional neural network에 대한 greedy layer-wise pretraining에서 발견되었다. 그러나 random weight initialization schemes가 처음부터 network를 훈련하기에 충분하다는 것을 알게 되면서 autoencoder에 사용이 줄어들었다.
  또한 batchnormalization은 훨씬 더 깊은 network를 허용하기 시작했고, 2015년 말부터는 residual learning을 사용하여 임의적으로 deep network를 훈련시킬 수 있었다. 
  
  지금의 autoencoder의 응용분야는 data denosing과 데이터 시각화를 위한 차원 축소이다. 적절한 dimensionality와 sparsity contraints를 사용하면 PCA나 다른 기법들 보다 더 흥미로운 data visualization 혹은 projection을 배울수 있다.
  
  2차원 시각화에 대해, t-SNE는 최고의 알고리즘이다. 하지만 이는 상대적으로 낮은 차원의 데이터를 요구한다. 따라서 높은 차원의 데이터에서 유사관계를 시각화하는 것은 먼저 autoencoder를 이용해 데이터를 낮은 차원으로 압축하는 것이다. 그리고 t-SNE를 사용하여 2차원 평면에 매핑한다. 
  
  
  ### Autoencoder의 중요성은?
  비지도 학습의 문제를 풀어낼 잠재적인 수단. 즉, self-supervised leanring. 입력데이터로부터 타겟을 만들어내는 학습 모델.
  문제는 픽셀 수준에서 사진의 재구성에 초점을 맞추는 것은 추상적인 특징을 배우는데 도움이 되지않는다는 증거가 있다.(타겟이 '개'나 '자동차' 처럼 인간이 발명해낸 추상적인 개념들인 경우) 
  vision에 적용되는 self-supervised learning에서, autoencoder 스타일의 입력 재구성에 대한 대안은 다음과 같다. 직소 퍼즐 해결, 세부 컨텍스트 매칭(고해상도이지만 그림의 작은 조각들을 그 조각들이 추출된 그림의 저해상도 버전으로의 매칭을 가능하게 함)같은 작업에 사용하는 것이다.
