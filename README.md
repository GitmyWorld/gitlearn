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
	 
==其他==：
	 
##### 2个退出技巧：

1.突然需要修改什么文件：vi 文件名

2.查看commit 的路线：git log -graph

- git log 日志过长无法退出：按q；

- 因为冲突出现的vim画面：
退出方法：
 在出现需要你输入新的merge信息的终端窗口，在最上面的提示句下有一行空格，
 按照链接的帮助，按”i”进入输入模式，随便输入个什么，然后 esc，
 直接输入”:wq”你会发现这个出现在终端的最下面，这是OK的，最后                     enter，就OK了。
 Writing objects:文件大就等
    	 
3.当文件过大，或者提示Unable to rewind rpc post data等时,         需要将http.postBuffer设置成适合的值
    git config --global http.postBuffer 20480000
    git config --list

##### 使用vim 命令打开、关闭、保存文件

1、vi & vim 有两种工作模式：

（1） 命令模式：接受、执行 vi & vim 操作命令的模式，打开文件后的默认模式；
（2） 编辑模式：对打开的文件内容进行 增、删、改 操作的模式；
 #在编辑模式下按下 ESC 键，回退到命令模式。
     
2、创建、打开文件：$ vi [filename]

（1）使用 vi 加 文件路径（或文件名）的模式打开文件，如果文件存在则打开现有文件，如果文件不存在则新建文件，并在终端最下面一行显示打开的是一个新文件。
（2）键盘输入字母 “i”或“Insert”键进入最常用的插入编辑模式。

3、保存文件：

（1）在插入编辑模式下编辑文件。
（2）按下 “ESC” 键，退出编辑模式，切换到命令模式。
（3）在命令模式下键入"ZZ"或者":wq"保存修改并且退出 vi 。
（4）如果只想保存文件，则键入":w"，回车后底行会提示写入操作结果，并保持停留在命令模式。

4、放弃所有文件修改：

（1）放弃所有文件修改：按下 "ESC" 键进入命令模式，键入 ":q!" 回车后放弃修改并退出vi。
（2）放弃所有文件修改，但不退出 vi ，即回退到文件打开后最后一次保存操作的状态，继续进行文件操作：按下 "ESC" 键进入命令模式，键入 ":e!" ，回车后回到命令模式。
