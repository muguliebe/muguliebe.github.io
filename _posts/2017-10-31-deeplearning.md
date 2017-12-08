---
layout: post
title: "Deep Learning"
date: 2017-10-30
categories: AI
tags:
- machine learning
- deep learning
---

## Introduce
- 머신러닝의 한 종류
- 기존 이미지 인식과 딥러닝의 차이
   - 특징량 추출: '색에 주목해서 살펴라'가 아니라, 색이던 모양이던 기계가 찾아 냄
- neural network
   - 신경망을 3개 이상 중첩 => Deep Neural Network
- Convolutional Neural Network: CNN
   - 입력층과 출력층 사이의 중간층에 합성곱층과 풀링층을 배치

<!-- more -->

### question
- [ ] normalization 의 디테일한 이유?
- [ ] softmax 회귀론?
- [ ] cross entropy ?
- [ ] Steepest descent method ( 경사하강법 ) ?
- [ ] 합성곱층, 풀링층, 전결합층의 차이 ?

## perceptron
![alt](http://muguliebe.github.io/assets/images/blog/perceptron.png)

- 1957년에 프랑크 로젠블라트(Frank Rosenblatt) 가 제안
- 신경망(딥러닝)의 기원이 되는 알고리즘
- 다수의 신호를 입력으로 받아 하나의 신호를 출력

## neuron
![alt](http://muguliebe.github.io/assets/images/blog/perceptron/fig2-1.png)
- 뉴런 or 노드
- 입력 신호가 뉴런에 보내질 때 각 고유한 가중치가 곱해진다
- 뉴런에서 보내온 신호의 총합이 정해진 한계를 넘어설 때만 1을 출력
- 그 한계를 임계값(θ) 이라 한다

### AND 회로
- before bias
```python
def AND(x1, x2):
    w1, w2, theta = 0.5, 0.5, 0.7
    tmp = x1*w1 + x2*w2
    if tmp <= theta:
        return 0
    elif tmp > theta:
        return 1
```

- after bias
![alt](http://muguliebe.github.io/assets/images/blog/perceptron/e2.2.png)
```python
def AND(x1, x2):
    x = np.array([x1, x2])
    w = np.array([0.5, 0.5])
    b = -0.7
    tmp = np.sum(w*x) + b
    if tmp <= 0:
        return 0
    else:
        return 1
```

- bias (편향): 한쪽으로 치우쳐 균형을 깬다

## 학습 알고리즘
신경망에는 적응 가능한 가중치와 편향이 있고 이 가중치와 편향을 
훈련 데이터에 적응하도록 조정하는 과정

### 순서
1. 미니배치
  - 훈련 데이터 중 일부를 무작위로 선별한 데이터를 미니배치라 함
  - 미니배치의 손실 함수 값을 줄이는 것이 목표
2. 기울기 산출
  - 미니배치의 손실 함수 값을 줄이기 위해 각 가중치 매개변수의 기울기를 구함
  - 기울기는 손실 함수의 값을 가장 작게 하는 방향을 제시
3. 매개변수 갱신
  - 가중치 매개변수를 기울기 방향으로 아주 조금 갱신
4. 반복
  - 1~3 단계 반복
  
### 확률적 경사 하강법 (stochastic gradient discent, SGD)
데이터를 미니배치로 무작위로 선정하기 때문에 SGD 라고 부름
* stochastic = 확률적
