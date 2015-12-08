# Git版本库

git版本库可以理解为一个目录，里面的所有文件都由git托管，每个文件的删除、修改、增加，git都能追踪到，以便以后任何时候都能查到不同的历史版本。

### 创建一个版本库

首先创建一个文件夹，然后执行初始化命令：

	$ mkdir mygit
	$ git init

此时mygit文件夹内会出现一个.git目录，这个目录是用来追踪管理版本库的，不用管里面的东西，也不要去修改。

### 添加文件到版本库

随便在mygit文件夹里建立一个test.txt文件，内容如下（也可随便写）：

	I'm learning git.
	Git is a good tool.

然后用`git add`添加到暂存区：

	$ git add test.txt

最后用`git commit`添加到版本库：

	$ git commit -m "first commit"

-m后面输入的文本是这次提交的说明。

注：或者可以把所有文件`add`到暂存区后再统一提交到版本库

	$ git add 1.txt
	$ git add 2.txt
	$ git add 3.txt
	$ git commit -m "commit three files"

