# KNN: k-nearest-neighbors

![image-20220615234226236](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615234226236.png)

![image-20220615234233585](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615234233585.png)

> k 값이 커질 수록 과하게 일반화

# KNN 의 차원의 저주

![image-20220615234626215](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615234626215.png)

## The curse of dimensionality

* "차원의 법칙" 덕분에 더 높은 차원의 문제에 직면하게 되고, 결국 고차원 공간이 방대하다는 사실로 귀결된다.
* 고차원 공간들의 점(데이터)들은 사실상 매우 멀다.

> 해결하기 위한 방법은 d-dimension 에서 "unit cube" 에서 **점들의 쌍을 랜덤하게 다양하게 생성**하고 그 거리를 계산하는 것이다.

#### 차원이 커질수록 서로간의 거리가 멀어진다.

![image-20220615234758974](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220615234758974.png)

* 레이블링은 필수이다.
  * 레이블링을 하지 않으면, 학습에는 시간이 걸리지 않는 반면에 예측에는 시간이 많이 소요될 것이다.

## k-d tree

* KNN 알고리즘에 사용되는 알고리즘 중 하나

* k-demensional BST(Binary Search Tree)

  

  1. x 축 Median 을 찾은 뒤, 그 Median 을 기준으로 양쪽으로 split 한다.

  2. 각각의 split 된 공간에서 y 축 Median 을 찾은뒤, 마찬가지로 각각 양쪽으로 split 한다.

  3. 이 과정을 반복하여 트리를 형성한다.

![image-20220616001203725](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220616001203725.png)

* range query
  * 범위 내의 데이터를 찾는 query