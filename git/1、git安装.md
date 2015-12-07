# Git安装

### 在Windows上安装Git

Windows下要使用很多Linux/Unix的工具时，需要Cygwin这样的模拟环境，Git也一样。Cygwin的安装和配置都比较复杂，就不建议你折腾了。不过，有高人已经把模拟环境和Git都打包好了，名叫msysgit，只需要下载一个单独的exe安装程序，其他什么也不用装，绝对好用。

msysgit是Windows版的Git，从[http://msysgit.github.io/](http://msysgit.github.io/)下载，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

![successIntall] (./imgs/successInstall.jpg)

装完成后，还需要最后一步设置，在命令行输入：

	$ git config --global user.name "Your Name"
	$ git config --global user.email "email@example.com"

- - -

**注册github账号：[https://github.com/](https://github.com/)**