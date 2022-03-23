# Training Neural Networks  

## Activation Functions  
* 활성화 함수를 넣지 않고 layer들만 쌓아주면 의미가 없음.  
* 비선형을 가해주는 중요한 역할  
### Sigmoid
* 0~1로 값을 가짐.  
* 최근에는 최종 output에만 사용함.  
    * 단점  
    * 기울기를 없애 버림(vanishing gradient)  
    * zero-center : 0을 중심으로 있지 않음, 양수의 값만이 input 되는 문제. 기울기에서 전부 양수가 되거나 음수가 됨.  
    * exp의 연산은 계산이 많이 소요됨.  
### Tanh  
* 범위가 1에서 -1  
* zero-centered 문제 해결.  
* 기울기 소실 문제를 해결하지 못해서 활성화 함수로 부적격  
### ReLU  
* f(x) = max(0,x)  
* 기울기 소실 문제를 어느정도 해결  
* 음의 영역에서는 zero-centerd, 기울기 소실 문제가 있음.  
* 음의 영역에서는 dead ReLU  
    * ReLU를 활성화 함수로 하면 훈련 도중 network 일부가 freeze 됨.  
    * 10~20% 정도 dead relu에 빠진 것  
    * 문제이지만 학습은 잘됨.  
### Leaky ReLU  
* f(x) = max(0.01x,x)  
* dead relu의 단점을 보완한 함수  
* 음의 영역에서 기울기를 주어 vanishing gradient 문제를 해결함.  
### PReLU  
* 음의 영역의 기울기를 파라미터 알파로 만들어 좀더 융통성을 만듬  
### ELU  
* 0에서 미분 가능하게 smooth 시킴.  
* Leaky ReLU보다 노이즈에 대해 더 로버스트 함
* 음의 영역에서 기울기 소실 문제가 있음.  
* exp 연산으로 효율이 조금 떨어짐.  
### Maxout Neuron  
* 기울기가 사라지는 문제점은 없지만 연산량이 두배가 되는 단점이 있음.  

## Data Preprocessing  
* zero-centering  
* normalize  
    * 이미지는 다 같은 범위라 거의 안함.
* PCA  
* whitening  

## Weight Initialization  
* What happens when W=0 init is used?  
    * w가 전부 0이기 때문에 입력값에서 부터 모든 뉴련이 계속 똑같은 값을 내놓음.  
    * 활성화 함수가 작동하지 않으니, layer의 의미가 없어짐.  
* small random number  
    * 1보다 작은 w의 값들이 layer가 깊어질수록 곱해지니까 0으로 수렴.  
    * initialization이 w를 작게하면 collapse가 되고 너무 크면 saturate 됨. 그래서 어려움.  
* Xavier initialization  
    * 입력값들의 수가 적으면 큰 값의 w가 필요해서 더 적은 수로 나누어 스케일링해줌.  
    * 반대로 입력 값들의 수가 많으면 작은 값의 w가 필요해서 큰수로 나누어 스케일링함.  
* Batch Normalization  
    * 현재 batch에서의 평균과 분산을 이용해서 batch normalization을 취해 모든 층에서 정규분포를 따르게 하려 함.  
    * Conv 층과 FC 층 후에 batch norm을 넣어줌(활성화 함수 전)  
    * mini-batch 마다 mean, variance를 계산함.  
    * 구한 mean과 variance로 normalize를 함.  
    * scailing과 shifting factor를 가지고 있음.  
    * 기울기의 흐름에 좋은 영향을 주어 robust한 결과를 냄.  
    * test 셋에서 batch norm을 할때에는 train 셋에서 이용한 mean과 variance를 이용함.  

## Babysitting and Learning Process  
* network architecture를 선택  
* loss 함수를 지정하거나 regularization을 생각해봄.  
* 학습을 시킬때 Sanity Check로 먼저 진행.  
* 전체 데이터를 학습하고 loss확인하면서 learning rate를 조정.  

## Hyperparameter Optimization  
* cross-validation  
    * 넓은 범위에서 좁은 범위로 좁혀가며 하이퍼 파라미터를 세팅함.  
* Grid Search  
    * 일정한 간격으로 조합을 찾음.  
* Random Search  
    * 무작위로 살펴 나감.  
* Big gap : overfitting. increase regularization strength.  
* no gap : increase model capacity.  