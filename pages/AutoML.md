- ## 库
  id:: 6224b3d5-64ef-4d2d-ba45-f7a1232a23f6
  collapsed:: true
	- ((12723764-b137-4fbd-8029-d0c7b36d0e4a))
	  id:: 625cc206-ccb2-42d7-add0-7f48ebdfe308
- EvalML
  collapsed:: true
	- [Install — EvalML 0.44.0 documentation](https://evalml.alteryx.com/en/latest/install.html)
	- EvalML/使用
	  collapsed:: true
		- 时序模型
		  id:: 62105ddc-bea1-410b-9fed-39f0b2ea2668
		  collapsed:: true
			- [AutoMLSearch for time series problems — EvalML 0.44.0 documentation](https://evalml.alteryx.com/en/latest/user_guide/timeseries.html)
- [[PyCaret]]
- TPOT
  collapsed:: true
	- 遗传算法优化超参数，简单易上手（[松桦 关于AutoML，你想知道的都在这里！](https://zhuanlan.zhihu.com/p/93109455)），但支持模型少，性能不高（[字节 走马观花AutoML](https://zhuanlan.zhihu.com/p/212512984)）
- Auto-sklearn
  collapsed:: true
	- 效率高（[字节 走马观花AutoML](https://zhuanlan.zhihu.com/p/212512984)），[不支持Windows](https://automl.github.io/auto-sklearn/master)
- [HyperGBM](https://hypergbm.readthedocs.io/en/latest/overview_about.html)
  collapsed:: true
	- 是以GBDT算法为核心的automl，支持强化学习和迁移学习等高级功能
- AutoKeras
  collapsed:: true
	- AutoKeras/官网
	  collapsed:: true
		- [AutoKeras](https://autokeras.com/)
	- AutoKeras/基础
	  collapsed:: true
		- 安装：先安装tensorflow，再安装autokeras
		  collapsed:: true
			- [解决国内安装Tensorflow太慢的问题_大脸猫的博客-CSDN博客_tensorflow安装慢](https://blog.csdn.net/qq_38890412/article/details/104339698)
			  
			  ```
			  pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ --upgrade tensorflow
			  
			  ```
		- 自动搜索神经网络架构，支持多任务学习
		- [Automated Machine Learning with AutoKeras: Deep learning made accessible for everyone with just few lines of coding ](https://zh.1lib.pl/book/14621461/c606d4?signAll=1&ts=0511)：[配套代码](https://github.com/PacktPublishing/Automated-Machine-Learning-with-AutoKeras)
		- 多任务学习
		  id:: 61b944a5-e67b-490d-abc0-307a4dcfc6a2
		  collapsed:: true
		  :LOGBOOK:
		  CLOCK: [2021-12-12 Sun 21:00:06]--[2021-12-12 Sun 21:04:39] =>  00:04:33
		  :END:
			- 实例：[rahul-pande/faces-mtl: Multi Task Learning example with Keras](https://github.com/rahul-pande/faces-mtl)
			- 实例：[大众点评评论的4分类20个多任务学习](https://github.com/CuiShaohua/MultiTaskLearning#%E5%A4%A7%E4%BC%97%E7%82%B9%E8%AF%84%E8%AF%84%E8%AE%BA%E7%9A%844%E5%88%86%E7%B1%BB20%E4%B8%AA%E5%A4%9A%E4%BB%BB%E5%8A%A1%E5%AD%A6%E4%B9%A0)
			- 实例：[yaringal/multi-task-learning-example: A multi-task learning example for the paper https://arxiv.org/abs/1705.07115](https://github.com/yaringal/multi-task-learning-example)
			- 自动调节权重：[2018 MTL Using Uncertainty to Weigh Losses - 知乎](https://zhuanlan.zhihu.com/p/269162365)
	- AutoKeras/问题
	  collapsed:: true
		- LSTM
		  id:: 6210a0e1-044a-402a-b14e-f50eefe2d679
		  collapsed:: true
			- [may i ask how to use the lstm block in autokeras · Issue #696 · keras-team/autokeras](https://github.com/keras-team/autokeras/issues/696)
		- 运行 [Example](https://autokeras.com/tutorial/multi/)
		  collapsed:: true
			- 使用rmse报错，因为rmse不属于[Keras可用损失函数](https://keras.io/zh/losses/)
			- 报错 No module named 'statsmodels'，解决方法 pip install statsmodels
			- 报错 Failed to convert a NumPy array to a Tensor，解决方法是定义数字格式为float32
		- Anaconda 3.6导入包 from keras.models import Sequential 时报错 cannot import name 'LayerNormalization'
		  collapsed:: true
			- [关于使用Keras 中Sequential语句引用时报错的解决方法_zero00moon的博客-CSDN博客](https://blog.csdn.net/zero00moon/article/details/111169088)：将from keras ...改成from tensorflow.python.keras ...
- ## 和“手动机器学习”的区别
  id:: 6224b3f7-03ac-4974-98ca-9776d4e86575
<<<<<<< HEAD
=======
  collapsed:: true
>>>>>>> 7394450ff3f1d3d6e5ef95d10c09eb98f8833ef9
	- [汇雅电子书-自动机器学习入门与实践](http://book.sslibrary.com/book/card?cnFenlei=TP311.561&ssid=14740604&d=b73c60b976ee9bc1eb424d0724405ac5&isFromBW=true&isjgptjs=false)
	- [Automated Machine Learning | SpringerLink](https://link.springer.com/book/10.1007/978-3-030-05318-5#toc)：免费电子书
- AutoML关心的是最终的模型，科研特别是材料科学并不十分关心模型，而更关心对建模过程的分析
- AutoML库在建模的过程中**不会产生很多数据**，最多有一些可视化工具帮助诊断模型
- 因此AutoML更适合**工业领域需要快速部署模型的场景**，并不适合科研