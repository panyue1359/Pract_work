- ## 基础
- 可识别表格、竖排文字和公式，专业版可以自定义付费接口
- ((ffed279a-dda4-412b-afbb-0863b56bc44d))：需要申请付费接口
  id:: 62529410-46f1-4f53-b43b-f8251dd7fbe9
- ((95bde2e1-5fc2-4322-a227-29f5c5fc11e3))：在右侧预览窗口复制，支持混排
  id:: 4d030039-e9f4-4baf-98c7-b5cf699ffa04
- ## 问题
- ~~天若窗口重新获取焦点自动切换到全角~~，新版已修复
  collapsed:: true
	- 这个问题可能是[net 2.0下，Winform中进行焦点转移时，输入法自动切换全角的问题。 - 眯妖 - 博客园](https://www.cnblogs.com/zhouhuitao/archive/2012/07/05/2577591.html)，下载微软补丁NDP20-KB925488-X86.msp，但提示“找不到要升级的程序”
	- 点击鼠标的同时按Shfit+space切换，发现可以禁用全角
	- [本地版](https://gitee.com/wanglifree/tianruoocr-cl/tree/master)没有这个问题
- 快捷键呼出窗口没有焦点，需要点一下
  id:: 632988f0-89ca-41a0-bd42-2e9fa0ff1a4d