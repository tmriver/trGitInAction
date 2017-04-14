timeriver's git 实战: 基本操作-->fork-->pull request
学习自 ：廖雪峰 http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000
这是我喜欢的讲解风格，哈哈！

git init //把这个目录变成Git可以管理的仓库

git status //查看状态

git diff  //查看修改详情

git add readme.txt	//提交到暂存区stage

git commit -m "first commit" //提交到master分支

git log //查看commit历史

git reset --hard HEAD //当前版本

git reset --hard HEAD^ //HEAD^ 回退到上一版本

git reset --hard HEAD~100 //HEAD^ 回退到上100个版本

/d/work/gitRepo/trGitInAction	//工作区（Working Directory）
	.git 						//隐藏目录，而是Git的版本库(包含暂存区stage+本地仓库master分支)。
	.git/refs/heads/master		//master分支，git commit 
	.git/refs/heads/dev			//dev分支，git commit 
	.git/refs/tags				
	
	
git checkout -- readme.txt //让这个文件回到最近一次git commit或git add时的状态（使用版本库覆盖工作区）
	//git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令，
	

git reset HEAD readme.txt 	//把暂存区的修改回退到工作区。之后可以1，add添加到工作区；2，checkout放弃工作区的修改。


rm test.txt //删除工作区
git rm test.txt git commit test.txt //从版本库中删除该文件,


远程仓库-----------------
在github上创建一个新的仓库
$ git remote add origin https://github.com/tmriver/trGitInAction.git	//添加远程库
$ git push -u origin master
git clone 	//从远程库克隆


分支管理-----------------为了并行开发，一个分支一个时间线。
创建分支只是创建一个指针


git checkout -b dev //创建并切换到dev分支。相当于git branch dev;  git checkout dev
git branch			//查看所有分支
git checkout master	//切换分支，未add的代码不变。

git merge dev		//合并指定分支dev到当前分支。
	Fast-forward//表示这次合并是“快进模式”，也就是直接把master指向dev的当前提交，不是每次都能快进模式
$ git branch -d dev	//删除dev。
Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在master分支上工作效果是一样的，但过程更安全。	


解决冲突
git checkout -b feature1 	//创建新分支
add & commit readme.txt		//commit, log:f1
git checkout master			//切回master
add & commit readme.txt		//commit, log:m1
git merge feature1			//合并代码，显示冲突。Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容
编辑readme.txt				//commit, log:m2
重新add & commit readme.txt 
git log						//log依次为：m2,m1,f1... 合并成功
git log --graph				//合并路线图


f2222

f2111

m22
m12222