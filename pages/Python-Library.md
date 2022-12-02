---
title: Python/Library
---

- Python/Library/基础
  public:: true
  collapsed:: true
	- Python/Library/基础/安装
	  collapsed:: true
		- [Python Extension Packages for Windows - Christoph Gohlke](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy)第三方库下载网站
		- [python、pip、whl安装和使用 - konglingbin - 博客园](https://www.cnblogs.com/klb561/p/9271322.html)
	- Python/Library/基础/问题
	  collapsed:: true
		- [关于 pip has no attribute pep425tags 的解决_hyqiyu的博客-CSDN博客_pep425tags](https://blog.csdn.net/qq_40772189/article/details/106455315)
		- [有关pip安装出现的问题(报：HTTPSConnectionPool……错误)，及解决方案，亲测有效！！！_QvQWangXiaoBao的博客-CSDN博客](https://blog.csdn.net/QvQWangXiaoBao/article/details/111145854)
		  collapsed:: true
			- 临时更换源 pip install xxx -i \https://pypi.tuna.tsinghua.edu.cn/simple（注意删除地址前面的反斜杠）
- [[Python/Library/Pandas]]
- [[Python/Library/NumPy]]
- [[Python/Library/Matplotlib]]
- Python/Library/cvxopt：二次规划库
  collapsed:: true
	- [Python之CVXOPT模块 - 简书](https://www.jianshu.com/p/df447c3e4efe)：先卸载numpy，然后用pip install 安装numpy和cvxopt
	- mosek：二次规划求解器，需要[额外安装](https://hyp.is/hUX3VDQIEeyrDKdMHffprw/cvxopt.org/userguide/coneprog.html)
- [[Python/Library/优化算法库]]
- Python/Library/机器学习
  id:: XaIrAxjKD
  collapsed:: true
  id:: 9baa0f1a-1102-4ee5-aa94-6a68e36943cd
	- [[AutoML]]
	- 支持机器学习全流程的库
	  id:: -9Rth9-7y
	  collapsed:: true
	  id:: 12723764-b137-4fbd-8029-d0c7b36d0e4a
		- [[sklearn]]
		- [[pytorch]]
		- [Weka 3](https://www.cs.waikato.ac.nz/ml/weka/index.html)：一款开源机器学习软件，国内不可用
	- 机器学习/模型
		- [[MARS]]
		- [[spyct]]
		  id:: 6220bebc-c39a-4468-8629-0363cc695c01
- Python/Library/不确定性量化
  collapsed:: true
	- [IBM/UQ360: Uncertainty Quantification 360 (UQ360)](https://github.com/IBM/UQ360)
	  collapsed:: true
		- IBM不确定性量化python包，支持windows，需要python 3.7
	- [simetenn/uncertainpy: Uncertainpy](https://github.com/simetenn/uncertainpy)
		- 不确定性量化和敏感性分析python包
		- [Theory — Uncertainpy 1.2.3 documentation](https://uncertainpy.readthedocs.io/en/latest/theory.html)
		- [SALib](https://github.com/SALib/SALib)：python [[sensitivity measure库]]，可做delta method
- Python/Library/Materials Science
  collapsed:: true
	- [Atomic Simulation Environment — ASE documentation](https://wiki.fysik.dtu.dk/ase/index.html)：可视化原子模拟库，可以画相图和晶胞