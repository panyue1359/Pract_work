---
title: Python/Library/优化算法库
---

- [[skopt]]
  id:: 621d77a3-ed57-420b-848a-a4a23b15eeb0
	- skopt/基础
	  collapsed:: true
		- skopt/基础/超参数优化
		  id:: 621cd17b-0af6-4990-bb83-971b3d851fc3
			- 代码
			  
			  ``` python
			  #使用高斯过程给出不确定度
			  from skopt import gp_minimize
			  from skopt.space import Integer, Real
			  #根据实际情况定义space
			  space=[Integer(2,50,name="n_neighbors")]
			  #skopt中优化器导入多维数据需要扩展use_name_args
			  from skopt.utils import use_named_args
			  @use_named_args(space)
			  def objective(**params):
			      rege.set_params(**params)
			      return -np.mean(cross_val_score(rege, X_trainval, y_trainval, cv=13,\
			                                scoring="neg_mean_absolute_error"))
			  #贝叶斯优化调参
			  res_gp=gp_minimize(objective,space,n_calls=50,random_state=0)
			  #分数越接近0越好
			  "Best score=%.4f" %res_gp.fun
			  print("""Best parameters:%s""" % (res_gp.x))
			  
			  ```
		- 高斯贝叶斯全局寻优，参数设置[参考](https://scikit-optimize.github.io/stable/modules/generated/skopt.utils.use_named_args.html#skopt.utils.use_named_args)
		  collapsed:: true
			- ``` python
			  #优化前先fit模型
			  #可以使用其他先验函数如forest_minimize,gbrt_minimize等
			  from skopt import gp_minimize
			  from skopt.space import Integer, Real
			  space_frac=[Real(0.1,1,name='Al'),Real(0.1,1,name='Co')\
			        ,Real(0.1,1,name='Cr'),Real(0.1,1,name='Cu')\
			        ,Real(0.1,1,name='Fe'),Real(0.1,1,name='Mn')\
			        ,Real(0.1,1,name='Ni'),Real(0.1,1,name='V')]
			  from skopt.utils import use_named_args
			  @use_named_args(space_frac)
			  def ratio_to_pred(Al,Co,Cr,Cu,Fe,Mn,Ni,V,rege=rege):
			      atomic=np.array([Al,Co,Cr,Cu,Fe,Mn,Ni,V])
			      X_pred=dataset_generator.frac_ele_emp(atomic)
			      X_pred=X_pred[frac+ele_candidate+emp_candidate].values
			      #加负号使问题转换为找最小值
			      return -rege.predict(X_pred)[0]
			  #绘制优化轮数-目标值图
			  from skopt.plots import plot_convergence
			  result=gp_minimize(ratio_to_pred,space_frac,n_calls=100\
			               ,acq_func='EI',random_state=0)
			  print("x^*=%s, f(x^*)=%.4f" % (result.x, result.fun))
			  plot_convergence(result)
			  
			  ```
			-
- 智能优化算法包
  id:: ZpK7p4gIM
  id:: ab779f03-9307-405f-ab91-7d0694e96321
	- NEORL
	  id:: 6227e9c4-99dd-4bce-8f16-350999041f80
		- 官网：[NEORL](https://neorl.readthedocs.io/en/latest/index.html)
		- 一个混合神经网络和遗传算法的Python优化算法库，含更多启发式算法
			- ((e77bc68c-5d39-4a30-aefb-3cc28119d90f))
		- 需要Python3.7
	- 遗传算法
		- sklearn deap
			- 官网：[sklearn deap](https://github.com/rsteca/sklearn-deap)
			- 可以特征选择（EvolutionarySearchCV），也可以单纯的寻优（maximize）
			- 安装sklearn deap需要 "numpy>=1.9.3","scipy>=0.16.0", "deap>=1.0.2","scikit-learn>=0.24.0"
		- scikit-opt
			- 官网：[scikit-opt](https://scikit-opt.github.io/scikit-opt/#/zh/)
			- 国产良心（[Python智能优化算法库小汇总 - 知乎](https://zhuanlan.zhihu.com/p/181588957)）
			- 和skopt不一样
		- sklearn-genetic
			- 官网：[sklearn-genetic库](https://github.com/sk1010k/sklearn-genetic)
			- 特征选择
			- 感觉速度非常慢
		- Geatpy
			- 官网：[Geatpy](http://geatpy.com/)
			- 求解[Pareto前沿](http://geatpy.com/index.php/2019/07/28/%E7%AC%AC%E4%B8%83%E7%AB%A0%EF%BC%9A%E5%A4%9A%E7%9B%AE%E6%A0%87%E4%BC%98%E5%8C%96/)
		- gplearn
			- 官网：[gplearn](https://gplearn.readthedocs.io/en/stable/installation.html)
			- [【Python机器学习】用遗传算法实现符号回归——浅析gplearn - 知乎](https://zhuanlan.zhihu.com/p/31185882)
			- [【Python机器学习】用遗传算法实现符号回归——浅析gplearn - 知乎](https://zhuanlan.zhihu.com/p/31185882)
- kriging优化包：pyKriging
  id:: 621d75cb-981a-4d7f-a3c3-c2ec1cf0ce40
	- 官网：[pyKriging](http://www.pykriging.com/)
-