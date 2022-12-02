---
title: sklearn
---

- sklearn/官网
- sklearn/基础
	- 全流程：[材料数据科学:描述符和机器学习_就很秃然-CSDN博客_机器学习描述符](https://blog.csdn.net/qq_44785318/article/details/114751330)
	- ((4f92dc7b-9df6-4972-b309-f33fd0a0e9c3))
	  collapsed:: true
		- sklearn.feature_selection模块 [结合Scikit-learn介绍几种常用的特征选择方法 - 罗兵 - 博客园](https://www.cnblogs.com/hhh5460/p/5186226.html)
		- Pearson相关系数
		  id:: 6182349b-7ba2-4e80-80b1-4824f9cbd102
		  collapsed:: true
			- 排除线性相关特征的规则
			  :LOGBOOK:
			  CLOCK: [2021-11-04 Thu 11:14:35]
			  :END:
				- 想象成树状结构，从最多的一行开始，如A和B相关，B和C相关，那么可以划掉B和C
				- 相关系数出现两次而且第一次在最左边就排除
			- ``` python
			  """
			  使用Pearson相关系数过滤冗余特征
			  """
			  #标准化
			  from sklearn.preprocessing import StandardScaler
			  scaler=StandardScaler()
			  X_trainval_sca=scaler.fit_transform(X_trainval)
			  #还原X_trainval特征名称
			  X_trainval_sca=pd.DataFrame(X_trainval_sca,columns=scaler.feature_names_in_)
			  #构造全零矩阵，用相关系数替换
			  pearson_coef=pd.DataFrame(np.zeros((X_trainval_sca.shape[1],X_trainval_sca.shape[1])))
			  for i in range(X_trainval_sca.shape[1]):
			      for j in range(i+1,X_trainval_sca.shape[1]):
			    pearson_coef.loc[i,j]=np.corrcoef(X_trainval_sca.T)[i,j]
			  #构造DataFrame
			  pearson_coef.columns=[scaler.feature_names_in_]
			  pearson_coef.index=[scaler.feature_names_in_]
			  #筛选出相关系数>0.95或者<-0.95的行
			  pearson_coef_filter=pearson_coef.loc[pearson_coef.where((pearson_coef>0.95)|(pearson_coef<-0.95)).any(1)]
			  #筛选出每行相关系数>0.95或者<-0.95的列，并组合
			  for j in range(pearson_coef_filter.shape[1]):
			      _=list(pearson_coef_filter.columns[j])
			      _.append(pearson_coef_filter[pearson_coef_filter.iloc[:,j]>0.95].index.tolist())
			      if len(_)!=1:
			    print(_)
			  #有需要可以导出数据到excel作图
			  #pearson_coef_filter.to_excel('E:\Panyue\Data\JP\ML\pearson_coef.xlsx')
			  
			  ```
		- Spearmanr相关系数
		  collapsed:: true
			- ``` python
			  """
			  使用Spearmanr相关系数过滤冗余特征
			  """
			  from scipy.stats import spearmanr
			  spearmanr_coef=pd.DataFrame(np.zeros((X_trainval.shape[1],X_trainval.shape[1])))
			  rho,pval=spearmanr(X_trainval.T)
			  for i in range(X_trainval.shape[1]):
			      for j in range(i+1,X_trainval.shape[1]):
			    spearmanr_coef.loc[i,j]=rho[i,j]
			  #构造DataFrame
			  spearmanr_coef.columns=[pipe1.feature_names_in_]
			  spearmanr_coef.index=[pipe1.feature_names_in_]
			  #筛选出相关系数>0.95或者<-0.95的行
			  spearmanr_coef_filter=spearmanr_coef.loc[spearmanr_coef.where((spearmanr_coef>0.95)|(spearmanr_coef<-0.95)).any(1)]
			  #筛选出每行相关系数>0.95或者<-0.95的列，并组合
			  for j in range(spearmanr_coef_filter.shape[1]):
			      _=list(spearmanr_coef_filter.columns[j])
			      _.append(spearmanr_coef_filter[spearmanr_coef_filter.iloc[:,j]>0.95].index.tolist())
			      if len(_)!=1:
			    print(_)
			  #有需要可以导出数据到excel作图
			  #pearson_coef_filter.to_excel('E:\Panyue\Data\JP\ML\pearson_coef.xlsx')
			  
			  ```
		- ((781a5e48-6ca7-40db-9e03-bf292e625fb4))
			- "在sklearn中，主要实现可以分成基于惩罚项的特征选择法和基于树模型的特征选择法。"[zsjsnanavfag (2019) 数据挖掘特征选择三大方法总结以及在sklearn中的实现](https://zhuanlan.zhihu.com/p/99776961)
	- ((0b63739d-ea14-44d5-852c-b69cfdba8721))
		- [sklearn的回归模型评价指标](https://scikit-learn.org/stable/modules/model_evaluation.html#regression-metrics)
	- fit、transform和fit_transform的区别
	  collapsed:: true
		- fit是获取数据的固有属性，如平均值、最大值等
		- transform是使用数据的固有属性对原始数据进行缩放，如最大值最小值缩放等
		- fit_transform是根据一组数据的固有属性变换所有数据，如根据训练集的固有属性变换测试集
	- Bunch对象：类似于字典，特征的键为data，目标的键为target
	- [sklearn的学习曲线](https://scikit-learn.org/stable/auto_examples/model_selection/plot_learning_curve.html#sphx-glr-auto-examples-model-selection-plot-learning-curve-py)
	  id:: 61405dc9-4bb1-4c2f-8832-99146aeb7d0e
	- ``` python
	  #输出数据手动作图
	  def plot_learning_curve_data(estimator, X, y, 
	                     cv=None, train_sizes=np.linspace(.1, 1.0, 5)):
	      train_sizes, train_scores, test_scores= \
	      learning_curve(estimator,X,y,train_sizes=train_sizes,cv=cv)
	      train_scores_mean = np.mean(train_scores, axis=1)
	      train_scores_std = np.std(train_scores, axis=1)
	      test_scores_mean = np.mean(test_scores, axis=1)
	      test_scores_std = np.std(test_scores, axis=1)
	      print(train_scores_mean,test_scores_mean,train_sizes)
	  plot_learning_curve_data(pipe,X_trainval,y_trainval)
	  
	  ```
	- TODO 学习曲线的横坐标是交叉验证折数还是样本数？
	  id:: 614de3d5-6b1f-4a10-9a25-754fcbd8a159
- sklearn/问题
	- 网格搜索pipe中的参数需要在字典中加“缩写__”前缀，否则会报错 Invalid parameter。[一个例子](https://www.5axxw.com/questions/content/8f560l)
	  collapsed:: true
		- ``` python
		  pipe=Pipeline([('pca',PCA()),('rege',SVR())])
		  param_test1={'rege__C':np.linspace(0.01,0,1)}
		  #而不是
		  param_test1={'C':np.linspace(0.01,0.1)}
		  
		  ```
	-