<<<<<<< HEAD
=======
- ## 安装
- Anaconda自带
- ## 基础
- 删除不想要的kernel
	- 使用`jupyter kernelspec list`查看所有kernel，然后使用`jupyter kernelspec remove kernel名称`删除
	- 如果list和jupyter notebook中的kernel对不上，那么通过list确认kernel所在的文件夹，手动删除不想要的kernel，效果一样 [r - remove kernel on jupyter notebook - Stack Overflow](https://stackoverflow.com/questions/42635310/remove-kernel-on-jupyter-notebook)
- 修改默认启动目录
  id:: 627479e8-bf1c-4bec-ad13-087f0971fb5d
  collapsed:: true
	- “首先找到Jupyter Notebook的快捷方式，右键如下图。“目标”中最后一个参数默认是%USERPROFILE%，就是默认启动目录。” 将其替换为自定义目录即可，不用加引号 [Windows下更改Jupyter Notebook默认启动目录_Sin_Geek成长の迹-CSDN博客](https://blog.csdn.net/sin_geek/article/details/78172132?utm_source=blogxgwz1)
	- 参考 [修改jupyter notebook的默认路径_small~白菜的博客-CSDN博客_jupyter notebook修改默认打开位置](https://blog.csdn.net/woniuyc/article/details/121986086) 右键快捷方式属性，删除"%USERPROFILE%/"及前面的空格，在jupyter_notebook_config.py中配置路径（单斜杠变双斜杠）
- 添加kernel
  id:: 63aa5eef-850d-4ba9-9250-6502a90f6d24
	- ``` python
	  pip install ipykernel
	  python -m ipykernel install --user --name pyamm --display-name "pyamm"
	  ```
- markdown
  collapsed:: true
	- 可以为标题自动生成目录，见在[jupyter notebook 中的markdown编辑时，如何取消自动生成标题的序号？ - 暮羽的回答 - 知乎](https://www.zhihu.com/question/267934067/answer/992371756)
- 远程使用
  collapsed:: true
	- 远程使用Jupyter Notebook
		- 教程：[远程访问Windows 10中Jupyter Notebook的配置方法 - 哔哩哔哩](https://www.bilibili.com/read/cv9010361)
			- 必须手动输入Enter password和Verify password（不显示结果是正常情况），复制粘贴会报错Invalid credentials
		- 公网访问
			- 参考 [用zerotier实现内网穿透 - 知乎](https://zhuanlan.zhihu.com/p/422171986)，安装win10版和安卓版
			- 手机通过浏览器访问jupyter显示没有互联网连接
				- 复制ZeroTier分配给电脑的ip地址，替换"jupyter_notebook_config.py"中的ip地址，可以访问
	- 手机只适合查看，编辑不如电脑方便
- 多人协作
  collapsed:: true
	- 推荐Deepnote [Jupyter notebook 和 Deepnote, Colaboratory的使用体验_正在努力变富有的Dolores的博客-CSDN博客](https://blog.csdn.net/caicau/article/details/118937955)
	- 中北企业邮箱可建立教育版
- ## 问题
- 如果Jupyter Notebook闪退，可能是找不到根目录
- jupyter notebook出现“500:Internal Server Error”问题：[jupyter notebook解决500:Internal Server Error](https://cloud.tencent.com/developer/article/1757774)
  collapsed:: true
	- ``` python
	  pip install --upgrade --user nbconvert
	  ```
	- 如果报错“ImportError: cannot import name 'secure_write'”，则
	  
	  ``` python
	  pip install --upgrade jupyter_client
	  ```
- 无法定位程序输入点？PyWinObject FromULARGE INTEGER@QYAPEAU_object@@AEBTULARGE_INTEGER@@@Z于动态链接库pywintypes36.dll上：[成功解决python.exe 无法找到程序入口 无法定位程序输入点_一个处女座的程序猿-CSDN博客](https://blog.csdn.net/qq_41185868/article/details/103557501)
  collapsed:: true
	- "E:\\Panyue\\Programs\\Anaconda3\\envs\\pysk\\Lib\\site-packages\\pywin32_system32"和\"E:\\Panyue\\Programs\\Anaconda3\\envs\\pysk\\Library\\bin找到文件pywintypes36.dll"，删除后者，有效
- 切换kernel，显示Dead kernel
  collapsed:: true
	- No module named 'defusedxml'，使用pip下载defusedxml解决
	- cannot import name 'ensure_dir_exists'
		- 网上多数建议更新jupyter_core and jupyter_client，无效
		- 按照 [TensorFlow环境下安装jupyter notebook后，cmd打开出现cannot import name 'ensure_dir_exists' - 灰信网（软件开发博客聚合）](https://www.freesion.com/article/189286157/)提示，降低jupyter_core版本，无法降低、
		- [python - ImportError: cannot import name 'ensure_dir_exists' - Stack Overflow](https://stackoverflow.com/questions/48372019/importerror-cannot-import-name-ensure-dir-exists)：pip install jupyter-core --upgrade，安装了一个pywin32==301版本，导致无法打开终端，卸载后可以打开，但无法打开界面
		- 按照 [解决jupyter 中ModuleNotFoundError: No module named xxx_吃胡萝卜的鳄鱼的博客-CSDN博客_jupyter modulenotfounderror](https://blog.csdn.net/qq_37135484/article/details/97242788?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1.no_search_link&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1.no_search_link)提示，安装cufflinks包
		- 卸载jupyter_core以后可以打开，提示Terminals unavailable
	- jupyter画图不显示中文：[jupyter画图不显示中文，恶心人的matplotlib画图不显示中文问题解决办法汇总](https://blog.csdn.net/j18233653274/article/details/89179461)
		- 方法一
		  ``` python
		  import matplotlib.pyplot as plt
		  plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
		  plt.rcParams['axes.unicode_minus']=False #用来正常显示负号
		  ```
		- 方法二
		  
		  ``` python
		  import matplotlib as mpl
		  mpl.rcParams['font.sans-serif'] = ['KaiTi']
		  mpl.rcParams['font.serif'] = ['KaiTi']
		  ```
		- 方法三
		  
		  ``` python
		  import matplotlib.pyplot as plt
		  plt.rc('font', family='SimHei', size=13)
		  ```
>>>>>>> 7394450ff3f1d3d6e5ef95d10c09eb98f8833ef9
