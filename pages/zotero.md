- ## 官网
- [中文版官方文档（部分）](https://www.zotero.org/support/zh/zotero_data)
  id:: 62122f61-24b8-4799-b821-9c65d7e8baf1
  collapsed:: true
	- 数据目录下的zotero.sqlite文件是最重要的文件，它包含了文献库中大多数内容：条目元数据，笔记，标签（关键字）等等。
- [Recent Discussions - Zotero Forums](https://forums.zotero.org/discussions)
- [dev builds [Zotero Documentation]](https://www.zotero.org/support/dev_builds)
- ## 基础
  id:: 627479e3-832e-41d8-aed1-0b663dced482
- zotero中外文名需要按提示刻意颠倒，把名放后面，把姓放前面
  id:: 631551ae-2796-490d-a858-c4e717b1c44b
- 图书版本只填数字
- 红色搜索框（Add Citation dialog box）
	- 按空格启动搜索，按回车确认条目
	- 点击确认的条目或者按Ctrl+方向键下可插入更多内容（如页码、章节等）：[Four-digit page numbers in Word plugin - Zotero Forums](https://forums.zotero.org/discussion/comment/404540#Comment_404540)
	- 有时候搜索框不会置顶显示，需要在“首选项”->“高级”->“设置编辑器”中查找“extensions.zotero.integration.keepAddCitationDialogRaised”项，如果是false，需要右键，选择“toggle”
- 同步账号
  collapsed:: true
	- storage file储存在名为storage的子目录中，这里面包含您的文件附件，例如PDF文件，网页快照，音频文件或是其他任何您导入的文件（注意：通过链接方式添加的附件不会被复制到该子目录下。）
	- linked file储存在其他位置，zotero只保留链接（链接关系属于data而不是file）
	- 默认只同步storage file，包括webdav
	- storage file在zotero中被删除，webdav中也会删除
	- teracloud的直接复制文件夹路径会包含\\v2\，必须用\https://seto.teracloud.jp/dav/+文件夹路径，否则会报错HTTP 400
- 抓取元信息
  collapsed:: true
	- 从 [Zotero translator中文网页抓取插件](https://github.com/l0o0/translators_CN) 下载更多网页编译器，可以从当当、京东、文津抓取图书信息，可以从知乎保存更详细元信息和文章内容
	- obsidian社区建议使用道格学社的translator替换上面的CN库  [目前知识管理存在的一些难点（持续更新中） - 每日闲聊 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/7486/2)、[gezhongran/DougSociety: 道格学社官方仓库](https://github.com/gezhongran/DougSociety)
- 添加搜索引擎
  collapsed:: true
	- 查找engines.json文件，添加搜索引擎片段，重启zotero生效
	- 自用
	  ``` json
	  	{
	     		 "_name": "豆瓣读书",
	     		 "_alias": "豆瓣读书",
	     		 "_description": "豆瓣读书",
	     		 "_icon": "https://www.douban.com/favicon.ico",
	     		 "_hidden": false,
	     		 "_urlTemplate": "https://search.douban.com/book/subject_search?search_text={z:title}&cat=1001",
	     		 "_urlParams": [],
	     		 "_urlNamespaces": {
	       			 "z": "http://www.zotero.org/namespaces/openSearch#",
	       			 "": "http://a9.com/-/spec/opensearch/1.1/"
	     		 },
	     		 "_iconSourceURI": "https://www.douban.com/favicon.ico"
	    	},
	    	{
	  		"name": "Amazon.com",
	  		"alias": "Amazon.com Search",
	  		"icon": "http://www.amazon.com/favicon.ico",
	  		"_urlTemplate": "http://www.amazon.com/gp/search/ref=sr_adv_b/?search-alias=stripbooks&unfiltered=1&field-author={rft:aufirst?}+{rft:aulast?}&field-title={rft:title}&tag=httpwwwdig0e7-20",
	  		"description": "Look up books on Amazon.com",
	  		"hidden": false,
	  		"_urlParams": [],
	  		"_method": "GET",
	  		"_urlNamespaces": {
	  			"rft": "info:ofi/fmt:kev:mtx:book",
	  			"xmlns": "http://a9.com/-/spec/opensearch/1.1/"
	  		},
	  		"_iconSourceURI": "http://www.amazon.com/favicon.ico"
	  	},
	  
	  ```
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
- Delete是从分类中删除条目，此时条目属于未分类，而不是回收站；Shift+Delete是删除条目
- 建立多个独立的库：只能通过多账号解决，比较复杂 [Creating a second personal library - Zotero Forums](https://forums.zotero.org/discussion/comment/338706#Comment_338706)
- ## 插件和助手
- 常用插件列表 [Zotero中文社区](https://zotero-chinese.gitee.io/zotero-plugins/#/)
- Better BibTeX
  collapsed:: true
	- [Citation Keys :: Better BibTeX for Zotero](https://retorque.re/zotero-better-bibtex/citing/)
	- [Zotero Better BibTex选项配置推荐(个人) - 知乎](https://zhuanlan.zhihu.com/p/458340252)
	- Citation Key格式说明：[Customize the citation key generator - JabRef](https://docs.jabref.org/setup/citationkeypatterns#default-citation-key-pattern)
	- 由于中文没有空格，作者推荐使用如下格式：[language=ja] [Authors:kuromoji:select=1,2:transliterate=ja][Title:kuromoji:skipwords:select=1,2:nopunct:transliterate=ja][year] | [language=zh] [Authors:jieba:select=1,2:transliterate=zh][Title:jieba:skipwords:select=1,2:nopunct:transliterate=zh][year] | [authEtAl][shorttitle2_2][year]，需要开启enable jieba
- [Zutilo](https://github.com/wshanks/Zutilo)：自定义快捷键插件
- Zotfile：文件管理相关插件
  collapsed:: true
	- zotero 本身就允许附件和数据分别储存，在首选项-高级-文件和文件夹中可以设置，zotfile 只是在此基础上附加了一些功能，无法改变文件夹内的微观结构（一个条目一个文件夹），仍然不便于手动查找。
	- Source Folder for Attaching New Files
	  collapsed:: true
		- [网友](https://zhuanlan.zhihu.com/p/104848524)：““举个例子：我通过zotero浏览器插件添加了一篇文献，Zotero自动抓去了文献条目信息，但是却没法自动下载附件，这时候我手动将附件下载到我指定的“Source Folder”文件夹内部，然后再条目上右键选择“Attach New File”，ZotFile就会自动从“Source Folder”文件夹读取我最新下载的附件追加到条目，然后自动转移到我所设定的需要转移的文件夹内部。”
	- Custom Location：这个对应zotero高级设置中的相对路径，只是增加了生成子文件夹功能
- Chartero：记录使用zotero内置阅读器阅读PDF的历史 [chartero: 做个好看的Zotero插件](https://gitee.com/const_volatile/chartero)
- Zotero Citation Picker for Windows (独立软件)
  id:: df93c1de-7efd-437e-a764-89f2a45a188c
  collapsed:: true
	- 全局调用zotero搜索并导出多种样式
	- 官网：[boan-anbo/Zotero-Citation-Picker-for-Windows: An AHK-based application to search and pick Zotero citations on Windows.](https://github.com/boan-anbo/Zotero-Citation-Picker-for-Windows)
	- 点击选中的文献或者按Ctrl+向下键可以继续向该条目增加元信息，在选择元信息时可以快速按字母键选择要增加的元信息，比如快速按下ch可以跳转到Chapter