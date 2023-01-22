- ## 基础
- [PyCaret帮助网站](https://pycaret.readthedocs.io/en/latest/installation.html)
- 支持模型多（[阿水 盘点Kaggle中常见的AutoML工具库](https://zhuanlan.zhihu.com/p/427547997)），full版含XGBoost #XGBoost
- 通用
  collapsed:: true
	- prepare data
	  collapsed:: true
		- 加载数据集失败，报错[11004](https://docs.microsoft.com/zh-cn/windows/win32/debug/system-error-codes--9000-11999-)，修改DNS后报错[WinError 10060]，等待一段时间后可以下载
		- pycaret中的数据集是数据和标签放在一个dataframe中，一个sample=instance+label
	- setup
	  collapsed:: true
		- 设置test_data后，hold_out sample即test_data
		- 在setup中设置Preprocessing=False，normalize将失效
		- setup设置transform_target=True可以显著提高svm分数
		- 我的数据集设置transform_target=True没有影响
		- setup中的transform_target默认使用“[Box-Cox转换](https://zhuanlan.zhihu.com/p/38956042)”
		- 如果提示“Input contains NaN, infinity or a value too large for dtype('float64').”，首先检查数据是否正常
		- 第一列可能被预处理掉，需要注意
	- compare_model
	  collapsed:: true
		- compare中设置turbo=False可以保留svm，这个参数的作用是排除训练时间过长的算法
	- tune_model
	  collapsed:: true
		- tune_model中设置search_algorithm='grid'速度非常慢，效果也不好
		- tune_model首先打印默认参数的10折交叉验证结果，最后打印新的超参数中最佳的一组的10折交叉验证结果
		- [tune_model无法返回最优参数](https://github.com/pycaret/pycaret/issues/1987)
		- [Tuned model behaves even worse · Issue #234 · pycaret/pycaret](https://github.com/pycaret/pycaret/issues/234)：建议设置choose_better=True，并提高n_iter
		- [5个PyCaret的常见误解 - 人工智能遇见磐创 - 博客园](https://www.cnblogs.com/panchuangai/p/13967157.html)：先调好参数再creat_model
		- [Time Series | Tuning Custom Models & Pipelines · Discussion #1954 · pycaret/pycaret](https://github.com/pycaret/pycaret/discussions/1954)：通过设置return_tuner=True获取调参中间过程，如下
		  collapsed:: true
			- ``` python
			  tuned_custom_model, tuner = exp.tune_model(custom_model, custom_grid=my_grid, return_tuner=True)
			    #按分数降序排列
			      pd.DataFrame(random_tuner.cv_results_).sort_values("最后一列表头")
			  
			  ```
		- 自定义超参数列表需要自己划分，如设置自定义超参为\'A':[1,50]，则调参算法只尝试1和50
		- choose_better=True，则算法比较新参数中最好的和默认参数，设置为False则总是返回新参数
- 时序模型
  id:: 62105d92-7a2e-4c0d-8809-9a2b70476a2c
  collapsed:: true
	- [Time Series — pycaret 2.2.0 documentation](https://pycaret.readthedocs.io/en/time_series/api/time_series.html)
	- [pycaret/time_series_101.ipynb at time_series · pycaret/pycaret](https://github.com/pycaret/pycaret/blob/time_series/time_series_101.ipynb)
	- [Quickstart - PyCaret Official](https://pycaret.gitbook.io/docs/get-started/quickstart#time-series-beta)
	- 数据格式为Series，索引是时间，需要 ((4a5212de-5233-40ad-a363-76e5ad7ae0ba))
	- [fold_strategy](https://github.com/pycaret/pycaret/discussions/1761)
	  collapsed:: true
		- SlidingWindowSplitter已替换为在setup-fold_strategy中设置"sliding"
		- 根据time_series_experiment.py中源代码，**window_length**（预测所用数据天数）的公式为y_size - ((fold - 1) * step_length + 1 * fh_max_length)，**step_length**=fh
		- 当fh=1时，window_length=fold
- 模型解释
  collapsed:: true
	- ((f5e7a530-b10f-404c-8f6f-1e66281d6318))
- ## 问题
- 报错`No module named pycaret`
	- ((63aa5eef-850d-4ba9-9250-6502a90f6d24))：在虚拟环境中添加kernel，而不是base环境 [python - No module named 'pycaret - Stack Overflow](https://stackoverflow.com/questions/68310729/no-module-named-pycaret)
- Pycaret中的BaggingRegressor代码和sklearn网站的不一样
- 报错 cannot import name 'delayed' from 'sklearn.utils.fixes，查看原文件发现文件名错误
- 报错`ConnectionError: HTTPSConnectionPool(host='raw.githubusercontent.com', port=443): Max retries exceeded with url: /pycaret/datasets/main/data/common/mice.csv (Caused by NewConnectionError('<urllib3.connection.HTTPSConnection object at 0x0000022BB6CF1340>: Failed to establish a new connection: [Errno 11004] getaddrinfo failed'))`，从官方github仓库下载文件，然后从本地读取 [解决tsfresh下载robot_execution_failures数据集(host=‘raw.githubusercontent.com‘, port=443)的问题_liuxiaoru_的博客-CSDN博客_robot_execution_failures](https://blog.csdn.net/liuxiaoru_/article/details/120026576)