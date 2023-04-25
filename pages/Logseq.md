- ## 基础
  id:: b77424ab-ef18-4892-8b51-aa8a10e9c458
- 插件市场主题
	- Allday Theme左侧栏看不清
	- Gunmetal Theme日记中会显示两个日历图标
	- Bonofix Theme字体过于纤细
	- Neno Theme除日记以外的页面标题全都看不清
	- Craft Theme字体偏小，日记中会显示两个日历图标
	- Atlas Theme字体非常小
	- Dev Theme字体偏小
	- Woz Theme字体正常，可以突出显示链接，已使用
- [B站分Part视频](https://cn.logseq.com/t/topic/1137)： 直接粘贴网址不能识别，需要使用格式 https://www.bilibili.com/video/:BV&page=:num num指part
- 自定义字体
	- [推荐一个中文字体：方正清刻本悦宋](https://cn.logseq.com/t/topic/2970)
- 分级页面
  id:: 620b7351-6599-4eb4-82f8-a4febb2749ad
	- Logseq的层级页面命名不能传递，比如我建立两个页面\[[第一层/第二层/第三层]]和\[[第二层/第三层]]，第一个的第三层和第二个的第三层不是一个页面
	- Logseq的分级页面能在中间插入级别吗，就像在表格里插入列
	- 能否用插件实现自动插入上级内容
- 别名功能
  id:: 625971ac-9d00-47d9-b475-985c44457940
	- 别名应该视为同义词，在检索中应该享有和同义词相同的待遇，例如mouse和mice是同义词，那么在搜索mouse时应该提示mice。
	- 目前别名的唯一功能就是重定向到所谓原始页面，在搜索中则完全无关，事实上反而造成了冗余。
- ## 问题
  id:: 635d44de-8699-4e40-9430-bb6eb0620bfe
- 无法访问插件市场，使用hosts代理，修改Logseq代理为direct
  id:: 63e511c8-3fa7-4971-bc93-a0c7ec87b7a2
- [Filters for note body, not just backlinks - Feature Requests - Logseq](https://discuss.logseq.com/t/filters-for-note-body-not-just-backlinks/1305)
- [Filtering for the Linked Reference filter - Feature Requests - Logseq](https://discuss.logseq.com/t/filtering-for-the-linked-reference-filter/3718)
- [Longform writing in Logseq - Feature Requests - Logseq](https://discuss.logseq.com/t/longform-writing-in-logseq/3527/25)
- [Proposal: Changing How Namespaces Function in Logseq - Bug Reports - Logseq](https://discuss.logseq.com/t/proposal-changing-how-namespaces-function-in-logseq/3727/17)
- [Improve implementation of aliases - Feature Requests - Logseq](https://discuss.logseq.com/t/improve-implementation-of-aliases/81)
- ## 插件
  id:: 620b0fb0-f6b1-441c-9d1e-0cc518269fd6
- logseq-extract-plugin：抓取高亮或加粗部分
- logseq-hugo-plugin：导出hugo可用的page
  id:: 625e725c-3165-4537-9187-19d11d1871eb
  collapsed:: true
	- Hugo建站
		- 官网：官方文档写得很差
			- [Hugo Home](https://gohugo.io/)
			- [HUGO Community](https://discourse.gohugo.io/)
		- 下载Hugo：[手把手教你使用Hugo搭建个人博客网站|保姆级教学_Hudie.的博客-CSDN博客_使用hugo搭建博客](https://blog.csdn.net/weixin_43691058/article/details/101772871)
		- 建立博客文件夹，如hugo new site E:\Panyue\Data\hugo myblog
			- 文件结构说明：[Hugo的使用_欢欢2776479680的博客-CSDN博客_hugo使用](https://blog.csdn.net/qq_30682027/article/details/83536577)
		- 下载主题：[Complete List | Hugo Themes](https://themes.gohugo.io/)
			- 有些主题不会下载到theme中，需要手动复制其中exampleSite文件夹中的config.toml文件到博客文件夹根目录替换config.toml
			- 一些主题的安装教程提示 git submodule add xxx.git 需要建立git仓库，如果不想建立git仓库可以git clone
			- 进入exampleSite目录，运行hugo server --themesDir ../..可看示例
			- 如果报错如 module "hugo-theme-basic" not found，需要修改config.toml中的theme为主题的文件夹名称或相反
			- even支持数学公式，不过没有搜索框
		- 将主题中的config.toml复制到博客根目录可以配置参数
		- LaTeX公式
			- 查找所需mathjax脚本：[mathjax - Libraries - cdnjs - The #1 free and open source CDN built to make life easier for developers](https://cdnjs.com/libraries/mathjax/3.2.0)
			- [Hugo支持MathJax的配置_WingsZeng的博客-CSDN博客](https://blog.csdn.net/weixin_42465278/article/details/117368615)推荐配置
				- 在主题文件夹中的layouts中建立partials文件夹，新建mathjax.html文件，粘贴以下内容
					- 具体解释：[前端整合MathjaxJS的配置笔记 - SegmentFault 思否](https://segmentfault.com/a/1190000008317350)
					- 去掉倒数第二段代码：[markdown - Rendering Latex on Hugo websites with MathJax - Stack Overflow](https://stackoverflow.com/questions/56648378/rendering-latex-on-hugo-websites-with-mathjax)
					- ``` HTML
					  <script type="text/javascript"
					          async
					          src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
					  </script>
					  
					  <script type="text/x-mathjax-config">
					    MathJax.Hub.Config({
					      tex2jax: {
					        inlineMath: [['$','$'], ['\\(','\\)']],
					        displayMath: [['$$','$$'], ['\[','\]']],
					        processEscapes: true,
					        processEnvironments: true,
					        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
					        TeX: { equationNumbers: { autoNumber: "AMS" },
					    extensions: ["AMSmath.js", "AMSsymbols.js"] }
					      }
					    });
					  </script>
					  
					  //<script type="text/x-mathjax-config">
					  //  MathJax.Hub.Queue(function() {
					  //    // Fix <code> tags after MathJax finishes running. This is a
					  //    // hack to overcome a shortcoming of Markdown. Discussion at
					  //    // https://github.com/mojombo/jekyll/issues/199
					  //    var all = MathJax.Hub.getAllJax(), i;
					  //    for(i = 0; i < all.length; i += 1) {
					  //        all[i].SourceElement().parentNode.className += ' has-jax';
					  //    }
					  //});
					  //</script>
					  
					  <style>
					  code.has-jax {
					    font: inherit;
					    font-size: 100%;
					    background: inherit;
					    border: inherit;
					    color: #515151;
					  }
					  </style>
					  
					  ```
				- 在使用的layouts文件夹中找到包含<div class="post-footer">代码的html文件，增加{{ partial "mathjax.html" . }}
			- [mathjax - How to use markdown syntax to write math in Hugo? - Stack Overflow](https://stackoverflow.com/questions/64050359/how-to-use-markdown-syntax-to-write-math-in-hugo)推荐配置
				- 在使用的 layouts 文件夹中找到包含<div class="post-footer">代码的 html 文件或者footer.html文件，添加以下代码
					- ``` html
					  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
					  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
					  
					  ```
		- 反向链接
			- ``` html
			  {{ $re  = $.File.BaseFileName }}
			  {{ $backlinks  = slice }}
			  {{ range where .Site.RegularPages "Type" "page" }}
			     {{ if and (findRE $re .RawContent) (not (eq $re .File.BaseFileName)) }}
			        {{ $backlinks = $backlinks | append . }}
			     {{ end }}
			  {{ end }}
			  
			  {{ if gt (len $backlinks) 0 }}
			    <aside>
			      <h3>Backlinks</h3>
			      <div class="backlinks">
			        <ul>
			  {{ range $backlinks }}
			     <li class="capitalize"><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
			  {{ end }}
			       </ul>
			      </div>
			    </aside>
			  {{ else  }}
			    <aside>
			      <h4>No notes link to this note</h4>
			    </aside>
			  {{ end }}
			  
			  <aside class="related">
			    {{ $related  = .Site.RegularPages.Related . | complement $backlinks | first 3 -}}
			    {{ with $related -}}
			    <h3>slightly related</h3>
			    <ul>
			    {{ range . -}}
			    <li class="capitalize"><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
			    {{ end -}}
			    </ul>
			    {{ end -}}
			  </aside>
			  
			  ```
		- hugo server -t theme buildDrafts报错either add it as a Hugo Module or store it in
			- 查看config.toml文件的themeDir是否是"../.."
		- 如果出现一大段报错可能需要替换config.toml文件
	-
- ## 代码块自动换行
- 自带的config.edn里有相关的配置，但是开启后程序崩溃
- 在config.edn里添加论坛提供的代码，成功 [Wrap long code lines in Logseq inside the Src ``` code ``` block - Feature Requests - Logseq](https://discuss.logseq.com/t/wrap-long-code-lines-in-logseq-inside-the-src-code-block/8149/3)
	- ``` 
	  :editor/extra-codemirror-options 
	    { :lineWrapping true }
	  ```