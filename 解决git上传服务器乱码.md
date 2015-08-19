#解决Git上传服务器文本乱码



1. 在bash提示符输入：

	设置 commit log 提交时使用 utf-8 编码，可避免服务器上乱码，同时与linux上的提交保持一致！
	
	git config --global i18n.commitencoding utf-8

2. 在bash提示符下输入：

	git config --global core.quotepath false
	core.quotepath设为false的话，就不会对0x80以上的字符进行quote。中文显示正常。

