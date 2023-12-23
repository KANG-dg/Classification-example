# Classification-examples

## 개요: 3개의 Dataset을 사용하여 Classification task를 구현
## 목적: computer vision 분야의 기본적인 task인 이미지 calssifcation을 구현하고 해당 task의 동작 방법을 이헤


### 1. chest X-Ray classification
#### Chast X-Ray dataset을 통해 3개 class(covid-19, noraml, pneumonia)로 분류하는것이 목적 모델은 pretrained된 VGG19 모델을 사용하였음
#### 이 때 모델의 마지막 layer에 adaptiveaveavgpooling, Relu, dropout을 사용하였음 일반적으로 마지막 classifier의 output 숫자를 class개수에 맞게 수정하는 방법보다 overfitting을 방지하는것에 효과가 있을 것으로 판단.

### 2. Mnist dataset classification
#### Benchmark dataset으로 주로 사용되는 Mnist dataset을 통해 이미지 classification 모델을 구현하였음
#### 이 때 torch에서 제공하는 모델이 아닌 CNN기반 모델을 구현해서 사용하였음 구현된 모델의 구조는 아래와 같음
```python
class CNN(nn.Module):
  def __init__(self):
  super(CNN, self).__init__()
  self.conv1=nn.Conv2d(1,32,3,1)
  self.conv2=nn.Conv2d(32,64,3,1)
  self.dropout1=nn.Dropout2d(0.25)
  self.dropout2d==nn.Dropout2d(0.5)
  self.fc1=nn.Linear(9216, 128)
  self.fc2=nn.Linear(128, 10)
```
#### 해당 모델에서 hyperparameter는 lr=0.0001, batch_size=50, epoch=15 로 사용하여 학습하였을 때 Test에서 99.00의 accuracy를 보였다. 간단한 모델을 구현 했다고 생각했는데 예상외로 높은 성능을 보여주었다.

### 3. 작물 병충해 분류
#### 33개 class가 존재하는 작물 잎 병충해 데이터를 사용하였음 모델은 pretrained된 Resnet50 모델을 사용하였고 학습시 Augmentation으로 Horizontalflip, Verticalflip, randomcrop을 사용하여 실험 하였음 Augmentation이 모델의 성능에 긍정적인 영향을 줄 수 있음을 확인하였음
