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
	.git 						//隐藏目录，而是Git的版本库。
	.git/refs/heads				//master分支，git commit 
	.git/refs/tags				
	
	
git checkout -- readme.txt //让这个文件回到最近一次git commit或git add时的状态
	//git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令，
	
	addd333
	