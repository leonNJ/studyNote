# Shell文件包含_9

---

和其他语言一样, Shell 也可以包含外部脚本. 这样可以很方便的封装一些公用的代码作为一个独立的文件. 

Shell 文件包含的语法格式如下: 

	. filename   
	
	或
	
	source filename

注意**点号(.)和文件名中间有一空格**. 

## 实例 

创建两个 shell 脚本文件. 

test1.sh 代码如下: 

	#！/bin/bash
	
	url="www.baidu.com"

test2.sh 代码如下: 

	#!/bin/bash
	
	#使用 . 号来引用test1.sh 文件
	. ./test1.sh
	
	# 或者使用以下包含文件代码
	# source ./test1.sh
	
	echo "百度地址: $url"

运行结果: 

	[root@localhost yichang]# ./test2 
	百度地址: www.baidu.com

注: **被包含的文件 test1.sh 不需要可执行权限**. 

