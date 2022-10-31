---
title: Python/安装
---

- Python/安装/教程
	 - 打开开始菜单直接输入path，选择“编辑账户的环境变量”可以直接打开环境变量配置

	 - [python与anaconda安装（先安装了python后安装anaconda，基于python已存在的基础上安装anaconda）——逼死强迫症、超详解_NBS的博客-CSDN博客](https://blog.csdn.net/qq_43529415/article/details/100847887)

	 - [Anaconda 查看、添加、删除 安装源_David_jiahuan的博客-CSDN博客](https://blog.csdn.net/david_jiahuan/article/details/104544957?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_title-2&spm=1001.2101.3001.4242)

	 - [anaconda python 版本对应关系_茶佬牛逼-CSDN博客_anaconda python版本](https://blog.csdn.net/yuejisuo1948/article/details/81043823)

	 - Anaconda更换镜像源
		 - [Anaconda更换镜像源方法_SueMagic-CSDN博客_anaconda修改镜像源](https://blog.csdn.net/SueMagic/article/details/85332457)，这个方法会报错 PackagesNotFoundError: The following packages are not available from current channels

		 - [Anaconda配置清华镜像源_克豪的博客-CSDN博客_anaconda 清华镜像](https://blog.csdn.net/qq754772661/article/details/107174824/)，这个更好

- Python/安装/报错
id:: 62484cb6-dc55-4c51-981a-d76326edbe5c
	 - 重装时提示 failed to create anacoda menu
collapsed:: true
		 - [windows安装anaconda 报错failed to create anacoda menue？ - 知乎](https://www.zhihu.com/question/42263480) 建议手动配置

	 - 使用conda终端下载scikit-learn，报错 CondaError: Cannot link a source that does not exist.
id:: 614c8bf9-df87-44b8-95a7-349541603042
		 - [建议升级conda](https://stackoverflow.com/questions/54024671/error-while-installing-tensorflow-in-conda-environment-condaerror-cannot-link)：conda update -n root conda

	 - 安装完成发现没有Scripts和Library文件夹
collapsed:: true
		 - [Anaconda3安装后缺失大量文件，没有scripts、library等目录，conda list报错（管理员模式安装也无效）_yuukai的博客-CSDN博客](https://blog.csdn.net/yuukai/article/details/119890159)，建议删除C:\Users\Administrator\下的.condarc文件和.conda文件夹，失败

		 - [Anaconda安装（缺少大量文件）_cang_ming的博客-CSDN博客](https://blog.csdn.net/cang_ming/article/details/106065730)，使用旧版安装包，失败

		 - 卸载python3.6.0后重装，文件完整，使用Listary启动CMD窗口显示“ 'python' 不是内部或外部命令，也不是可运行的程序或批处理文件。”

		 - 下载最新版Anaconda3，安装在D盘，显示“[WinError 123] 文件名、目录名或卷标语法不正确”

		 - 下载2021年版本Anaconda3，同样出错

		 - 下载4.3.1版本，成功

	 - Anaconda无法启动
collapsed:: true
		 - 结合 [Anaconda闪退的问题AttributeError: 'str' object has no attribute 'get'_tanmx219的博客-CSDN博客](https://blog.csdn.net/tanmx219/article/details/88069375) 评论区的做法，我把anaconda_api.py的VSCODE_ENDPOINT处的网站由“https://vscode-update.azurewebsites.net/api/update”改成了“https://update.code.visualstudio.com/api/update”，可以正常运行

		 - 还有一种方法是换源 [Anaconda安装及更新失败解决方式和conda 连接超时_u014330763的博客-CSDN博客](https://blog.csdn.net/u014330763/article/details/79994593)

		 - 按照[Anaconda Navigator 一直loading application 无法启动 - 知乎](https://zhuanlan.zhihu.com/p/364935316)修改，无效

		 - 按照[Anaconda安装及更新失败解决方式和conda 连接超时_u014330763的博客-CSDN博客](https://blog.csdn.net/u014330763/article/details/79994593)修改.condarc的地址，有效

	 - 
