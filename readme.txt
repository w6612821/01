day03 

git  分布式版本控制器  




命令:
    ls 查看当前目录下的文件 
    cd 切换目录 
    clear 清屏
    pwd 显示完整路径 
    touch 可以创建一个文件
    rm 删除一个文件 
    mkdir 创建一个文件夹aa

基础的设置:
    git config --global user.name "deslibai"
    git config --global user.email "libaibuhejiu@foxmail.com"


核心命令:
    git init  创建一个git 仓库
    git add 文件名  将工作区当中的文件提交到暂存区 
    git commit -m "关于本次提交的说明" 将暂存区中的文件提交到分支仓库
    git status 查看文件状态
  版本回退:
    git log 查看最近的几次操作   --pretty=oneline 
    git reset   让代码回滚到上一个版本                
                --hard HEAD^
                --hard 1b9d7b
    git reflog 查看曾经的一些操作，可以看到id号
  代码修改:
    ① 当修改了文件并且提交到了暂存区，之后又进行了第二次修改，那么应该将暂存区当中的文件先进行提交，然后再重新把第二次修改的进行提交
    ② 当对一个文件进行了修改并且提交到了暂存区，之后进行了第二次修改，然后想要撤销掉第二次修改:
        git checkout -- 文件名 
    ③ 当对一个文件修改完成后并且提交到了暂存区，如果想要把其修改撤回到工作区，可以使用:
        git reset HEAD 文件名 
  文件删除:
    如果在本地将一个文件删除，并且这个文件在分支仓库当中已经有了存储，那么此时有两个选择：1 通过分支仓库回复删除的文件 2 将分支仓库里面的文件也删除
    git checkout  -- 文件名 通过这条命令可以从分支仓库找回文件 
    git rm 文件名  执行删除操作 
        git commit -m '' 将删除命令发送到分支仓库，这样就会把分支仓库的文件也删除掉

    libaibuhejiu@foxmail.com

    如果你的电脑第一次链接远程仓库，需要执行下面的命令，并且把生成的秘钥粘贴在远程仓库当中。
    ssh-keygen -t rsa -C "libaibuhejiu@foxmail.com"  生成一个秘钥

    创建一个远程仓库

  链接远程仓库:
    git remote add origin https://github.com/deslibai/e1.git
    将本地分支仓库的文件上传到远程仓库
    git push -u origin master(第一次提交的时候执行本句，第二次之后提交 git push origin master) 
  下载:
    git pull origin master (需要先连接远程仓库)
    git clone 文件地址 (相当于是把目标文件进行了一次克隆)
  

  
  分支操作
    git branch 查看分支 
    git branch 名字 创建分支 
    git checkout 分支名 切换分支
    git branch -d 分支名  删除分支 
    git merge 分支名 合并分支 
    git checkout -b 名字 创建并且切换到新创建的分支 

 特殊文件: 专门用来忽略不想上传的文件
    .gitignore

    例如:
     想要不去上传或者说忽略掉.html的文件，那么就可以直接在这个文件里面写
     *.html 这样的话在工作区中所有的html代码就会被忽略掉。

     如果想要把特殊文件也进行上传，需要在git add 后面加上一个-f ,例如:
     git add -f 01.html
linux设计哲学:
    没有回应就是最好的回应 

