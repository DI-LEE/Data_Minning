# Clustering

* unsupervised learning
* unlabeled data
* 차원이 커지면 clustering 을 할 이유가 없다
## k-means

* 현재 완벽한 클러스터링을 찾는 것은 불가능하다.

1. k-means 를 설정한다.
2. means 에 가까운 점들을 할당한다.
3. 더이상 할당할 점들이 없으면 멈춘다.
4. 할당한 점들이 바뀌면, 다시 2번으로 돌아가 계산한다.

#### ***means(새로 구하는 값)** 를 찾는 것이 의미 없는 경우 **Medoid(실제 존재하는 값)** 를 찾는다(k-medoid)*

* ex) 



### Inter cluster distance

* cluster 의 mean 사이의 거리

### Intra cluster distance

* cluster 내부의 점과 mean 사이의 거리

> cluster 에서 inter cluster 는 최대로 intra cluster 는 최소화해줘야 한다.

![image-20220616005820243](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220616005820243.png)

![image-20220616005838920](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220616005838920.png)

* k가 작아질수록 모델이 심플
* k가 클수록 모델이 복잡

![image-20220616030841634](C:\Users\leedo\AppData\Roaming\Typora\typora-user-images\image-20220616030841634.png)

꺽이는 지점이 가장 적합한 k 값