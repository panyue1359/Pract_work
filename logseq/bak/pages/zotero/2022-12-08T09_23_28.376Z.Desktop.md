---
title: zotero
---

- zotero/官网
  collapsed:: true
	- [中文版官方文档（部分）](https://www.zotero.org/support/zh/zotero_data)
	  id:: 62122f61-24b8-4799-b821-9c65d7e8baf1
		- 数据目录下的zotero.sqlite文件是最重要的文件，它包含了文献库中大多数内容：条目元数据，笔记，标签（关键字）等等。
	- [Recent Discussions - Zotero Forums](https://forums.zotero.org/discussions)
- zotero/安装
  collapsed:: true
	- [dev builds [Zotero Documentation]](https://www.zotero.org/support/dev_builds)
- zotero/基础
  id:: 627479e3-832e-41d8-aed1-0b663dced482
	- ((63155198-b133-43a0-a0ec-5df05928606d))：zotero中外文名需要按提示刻意颠倒，把名放后面，把姓放前面
	  id:: 631551ae-2796-490d-a858-c4e717b1c44b
	- 不同类型参考文献
	  collapsed:: true
		- 图书版本只填数字
	- 红色搜索框（Add Citation dialog box）
	  collapsed:: true
		- 按空格启动搜索，按回车确认条目
		- 点击确认的条目或者按Ctrl+方向键下可插入更多内容（如页码、章节等）：[Four-digit page numbers in Word plugin - Zotero Forums](https://forums.zotero.org/discussion/comment/404540#Comment_404540)
	- ((486cf681-e808-4636-95e5-21857e2cc00e))
	  collapsed:: true
		- 使用支持中英文混排的csl文件： [国标格式](https://zhuanlan.zhihu.com/p/278112406?utm_source=wechat_session)
		- 设置中文文献的语言为zh，英文文献的语言为en：可使用插件 ((e52361cc-c5ec-4a10-8eb8-73f2c19f6566)) 快速设置
	- 同步账号
		- storage file储存在名为storage的子目录中，这里面包含您的文件附件，例如PDF文件，网页快照，音频文件或是其他任何您导入的文件（注意：通过链接方式添加的附件不会被复制到该子目录下。）
		- linked file储存在其他位置，zotero只保留链接（链接关系属于data而不是file）
		- 默认只同步storage file，包括webdav
		- storage file在zotero中被删除，webdav中也会删除
		- teracloud的直接复制文件夹路径会包含\\v2\，必须用\https://seto.teracloud.jp/dav/+文件夹路径，否则会报错HTTP 400
	- 抓取元信息
		- 从 [Zotero translator中文网页抓取插件](https://github.com/l0o0/translators_CN) 下载更多网页编译器，可以从当当、京东、文津抓取图书信息，可以从知乎保存更详细元信息和文章内容
		- obsidian社区建议使用道格学社的translator替换上面的CN库  [目前知识管理存在的一些难点（持续更新中） - 每日闲聊 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/7486/2)、[gezhongran/DougSociety: 道格学社官方仓库](https://github.com/gezhongran/DougSociety)
	- ((a7c8eecf-a432-45a2-a58b-50dd7d40ad6c))
	  id:: 633103b5-2250-457f-b76e-e1128be1898a
		- 自定义CSL步骤：访问网站[Find and edit CSL citation styles](https://editor.citationstyles.org/about/)->选择样式或者上传CSL文件->左侧栏STYLE INFO是CSL文件的描述，包括制作者、日期等；INLINE CITATION是文内引用格式；BIBLIOGRAPHY是参考文献目录样式；**MACROS是对不同元数据的处理方式，本质上是一组IF...THEN规则，是CSL的核心**；ADVANCED是以上所有信息的汇总->确定条目类型->在[CSL参数表](https://aurimasv.github.io/z2csl/typeMap.xml#cslVar-issued)查找对应条目类型（UI Label）的元数据类型（Zotero field）及变量类型（CSL field），例子如下->保存一次以后需要刷新才能再次保存（刷新不会丢内容）
			- 期刊文章属于article，书籍属于book，会议论文属于paper-conference，硕博士论文属于thesis，网页属于webpage
			- 期刊文章需要获取期刊名Publication（对应变量container-title），出版年Date（对应变量issued），标题Title（对应变量title和title-short）
			- 书籍需要获取书籍作者Author（对应变量author）
			- 会议论文需要获取会议名称Conference Name（对应变量event-title）
			- 硕博士论文需要获取毕业学校University（对应变量publisher）
		- 参考文献
		  collapsed:: true
			- [四步实现自定义 Zotero 参考文献格式 - 知乎](https://zhuanlan.zhihu.com/p/31326415)
			- [Zotero + CSL编辑器，自定义文献引用格式，创建PPT中的短文献引用 - 知乎](https://zhuanlan.zhihu.com/p/185026280)
			- [CSL 1.0.2 Specification — Citation Style Language 1.0.1-dev documentation](https://docs.citationstyles.org/en/stable/specification.html)
			- [其他文献管理软件的CSL格式](https://github.com/bwiernik/zotero-tools)
		- 使用自带编辑器：[dev:citation styles:style editing step-by-step [Zotero Documentation]](https://www.zotero.org/support/dev/citation_styles/style_editing_step-by-step)
			- 使用自带样式编辑器修改后务必修改<id>行的名称，然后另存为
	- 添加搜索引擎：[zotero 添加文献搜索引擎实现期刊分区的快速查询 - wybert - 博客园](https://www.cnblogs.com/wybert/p/14225202.html)
	- [科学网-Zotero: 关于一些疑问-李楠的博文](http://wap.sciencenet.cn/blog-41796-21585.html?mobile=1)：关于zotero的软件定位等基础问题
	- 备份
	  collapsed:: true
		- 在数据目录中还会包含其他文件：zotero.sqlite,bak（该文件是zotero.sqlite文件的自动备份，它是在关闭Zotero客户端时生成的，且该文件在最近的12小时内是没有更新的）
		- 同步并不能很好地替代备份：Zotero服务器仅存储您的库的最新版本
		- 我们建议您使用备份实用程序，而不是仅备份Zotero数据库，该实用程序会定期自动将整个硬盘驱动器备份到外部设备。
		- 如果要专门备份Zotero数据，请找到Zotero数据，关闭Zotero，然后将数据目录（整个目录，包括zotero.sqlite和storage以及其他子目录）复制到备份位置
	- [Zotero｜推荐几个非常不错的Rss订阅源 - 知乎](https://zhuanlan.zhihu.com/p/113487194)
	- [Zotero: add a history feature for paper viewing 为Zotero添加论文跳转历史记录功能 - sonictl - 博客园](https://www.cnblogs.com/sonictl/p/13124264.html)
	- [Zotero 使用技巧_M2kar的专栏-CSDN博客](https://blog.csdn.net/still_night/article/details/106521186)：同步，修改默认PDF命名，打标签，打星，sci-hub支持
	- [长按Ctrl显示条目所属文件夹](https://blog.csdn.net/u011092188/article/details/78746485)
	- ((d1ecc318-3166-4d44-acb9-4e59fe995c42))
	  id:: 6248105c-08c3-48a1-9a98-81780b33d443
	  collapsed:: true
		- [不同文件格式互转同时保持citations live](https://www.zotero.org/support/kb/moving_documents_between_word_processors)
		  id:: 62490495-dd79-4895-a56e-72b147169f54
	- Delete是从分类中删除条目，此时条目属于未分类，而不是回收站；Shift+Delete是删除条目
- zotero/问题
- zotero/插件
	- Better BibTeX
	  collapsed:: true
		- [Citation Keys :: Better BibTeX for Zotero](https://retorque.re/zotero-better-bibtex/citing/)
		- [Zotero Better BibTex选项配置推荐(个人) - 知乎](https://zhuanlan.zhihu.com/p/458340252)
		- Citation Key格式说明：[Customize the citation key generator - JabRef](https://docs.jabref.org/setup/citationkeypatterns#default-citation-key-pattern)
		- 由于中文没有空格，作者推荐使用如下格式：[language=ja] [Authors:kuromoji:select=1,2:transliterate=ja][Title:kuromoji:skipwords:select=1,2:nopunct:transliterate=ja][year] | [language=zh] [Authors:jieba:select=1,2:transliterate=zh][Title:jieba:skipwords:select=1,2:nopunct:transliterate=zh][year] | [authEtAl][shorttitle2_2][year]，需要开启enable jieba
	- [Zotero IF Pro](https://github.com/qnscholar/zotero-if-pro)：付费66元
	  id:: odfeOBV8P
	  collapsed:: true
	  id:: e52361cc-c5ec-4a10-8eb8-73f2c19f6566
		- ((0d316331-59bc-42be-9322-4ec893922543))
	- [Zutilo](https://github.com/wshanks/Zutilo)自定义快捷键插件
	- Zotfile文件管理相关插件
	  collapsed:: true
		- zotero 本身就允许附件和数据分别储存，在首选项-高级-文件和文件夹中可以设置，zotfile 只是在此基础上附加了一些功能，无法改变文件夹内的微观结构（一个条目一个文件夹），仍然不便于手动查找。
		- Source Folder for Attaching New Files
		  collapsed:: true
			- [网友](https://zhuanlan.zhihu.com/p/104848524)：““举个例子：我通过zotero浏览器插件添加了一篇文献，Zotero自动抓去了文献条目信息，但是却没法自动下载附件，这时候我手动将附件下载到我指定的“Source Folder”文件夹内部，然后再条目上右键选择“Attach New File”，ZotFile就会自动从“Source Folder”文件夹读取我最新下载的附件追加到条目，然后自动转移到我所设定的需要转移的文件夹内部。”
		- Custom Location：这个对应zotero高级设置中的相对路径，只是增加了生成子文件夹功能
- zotero/助手
	- Zotero Citation Picker for Windows
	  id:: y5anIHn1u
	  id:: df93c1de-7efd-437e-a764-89f2a45a188c
		- 全局调用zotero搜索并导出多种样式
		- 官网：[boan-anbo/Zotero-Citation-Picker-for-Windows: An AHK-based application to search and pick Zotero citations on Windows.](https://github.com/boan-anbo/Zotero-Citation-Picker-for-Windows)
		- 点击选中的文献或者按Ctrl+向下键可以继续向该条目增加元信息，在选择元信息时可以快速按字母键选择要增加的元信息，比如快速按下ch可以跳转到Chapter