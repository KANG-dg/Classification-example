# Classification-examples

## 개요: 3개의 Dataset을 사용하여 Classification task를 구현
## 목적: computer vision 분야의 기본적인 task인 이미지 calssifcation을 구현하고 해당 task의 동작 방법을 이헤


### 1. chest X-Ray classification
#### Chast X-Ray dataset을 통해 3개 class(covid-19, noraml, pneumonia)로 분류 모델은 pretrained된 VGG19 모델을 사용하였음
#### 이 때 모델의 마지막 layer에 adaptiveaveavgpooling, Relu, dropout을 사용하였음 일반적으로 마지막 classifier의 output 숫자를 class개수에 맞게 수정하는 방법보다 overfitting을 방지하는것에 효과가 있을 것으로 판단.

### 2. Mnist dataset classification
#### Benchmark dataset으로 주로 사용되는 Mnist dataset을 통해 이미지 classification 모델을 구현하였음
#### 이 때 torch에서 제공하는 모델이 아닌 CNN기반 모델을 구현해서 사용하였음 구현된 모델의 구조는 아래와 같음
'''
for i in range(3)
'''
