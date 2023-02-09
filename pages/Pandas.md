- ## 官网
- [pandas documentation — pandas 1.4.1 documentation](https://pandas.pydata.org/docs/)
- ## 基础
- Dataframe转换为ndarray：[.as_matrix()的作用_琦度的博客-CSDN博客_as_matrix](https://blog.csdn.net/weixin_41884148/article/details/88783328)
  collapsed:: true
	- .as_matrix()方法快要被淘汰了
	- 建议使用df.values直接转换
- 按条件筛选行或者列
  collapsed:: true
	- drop和isin都只能按==条件删除，不能直接处理<>号
	  id:: 61776918-0513-469d-9ce8-382eee4feafb
	- [巧用DataFrame布尔索引的方法删除特定行或列_sigtem的博客-CSDN博客_dataframe布尔索引](https://blog.csdn.net/sigtem/article/details/81735242)
	- [pandas.dataframe中根据条件获取元素所在的位置（索引）_AI_盲的博客-CSDN博客_pandas找到元素的位置](https://blog.csdn.net/xwd18280820053/article/details/72614734/)
- 索引分片索引
  collapsed:: true
	- [在Pandas DataFrame中处理行和列](https://www.imangodoc.com/577.html)
	  collapsed:: true
		- df.loc[索引i]返回单行，loc\[[索引i,索引j]]返回多行
		- df[表头i]返回单列，df\[[表头i,表头j]]返回多列
- 删除行或列
  collapsed:: true
	- [在Pandas DataFrame中处理行和列](https://www.imangodoc.com/577.html)
	- [巧用DataFrame布尔索引的方法删除特定行或列_sigtem的博客-CSDN博客_dataframe布尔索引](https://blog.csdn.net/sigtem/article/details/81735242)
- 增加行或列：[pandas如何新增列？4种方式超级简单](https://baijiahao.baidu.com/s?id=1719917154971656272&wfr=spider&for=pc)
  collapsed:: true
	- 直接赋值：df.loc[:,列名称]=xxx，xxx是""表示赋空值，直接修改原表
	- apply：df.loc[:,列名称]=df.apply(xxx)，可进行运算，直接修改原表
	- assign：df.assign(列名称=xxx)，返回新表，注意列名称不能有括号
- 修改某列的值
  collapsed:: true
	- [将pandas DataFrame中的每个数值设为负数-python黑洞网](https://www.pythonheidong.com/blog/article/190598/d03970eaab31c5d82f65/)
	- ``` python
	  df2=copy.copy(df1)
	  df2['key']=-df1['key']
	  
	  ```
- 自动推断日期格式：[pd.to_datetime我吹爆！太强了_dropna()的博客-CSDN博客](https://blog.csdn.net/weixin_43491947/article/details/108842631?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-2.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-2.pc_relevant_default&utm_relevant_index=4)
- 日期格式转字符串：[python pandas 中datetime和string互相转化_richard_18的博客-CSDN博客_pandas 时间转字符串](https://blog.csdn.net/richard_18/article/details/80720572)
- 一维DataFrame转Series（取DataFrame某列作为Series索引）
  id:: HeF-ybsIJ
  id:: 4a5212de-5233-40ad-a363-76e5ad7ae0ba
	- ``` python
	  test = pd.Series(bar["content column"].values, index=bar["index column"], name="name")
	  
	  ```
- 求固定间隔的平均值：[使用Pandas的resample函数处理时间序列数据的技巧 - 知乎](https://zhuanlan.zhihu.com/p/277364792)
- 空的DataFrame不能用形如df["column name"]=a的方法直接赋值
- 修改列名称：df.rename(columns={"a":"A"}, inplace=True)
- [在dataframe添加1行（首行，或者尾部），且不覆盖](http://t.csdn.cn/Qfutq)
- 分段统计：[Python3 pandas库(17) 分段函数及cut() - 曹骥的文章 - 知乎](https://zhuanlan.zhihu.com/p/30638406)
- [中文导出csv乱码](http://t.csdn.cn/lvzHf)：导出时增加 encoding="utf_8_sig"
- [多列拼接成一列](https://www.jianshu.com/p/c1d99d14603d)
- 筛选以及合并值相同的行
  id:: 621b8cf7-dc84-4490-af7e-76fd64dbe728
  collapsed:: true
	- 小心： ((4b592c6e-926e-4b30-9e03-6943a53156b3))
	- Groupby方法
	  id:: 621b8d84-4577-46f5-bb8b-3fbc27f247fa
	  collapsed:: true
		- 示例
		  
		  ``` python
		  s = 'Al13Cr21.7Cu21.7Ni21.7Ti21.7'
		  s_list=[''.join(list(g)) for k, g in groupby(s, key=lambda x: x.isalpha())]
		  s_dict={}
		  for i in range(0,len(s_list),2):
		  s_dict[s_list[i]]=s_list[i+1]
		  """
		  lambda x: x.isalpha() 表示判断x是否为英文字母，返回bool
		  groupby(s, key=func)表示对迭代器s的每一个元素根据func提取出分组依据（key）
		  这个例子中key是每一个字符是否为英文字母，因此第一组是True：A，l，第二组是False：1，3，后面以此类推
		  ''.join(list(g))表示将一组g的元素不加间隔的拼接起来，成为一个元素
		  """
		  
		  ```
		- [pandas怎么筛选出多列值相同的行？ - 知乎](https://www.zhihu.com/question/404425505/answer/1314197111)
		- [pandas的DataFrameGroupBy转换为DataFrame_weixin_33695082的博客-CSDN博客](https://blog.csdn.net/weixin_33695082/article/details/92642867)
		- 解决 拆分字母和数字混杂的数据 问题
- 查找Series的9分位数：y.sort_values().quantile(0.9) [pandas中quantile函数浅解_Accelerating的博客-CSDN博客_pandas quantile](https://blog.csdn.net/Accelerating/article/details/116048021)
- 排序
  collapsed:: true
	- df.sort_values()按值大小排序
	- df.sort_index()按索引值排序
	- df.argsort()按值从小到大的顺序返回对应的索引值
- ## 问题
- A value is trying to be set on a copy of a slice from a DataFrame
  collapsed:: true
	- 避免使用df["column name"][index]，建议使用df.loc[index,"column name"]