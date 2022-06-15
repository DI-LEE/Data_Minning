# Machine learning

*predictive modeling/data mining*

> model

* 서로 다른 변수 사이에 존재하는 수학적(또는 확률적) 관계의 규격.

> Machine learning

* 데이터로부터 학습시킨 model 을 만들거나 사용하는 것

## supervised models(지도학습)

* 레이블링 된 데이타로부터 학습시키는 방법론
* 답이 정해져 있음

ex)

* Regression
  * 주식
* Classification

## unsupervised models(비지도학습)

* 레이블되어 있지 않은 데이터들로 부터 학습시키는 방법론

ex)

* clustering
* anomaly detection
* association
* topic modeling
* Autoencoders

※*PCA/TSNE(manifold learning) 는 unsupervised learning model 이다*

## Semi-supervised model(준지도학습)

* 소량의 레이블된 데이터에는 supervised learning을 적용하고 대용량 레이블되어 있지 않은 데이터에는 unsupervised learning을 적용하여 추가적인 성능향상을 목표로 하는 방법론

## The Bias-Variance Trade-off

> bias

* 실제값과 예측값의 차이의 평균

> variance

* 분산

**model 에서는 bias 와 variance 가 반비례 관계에 있다.**

## overfitting

> bias ↓ , variance ↑

* 모델이 너무 복잡할 경우 발생
* 극단적으로 학습시킨 train data 에 대해서는 예측을 잘하지만, 학습시키지 않은 새로운 데이터는 예측하지 못한다.
* learning noise 가 수반된다.

### underfitting

> bias ↑ , variance ↓

* 모델이 너무 단순할 때 발생
* 새로운 데이터는 물론 학습된 데이터 조차 예측하지 못함



![image-20220615220857434](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615220857434.png)

![image-20220615220838134](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615220838134.png)

![image-20220615220918819](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615220918819.png)



# Occam's razor(절약의 원칙)

"면도날로 불필요한 것을 자른다"

* 단순한 것이 최고다 라는 의미
* 간단한 해결책이 복잡한 해결책보다 훨씬 낫다는 의미

## Overfitting 피하는 법

* 데이터를 **학습용 데이터**와 **테스트용 데이터**로 분류하여 학습을 진행하고 예측하여 오류치를 측정한다.
* 데이터의 수를 늘린다.
* 모델의 복잡도를 낮추고 단순화한다.
* 정규화(Regularization)을 사용한다.

![image-20220615220939052](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615220939052.png)

# Feature Extraction and selection

*feature engineering*

* Dimensionality Reduction
  * ex) PCA, TSNE
* “Regularization” that penalizes models using more features (SVM or regression)
* "Dropout" in Deep neural network



---



# accuracy

### "Luke" 라는 이름을 가진 아기는 백혈병에 걸릴 것이다. => 98% accuracy

*accuracy 가 의미가 있을까?*

|            | 백혈병 | 백혈명 x   | total       |
| ---------- | ------ | ---------- | ----------- |
| "Luke"     | **70** | 4930       | 5000        |
| not "Luke" | 13930  | **981070** | 995000      |
| total      | 14000  | 986000     | **1000000** |

accuracy = (70+981070)/1000000 = 0.98114

* **데이터의 비율이 매우 비대칭적이기 때문에 높은 accuracy 가 의미가 없다.**

## confusion matrix

* binary judgment (0,1) 일 때
  * 예 아니오로 답할 수 있는 판단

|                 | predictive positive | predictive negative |
| --------------- | ------------------- | ------------------- |
| actual positive | TP                  | FN                  |
| actual negative | FP                  | TN                  |


#### TP : True Positive

* 실제: 사실/예측: 맞다

#### FP : False Positive

* 실제: 거짓/예측: 맞다

#### FN : False Nagative

* 실제: 거짓/예측: 틀리다

#### TN : True Nagative

* 실제: 거짓/예측: 틀리다 

## Precision(정밀도)

 *how accurate our positive predictions were*

> Positive 라고 예측한 것 중에 True positive

* TP/TP+FP

## Recall(재현율)

*what fraction of the positives our model identified*

> Positve 인 것 중에 True positive

* TP/TP+FN

## f1_score

* 2xPxR/(P+R)

> Precision 과 Recall 간의 조화평균
* 어느 한쪽으로 치우치지 않을 때 조화롭게 높은 값
* 경우에 따라 Precision 과 Recall 의 중요도를 다르다.

* Precision 과 Recall 은 반비례 관계

### weight average

* w1·x1 + w2·x2+ ··· + wn·xn / w1+w2+···+wn



### Trade-off between precision and recall

* Precision 과 Recall 은 반비례 관계
* 균형 필요



