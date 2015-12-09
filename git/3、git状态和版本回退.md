# Git状态和版本回退

### Git状态查看

	$ git status

git status命令可以让我们时刻掌握仓库当前的状态。

### Git查看修改

	$ git diff file

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式

### Git 查看commit日志

	$ git log (--pretty=oneline)

加上 `--pretty=oneline` 输出每次提交的ID和信息

### 回退到上一个版本

	$ git reset --hard HEAD^

### 回退到指定版本

	$ git reset --hard 1234567(ID)

### 查看每次命令

	$ git reflog
