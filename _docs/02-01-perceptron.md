---
title: "Deep Learning"
permalink: /docs/ai/dl/perceptron
excerpt: ""
redirect_from:
  - /theme-setup/
---

## perceptron
- 1957년에 프랑크 로젠블라트(Frank Rosenblatt) 가 제안
- 신경망(딥러닝)의 기원이 되는 알고리즘
- 다수의 신호를 입력으로 받아 하나의 신호를 출력

## neuron
![alt](http://muguliebe.github.io/assets/images/perceptron/fig2-1.png)
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
![alt](http://muguliebe.github.io/assets/images/perceptron/e2.2.png)
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

