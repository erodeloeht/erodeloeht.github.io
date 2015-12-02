---
Date: 2013-05-07 15:09
Title: Some codings
---

最近由于有海量的实验数据需要处理，在忍受了无数次的打开，另存为，拷贝，复制等机械操作后，终于一狠心现学点程序语言来自动化日常工作。python好学又好用，现学现用。不过mac自带的Applescrip也很方便。以下有两个具体的实现。{{more}}

#### 1. 用applescript把dat文件另存为microsoft excel格式
实验得到的数据都是以dat格式保存，因为接下来我需要用python来读取这些dat文件，所以第一步要做的是把它们另存为xls格式。用python应该也是可是实现，不过applescript也很方便，以下是具体代码。源文件下载[点此](https://dl.dropboxusercontent.com/u/914090/images/2013-05-07-save-as-xls.scpt)。

![](https://dl.dropboxusercontent.com/u/914090/images/2013-05-07-some-codings1.jpg)

#### 2. 合并若干个Excel文件

用python读取每个xls文件，复制工作表到一个新建的工作本。用到的模块有xlrd，xlwt和os。

	# -*- coding: utf-8 -*- 
	import xlrd 
	import xlwt
	import os

	# get the current working directory
	directory = os.getcwd() 

	# set the directory path
	new_listfile = os.listdir(directory)

	# name the new workbook
	f = 'Workbook1.xls'

	# creat a workbook
	wbk = xlwt.Workbook()

	for i in new_listfile:
		pos = i.find('.') # find the position of '.' 
		if i[pos+1:] == 'xls' and len(i) > 15:	# find all xls files in the folder	
			rb = xlrd.open_workbook(i) # open xls file
			rs = rb.sheets()[0] # read sheet number 1
			# add new sheet with the same sheet name to the new workbook
			table = wbk.add_sheet(i[:pos], cell_overwrite_ok=True) 
			# copy the contents to the new sheet
			for row in range (119):
				for col in range (15):
					table.write(row, col, rs.cell(row, col).value)

	wbk.save(f) # save new workbook
	
另外还有两个脚本分别用来处理数据和生成图标，不过只针对我自己的数据有用，就不放上来了。