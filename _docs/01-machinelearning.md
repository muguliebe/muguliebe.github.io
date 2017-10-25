---
title: "Machine Learning"
permalink: /docs/ai/ml/
excerpt: "개요"
redirect_from:
  - /theme-setup/
---

{% include base_path %}

### 개요
machine learning is...

### 종류
- Supervised learning
- Unsupervised learning
- Reinforcement learning

### 흐름
1. 데이터 수집
1. 데이터 가공
1. 데이터 학습
1. test
1. good job

###4-5~4-7
#### <참고자료>
* [SVM에 대한 자세한 내용](https://ko.wikipedia.org/wiki/%EC%84%9C%ED%8F%AC%ED%8A%B8_%EB%B2%A1%ED%84%B0_%EB%A8%B8%EC%8B%A0) (참고:[ 평면 방정식](http://showmiso.tistory.com/62))
* 머신러닝의 모델 성능에 대한 지표로 precision, recall, f1-score, support 가 사용된다.

>TERMS:
>  * True Positive(TP) : True인데 True라고 맞춘 경우 (맞음)
>  * False Positive(FP) : False인데 True라고 한 경우 (틀림)
>  * True Negative(TN) : False인데 False라고 한 경우 (맞음)
>  * False Negative(FN) : True인데 False라고 한 경우 (틀림)

1. Accuracy(정확도)
  TP+TN / TP+TN+FP+FN
  (올바른 판단 횟수) / (판단 총 횟수)
  **→ 전체 판단 중 얼마나 정확하게 맞추었는가**
2. Precicion(정밀도)
  TP / TP+FP
  (실제 True 횟수) / (True라고 판단한 횟수)
  **→ True로 분류했는데 그 것이 진짜로 True인가?**
3. Recall(재현율)
  TP / TP+FN
  (True 횟수) / (올바른 판단 횟수)
  **→ 바르게 판단한 케이스 중 진짜 True인 case를 얼마나 정확히 맞추었는가?**
4. F1-score
  정밀도와 재현율의 가중치가 같은 **조화평균**
  [참고자료 필독](http://blog.acronym.co.kr/557)
