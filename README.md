# LeNet-5과 Regularization을 추가한 LeNet-5(LeNet_Advance), Custom한 MLP(CustomMLP)를 구현하고, MNIST를 이용하여 각 모델들의 성능 평가 후 비교하는 프로젝트 진행


## 사전 작업 데이터셋 준비
데이터셋은 아래 url를 통해 다운 받을 수 있다.
- https://www.kaggle.com/datasets/hojjatk/mnist-dataset

## main.py 실행 시 다음 과정을 거쳐 학습이 진행된다.
1) 데이터 전처리
- code 폴더 내 dataset.py를 통해 이미지 전처리 진행
- T.ToTensor()를 이용하여 0과 1 사이 값으로 scaling 후 T.Normalize를 이용하여 정규화
- 파일명을 split하여 레이블 추출

2) 모델 선언
- code 폴더 내 model.py를 통해 LeNet-5와 CustomMLP가 선언됨
- LeNet-5와 CustomMLP 구조는 아래 그림과 같음
- LeNet_Advance의 경우 각 layer 사이에 batch normalization layer 추가
<p align="center">
  <img src="./LeNet%20구조.png" width="45%">
  <img src="./customMLP%20구조.png" width="45%">
</p>

3) 모델 학습
- LeNet-5, LeNet_Advance, CustomMLP 세 가지 모델 모두 다음과 같은 hyperparameter를 이용하여 학습진행
- LeNet_Advance의 경우 regularization을 추가하기 위해 weight_decay를 1e-3으로 설정  
-- optimizer : SGD  
-- learning rate : 0.01  
-- cost function : CrossEntropyLoss  
-- epoch : 30  
-- batch size : 512  

4) 성능 비교
- 아래 그래프와 같이 epoch에 따른 성능이 측정되었다.
- LeNet에 Regularization을 추가한 LeNet_Advance의 성능이 가장 높은 것을 확인할 수 있다.
<img src="./loss and accuracy plot.png">
