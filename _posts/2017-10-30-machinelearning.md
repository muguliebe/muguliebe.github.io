---
layout: post
title: "Machine Learning"
date: 2017-10-30
categories: AI
tags:
- machine learning
---

### 개요
machine learning is...

### 종류
- Supervised learning
- Unsupervised learning
- Reinforcement learning

<!-- more -->

### 흐름
1. 데이터 수집
1. 데이터 가공
1. 데이터 학습
1. test
1. good job

### 4-5~4-7
#### <참고자료>
* [SVM에 대한 자세한 내용](https://ko.wikipedia.org/wiki/%EC%84%9C%ED%8F%AC%ED%8A%B8_%EB%B2%A1%ED%84%B0_%EB%A8%B8%EC%8B%A0) (참고:[평면의 방정식](http://showmiso.tistory.com/62))
* [SVM 강의](https://www.youtube.com/watch?v=_PwhiWxHK8o) (19분까지는 margin을 수학적으로 구하는 방법, 그 이후로는 초평면을 찾는 과정)
* 머신러닝의 모델 성능에 대한 지표로 accuracy, precision, recall, f1-score, support 가 사용된다.  

>TERMS:
>  * **True Positive(TP) : True라고 예측하고 True 결과값을 얻음 (맞음)**  
>    *ex) 스팸으로 예측하여(T) 스팸함에 넣었는데 진짜로 스팸이었다(T)*  
>  * **False Positive(FP) : True라고 예측하고 False 결과값을 얻음 (틀림)**  
>    *ex) 스팸으로 예측하여(T) 스팸함에 넣엇는데 스팸이 아니었다(F)*  
>  * **True Negative(TN) : False라고 예측하고 False 결과값을 얻음 (맞음)**  
>    *ex) 스팸이 아니라고 예측하여(F) 받은 메일함에 넣엇는데 스팸이 아니었다(F)*  
>  * **False Negative(FN) : False라고 예측하고 True 결과값을 얻음 (틀림)**  
>    *ex) 스팸이 아니라고 예측하여(F) 받은 메일함에 넣엇는데 스팸이었다(T)*  

![참고그림](https://charsyam.files.wordpress.com/2017/04/table.png?w=776)

* Accuracy(정확도)  
  - TP+TN / TP+TN+FP+FN  
  (올바른 판단 횟수) / (판단 총 횟수)  
  **→ 전체 판단 중 얼마나 정확하게 맞추었는가**  
* Precicion(정밀도)  
  - TP / TP+FP  
  (실제 True 횟수) / (True라고 판단한 횟수)  
  **→ True로 분류했는데 그 것이 진짜로 True인가?**  
* Recall(재현율)  
  - TP / TP+FN  
  (True 횟수) / (올바른 판단 횟수)  
  **→ 바르게 판단한 케이스 중 진짜 True인 case를 얼마나 정확히 맞추었는가?**  
* F1-score  
  - 정밀도와 재현율의 가중치가 같은 **조화평균**  
  [참고자료 필독](http://blog.acronym.co.kr/557)  
