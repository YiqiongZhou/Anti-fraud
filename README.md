# Anti-fraud


未完待续。。。
蚂蚁金服风险大脑 支付风险识别比赛
网址：https://dc.cloud.alipay.com/index#/topic/intro?id=4

萌新第一次参加比赛代码分享


a榜最高：0.3919
b榜最高：0.3807（后面和一个大佬融合一下达到了0.3993，以下的思路只涉及到我的模型）

我的思路：
直接利用所有数据，并不作处理

具体细节：
缺失值填充方面：
利用随机森林来筛选特征，最后调参发现175个特征效果是最好的（因为随机森林不能处理缺失值的情况，所以在这里我用了均值去填充）
后面直接把随机森林选出的特征放入到XGBoost
XGBoost中的特征对应的数据并没有填充缺失值（我的实验效果不填比填了好） 

处理模糊样本方面：
官方给出的题目有提到过，模糊样本的来源在于他们之前的系统砍掉的交易，因为他们认为这些交易有风险，所以砍掉


样本非常不平衡方面：
我尝试过上采样，下采样，smote，smote+enn等多种方式，在我这个模型中都比不上不采样的效果好
在不平衡的数据处理方面，推荐一个包： imbalanced-learn（这里面有多种采样方式的api）
http://contrib.scikit-learn.org/imbalanced-learn/stable/index.html

在模型集成方面：
我尝试了用xgboost的叶子结点


在使用规则方面：

在特征工程方面：

在参数方面：

一些新的思考：
最后一句：
生活硬是把我这样精致的猪猪女孩变成了IT民工！！！！

我的尝试（失败了的。。。）

在筛特征的时候：
我尝试过用pca，但效果并不好，我的理解是：pca的原理是主成分分析




