- ## 基础
- 快速填充单元格
  collapsed:: true
	- [EXCEL空白单元格自动填充为上一个非空单元格内容_百度知道](http://zhidao.baidu.com/question/2052980308363849627?sharesource=weibo)
	  id:: 6210a845-be06-43a5-b98c-73ddbae5ffe7
	- Ctrl+D填充单元格，对于数据很多的情况有用
	- 对于很长的列表，如何在旁边快速填充公式
	  collapsed:: true
		- 在第二列开头插入公式，在第一列使用Ctrl+方向键下跳转到文档尾，平移到第二列尾部，使用shift+ctrl+方向键上选择该列，使用Ctrl+D填充
		- [在奇数行后面填充偶数行数据](https://zhidao.baidu.com/question/1303012932180756899.html)，然后[复制-粘贴，转化为文本](https://jingyan.baidu.com/article/c35dbcb01742fec917fcbc78.html)
- IF语句
  collapsed:: true
	- 示例：使用IF语句嵌套，标记只有硬度、只有相组成和都有
	  
	  ``` excel
	  =IF(I2=-2000,"只有相组成")
	  =IF(I2>0,"只有硬度")
	  =IF(ISLOGICAL(K2),IF(ISLOGICAL(L2),"都有",L2),K2)
	  ```
- 拆分字母和数字混杂的数据：分列
  collapsed:: true
	- [如何在excel表格中将字母和数字分开-百度经验](https://jingyan.baidu.com/article/6181c3e0ff37b2152ef153c9.html)
- ((13827514-91a4-4500-97a1-120c60188c79))：[怎么在Excel2010 的图表中设置双横轴?-ZOL问答](https://ask.zol.com.cn/x/6844061.html)
- ## 报错
  id:: 6e6006a4-6325-4f19-972f-243482bc3065
- [Excel 2010双击打开文件后为灰色空白，不显示内容 - Microsoft Community](https://answers.microsoft.com/zh-hans/msoffice/forum/all/excel/7fb0d2a0-aed6-4d89-b962-6d51bb53cda9?page=2)
  collapsed:: true
	- 打开注册表
	- 在HKEY_CLASSES_ROOT列表中下拉找到Excel.Sheet8，依次选择shell--open--command--(默认)
	- 将 /dde修改为 "%1"即可（双引号切记用英文的）
	- 同理不仅仅只是修改Excel.Sheet8里的，Excel.Sheet12里的也需要如上述的操作进行修改
	- 如果还有其他也可以自行探索。我是就修改了这两个就可以打开我的所有文档了，如果只修改了一个的话，不同格式的Excel打开可能还是空白。
- ## 插件
- [Excel工具箱 插件-方方格子 工作室-做最专业的Excel工具箱](http://ffcell.com/home/products.aspx)