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