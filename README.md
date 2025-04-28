# LeNet-5과 Custom한 MLP을 구현하고, MNIST를 이용하여 각 모델들의 성능 평가 후 비교하는 프로젝트 진행


## 사전 작업 데이터셋 준비
데이터셋은 아래 url를 통해 다운 받을 수 있다.
- https://www.kaggle.com/datasets/hojjatk/mnist-dataset

## main.py 실행 시 다음 과정을 거쳐 학습이 진행된다.
1) 데이터 전처리
- code 폴더 내 dataset.py를 통해 이미지 전처리 진행
- T.ToTensor()를 이용하여 0과 1 사이 값으로 scaling 후 T.Normalize를 이용하여 정규화

2) 모델 선언
- code 폴더 내 model.py를 통해 LeNet-5와 CustomMLP가 선언됨
- LeNet-5와 CustomMLP 구조는 아래 그림과 같음
![LeNet 구조](./LeNet%구조.png)
