## Git 将本地代码提交到 github
1. 建立本地 git 仓库，cd 到你的本地项目根目录下，执行 git init 命令
	cd 本地工程根目录
	git init  //这个目录就变成了git可以管理的仓库
2. 将本地项目工作区的所有文件添加到暂存区。小数点 “.” ，意为添加文件夹下的所有文件；也可以将 “.” 换成具体的文件名，如果想添加项目中的指定文件，那就把 “.” 改为指定文件名即可
	git add .
3. 降暂存区的文件提交到本地仓库
	git commit -m "提交描述"
4. 在github或者github上创建新的repository,本文基于github操作,gitlab类似
5. 降本地代码提交到远程仓库
	git remote add origin https://github.com/lujunlj/md.git
	在这一步如果出现错误:
	fatal: remote origin already exists
	git remote rm origin
	再输入
	git remote add origin https://github.com/lujunlj/md.git
6. 将代码由本地仓库上传到github远程仓库,依次执行下列语句
	6-1 获取远程库与本地同步合并 （如果远程仓库不为空必须做到这一步,否则后面的提交会失败）:
		git pull --rebase origin master //不加这句可能报错 原因是 github 中的 README.md 文件不在本地仓库中
	//可以通过该命令进行代码合并
	6-2 把当前分支master推送到远程,执行此命令后有可能会让输入用户名、密码
		git push -u origin master
	//如果你本地的当前分支不是master,就用git checkout master 命令切换到master 分支
	//如果你想用本地当前分支上传代码,则把第6步的命令里的master切换到你的当前分支名即可
#### 至此，操作成功!