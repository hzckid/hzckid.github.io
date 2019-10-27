# Machine Learing
## 什么是参数估计和非参数估计？
* parameter estimate: 先假定研究的问题具有某种数学模型，如normal distribution, binominal distribution, 再用已知类别的学习样本估计里面的参数。
* unparameter estimate: 不假定数学模型，直接用已知类别的学习样本的先验知识直接估计数学模型。

* l1-norm (lasso regularizer) and l2-norm (ridge regulrizer) are able to reducing overfitting, but the bonus of l1-norm will get more sparse representation solver, i.e. l1-norm have less non-zero factor.


# Ensemble learning
* Base theory: PAC(probably approximately correct):概率近似正确  
* Ensemble learning is care about Bias-Variance balance, what it is a perpetual topic in machine learning. The ensemble learning try to reduce one without adding another, even reduce both together, while the cost is ensemble.

1. Bagging (abbr. of Boostrap aggregating)  
Train multiepoch, re-sample as the input, the final result dicision with vote.

2. Boosting  
Popular method is AdaBoost (Adaptive Boosting); Initial each classifier with equal weight, afterwards training with t epoch, then offer the error training instance with higer weight, which make the algorithm concentrate on the failure sample, and vise versa. The final result produce with voting.

3. Stacking  
Proposed by Wolpert in paper "Stacked Generalization"
The stacking could considering as the generalize of Aggregation in ensemble. Replacing the voting or averaging in bagging and boosting to decresing the bias and variance.Such as the voting could replace by KNN, softmax (logistic regression) instead weight voting and linear regressiong for averaging.


3. Cascading  


3. NFL  
proposed by David H. Wolpert.
假设在整个函数空间中所有可能的目标函数f是均匀分布的（也就是说现实中的真实的问题是均匀出现的（因此这个就是我开头所说的前提！！！）


4. CrossValidation(abbr. as CV)
Proposed by Seymour Geisser, the CV known as *Rotation Estimation* a pratical approach to cutting the dataset into subset in statistic.
When training data, leave one subset as testing data, the others as traing data, until every subset had test and only once time.  Then add predict error of each sample as the PRESS (predicted error sum of squares).

3. difference between bagging and boosting:
data of bagging generate from re-sample, while bootstraping sample with error rate, thus the classify of bootstrap is better than bagging.

4. compositional algorithem based on bagging and boosting:  
Bagging  + DecisionTree = Random Forest  
AdaBoost + DecisionTree = Boosting Tree (the base classifier is CART) 
Gradient + DecisionTree = GBDT(gradient boosting decision tree) (generally used in regression, XGBoost is engineer work of GBDT)

5. DecisionTree  
* ID3  使用信息增益熵
* C4.5 C4.5算法不直接用信息增益，而是使用信息增益率来选择最优划分
* CART CART使用基尼指数来选择划分

非参数估计方法 Mente Carlo Estimation,Bootstrap是Mente Carlo的基础上提出来的，其实质是对观测信息进行再抽样，进而对总体的分布特性进行统计推断。
Re-sample 在抽样,有放回的抽样，从旧的样本中抽取一定数据量的新样本。

what is bootstraping? It is come from 'pull up by your ownbootstraps', means rely on your resource, utilize the re-sample trick.

## tmp
* diff of ML and PR?

1. Data classify with structure whether having neat structure or not?  
* Euclidean Structure Data   
* Non-Euclidean Structure Data: Graph or Manifold.

2. dimension reduction algrithm  
* PCA (pricinple componet analysis)
* LDA (Linear Discriminant Analysis)
* LLE (local linear embedding)
* Laplacian Eigenmaps (local aspect)

## SVM (support vector machine)
1. what is the representation of inner product?  
x=(x1,x2,x3),y=(y1,y2,y3)  x*y=x1*y1+x2*y2+x3*y3  
The means of inner product of x and y is that vector x projection in vector y.

2. kernel trick
why need kernel trick? Some case we need to mapping data to high dimenstion, it should find some distance measure, such as the inner product, however calucation the inner product in high dimension is complex, thus is there existing some approch could do it in simple way? The answer is Kernel Function.  
![kernel](https://github.com/hzckid/hzckid.github.io/blob/master/img/kernel.png)  
As above mentioned, the essence of Kernel Function is inner(dot) product of high dimension, the Kernel function K(v1,v2) represent as mapping two vector v1 and v2 in the origin vector to high dimension space, then calculating the dot product. The mapping rule $P(x,y)=(x^2,\sqrt[2]{2}xy,y)$ will map two dimension data into three dimension data. As for the Kernel function:
$$
K(x,z) = exp(-\frac{\|x-z\|^2}{2\sigma^2})
$$
In this fucntion, if x is similar to z ( $\|x-z\|\approx0$ ),  the kernel value would be 1, while if x is vary widely with z ($\|x-z\|\gg0$), then the kernel function is approximately equal to 0. Because this function is similar to Gaussian distribution, it also konw as Gaussian Kernel Function or RBF (Radial Basis Funtion), it could map the origin feature to infinite dimension.
* RBF rely on the dot distance, i.e.,  $\phi(x,y)=\phi(\|x-y\|)$. Any function $\phi$ satisfy this condition would be the RBF, generally speaking the distance is euclidean, it could be other distance as well. The other two common kernel function is Exponential kernel 
  $$
  k(x,z)=exp(-\frac{\|x-z\|}{2\sigma^2})
  $$
  and Laplacian kernel
  $$
  k(x,z)=exp(-\frac{\|x-z\|}{\sigma})
  $$
  





