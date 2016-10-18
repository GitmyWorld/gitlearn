# gitlearn

### 基本操作：


- git config --global user.email""
- git config --global user.name""
- git pwd 显示当前目录
- 工作区 ----add----暂存区---commit提交--版本库---push--远程

- 版本回退：commot提交之后：git reset --hard HEAD^ // 前一版本   HEAD当前版本
		  git reset --hard 版本号id前几位数
		  
- 纪录我的每一次历史命令：git reflog

- cat 文件名 //查看文件内容


//撤销修改

- git checkout --file //丢弃工作区修改
- git reset HEAD file 把暂存区的修改撤销（unstage），重新放回工作区

//删除文件

- 工作区删除 直接删或者rm file
- 版本库删除：git rm file-----git commit



### 通用步骤：

1.安装git

2.建立远程仓库
	
3.git链接仓库

git clone + 地址（项目主页--代码--左下地址）,下载远程库
  
4.进入根目录master分支操作
 
- git log 查看版本
    //如果操作时间过长，把最新那份复制下来，更新本地代码库
- git pull  成功 包含git fetch 和marge
    
    所以要是不更改源文件取get pull，否则会被覆盖 ，需要取舍，或者vim
    
    如果已经更改txt了就先commit，没有产生版本号，然后git pull 被覆盖了~~（那我commit的还在吗？），然后我再merge，发现有冲突了！
    窗口提示我，修改冲突，再一次add ，commit。。
    
-    git fetch <远程主机名> <分支名>
    
远程主机名 git remote -v

 5.然后添加文件或者覆盖；
 
 6.使用本地git branch (或者所有分支 git branch -a  远程分支 git branch -r)
 
- 查看活动分支： 带星号的为活动分支
- git checkout -b branchname  //只在本地产生
    创建并HEAD指针指向该分支：相当于
    {创建：git branch branchname
    指向转换分支：git checkout branchname}  
    
- 转向新建branch操作
    add* 新文件名
    commit
    git log 获取版本号
 
 7.转回主分支

-  把其他分支合并到master上:git merge branch2 // merge是把分支合并到master分支上
-  cherry-pick 分支里获取的版本号 // 把多个commit和并到master分支上
 
 8.push origin master
 
 9.完成后删除分支
    git branch -d branch
	 
