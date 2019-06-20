### 1.在工作目录初始化新仓库
```
$ git init
```

### 2.从现有仓库克隆
```
$ git clone https://github.com/laofa/matlab_note.git
```
注意：  
我们从github获取URL；  
生成一个matlab_note的文件夹；  
origin会默认替代远程仓库URL；  
在文件夹内使用git命令一律是针对当前远程仓库；  
当前我们在master分支上；  
查看本地分支用git branch；  
查看所有分支用git branch -a/-r(本地、远程）；  
当前其他分支如origin/dev在本地没有名字；  
切换本地分支用git checkout -b dev origin/dev；  
查看本地分支git branch会发现多了一个本地分支；  
当前在dev分支上，就是origin/dev，dev是替代名；  
再切换分支就可以用git checkout master/dev；  

### 3.查看当前远程仓库
```
$ git remote -v
```

### 4.添加远程仓库
```
$ git remote add [origin2] [URL]
```

### 5.拉取远程仓库和分支
```
// git pull命令的作用是，取回远程主机某个分支的更新，再与本地的指定分支合并。  
$ git pull　<远程主机名> <远程分支名> ： <本地分支名>  
$ git pull origin dev:master

// 如果远程分支是与当前分支合并，则冒号后面的部分可以省略，谨慎用。  
$ git pull origin dev

// 上面命令表示，取回origin/next分支，再与当前分支合并。实质上，这等同于先做git fetch，再做git merge。  
$ git fetch origin
$ git merge origin/dev
```

### ６．查看分支
```
// 查看本地已有名字的分支
$ git branch

// 查看所有本地/远程所有分支
$ git branch　-a/-r
```
### ７．创建切换删除本地分支
```
// 第一次创建新的分支
$ git checkout -b dev origin/dev

// 此时在dev分支上，切换回master分支
$ git checkout master

// 删除本地分支
$ git branch -d [branchName]
```

### 8.合并分支
```
// 将某分支合并到当前分支（master）
$ git merge dev
```

### 9.推送分支
```
// 添加本地索引
$ git add *

// 添加提交日志 
$ git commit -m "注释" 

// 若没有配置远程仓库用户名与密码，push代码时会让输入用户名与密码，成功后将会出现如下信息，可使用git config 命令配置
$ git config --global user.email "1005914544@qq.com"
$ git config --global user.name "laofa"

// git push的一般形式为 git push <远程主机名> <本地分支名> : <远程分支名> 
$ git push origin master:master

// 如果省略远程分支名，则表示将本地分支推送与之存在”追踪关系”的远程分支(通常两者同名)，如果该远程分支不存在，则会被新建。
$ git push origin dev

// 如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支。
$ git push origin :dev

// 如果当前分支与远程分支之间存在追踪关系，则本地分支和远程分支都可以省略。
$ git push origin

// 如果当前分支只有一个追踪分支，那么主机名都可以省略。
$ git push
```


