- Python/官网：[Our Documentation | Python.org](https://www.python.org/doc/)
  public:: true
  collapsed:: true
- [[Python/安装]]
- Python/基础
  collapsed:: true
	- Python/基础/教程
		- 遍历对象
		  id:: 6154715e-7844-4cb1-9c25-c7726eb2e278
		  collapsed:: true
			- [遍历输出对象的属性值_Great haste makes great waste-CSDN博客](https://blog.csdn.net/xiaodongxiexie/article/details/65648188)
			- [python动态获取对象的属性和方法 （转载） - zh1164 - 博客园](https://www.cnblogs.com/zh1164/p/6031464.html)
			- 使用dir遍历对象属性和方法，例如for method in dir(comp1_data)
			- getattr返回属性的值，方法则返回一个对象.方法，如要读取值需要加括号
			- 如果打印对象.方法()的值得到数值表示，需要格式化输出 print('%s'%foo_X)
		- \#-*- coding: UTF-8 -*-的作用
		  collapsed:: true
			- Python默认是以ASCII作为编码方式的，如果在自己的Python源码中包含了中文（或者其他的语言，比如小日本的日语……），此时即使你把自己编写的Python源文件以UTF-8格式保存了；但实际上，这依然是不行的。解决方法：在源码的第一行添加以下语句：\# -*- coding: UTF-8 -*-  
			  或者 
			  \#coding=utf-8（没有正斜杠）[# -*- coding: UTF-8 -*-_追随光、成为光的博客-CSDN博客_coding: utf-8](https://blog.csdn.net/Stillboring/article/details/105890415)
		- [最近要给单位里的员工培训Python，选哪本教材合适？_申龙斌的程序人生-CSDN博客](https://blog.csdn.net/slofslb/article/details/122535986?spm=1001.2014.3001.5501)
		- [Python基础教程，Python入门教程（非常详细）](http://c.biancheng.net/python/)
		- 装饰器
		  collapsed:: true
			- [详解python中@的用法 - python大师 - 博客园](https://www.cnblogs.com/daniumiqi/p/12162192.html)
			- [Python @函数装饰器及用法（超级详细）](http://c.biancheng.net/view/2270.html)
		- [Python ceil函数](https://www.runoob.com/python/func-number-ceil.html)：除法如果有余数则加一，否则不变
		- 列表推导
		  collapsed:: true
			- [从字典列表中获取平均值 - 问答 - Python中文网](https://www.cnpython.com/qa/51568)
			- [python列表推导式中使用if-else_jasonLee的博客-CSDN博客_python列表推导式else](https://blog.csdn.net/jasonLee_lijiaqi/article/details/79305779)
			  collapsed:: true
				- 只有if：[_ for _ in line if xxx]
				- if else：[exp if xxx else exp2 for _ in line]
			- [请问python的if后面直接跟变量是什么意思_百度知道](https://zhidao.baidu.com/question/1610480506685656747.html)：如果if后面直接跟变量, 即变量不是None为True, 是None为假.
		- 连接字符串：str.join(sequence)表示用str连接sequence这一组字符串
		- 进度条：[Python 实现进度条的六种方式 - ''竹先森゜ - 博客园](https://www.cnblogs.com/zhuminghui/p/13985315.html)
		  
		  
		  ``` python
		  import sys
		  import time
		  #开始计时
		  start = time.perf_counter()
		  flag = True #标记刚达到1%的时间，以便估计总时间
		  for i in range(n):
		    dur = time.perf_counter() - start
		    if i*100//1000==1 and flag:
		      print("Calculation progress: {}%: {:.2f}s".format(i*100//n,dur), "▋" * ((i*100//n) // 2))
		      flag=False  
		    else:
		      print("\r", end="")
		      print("Calculation progress: {}%: {:.2f}s".format(i*100//n,dur), "▋" * ((i*100//n) // 2), end="")
		      sys.stdout.flush()
		      time.sleep(0.05)
		  
		  ```
	- Python/基础/报错
		- 导入文件时报错，/b被转义为x08
		  collapsed:: true
			- [python防止字符串转义 - sgggr - 博客园](https://www.cnblogs.com/sggggr/p/11874902.html)
		- 读取数据错误：'gbk' codec can't decode byte
			- ['gbk' codec can't decode byte 0xae 解决方法_xzy565143480的博客-CSDN博客](https://blog.csdn.net/xzy565143480/article/details/89976706)
		- 安装库错误：No module named 'pip._internal'
			- [ModuleNotFoundError: No module named 'pip._internal' , pip 无法下载软件 解决办法_One Way的博客-CSDN博客](https://blog.csdn.net/wangweiwells/article/details/88374070)，使用方法1解决
		- 相同的数据不相等？
		  id:: JwU5jwOIv
		  id:: 4b592c6e-926e-4b30-9e03-6943a53156b3
			- ![merge_data_error_1651302014639_0.jpg](../assets/merge_data_error_1651302014639_0_1667482660018_0.jpg)
			- 原因：浮点数计算精度不足导致数据看起来相同，实际不等
			- 方法1：Decimal函数，缺点是该函数[只能处理字符串](https://www.xz577.com/j/44961.html)，因此只能保证导入时相等的数据相等
			- 方法2：写一个函数[查找替换近似行](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.testing.assert_frame_equal.html)，然后使用DataFrame的groupby方法合并
- Python/编辑器：[[Jupyter Notebook]]
- [[Python/Library]]