# document-memorandum
![](https://img6.bdstatic.com/img/image/public/liuyifei.jpg)
#### 端口相关
* 查找端口   
netstat -ano|findstr 8005
* 关闭端口   
taskkill/pid 3116
* 添加文字省略...  
```
    white-space: nowrap;  
    overflow: hidden;  
    text-overflow: ellipsis;
```  

#### nodeJS模块文件形参
```
    argument.callee.toString
    function (exports, require, module, __filename, __dirname)
```
#### 社区 UI类组件库
1. [*stackoverflow*](https://stackoverflow.com/)  
[*齐舞周刊*](https://weekly.75team.com/issue213.html)  
[*17素材网*](http://www.17sucai.com/)  
[*赛风*](http://s3.amazonaws.com/5nkt-sj7x-cc2h/zh.html)
2. [*material-ui*](http://www.material-ui.com/#/)  
[*ant.design*](https://ant.design/docs/react/introduce-cn)  
[*element-cn*](http://element-cn.eleme.io/#/zh-CN/component/layout)

#### git 相关操作
* git log 相关
    * git log
    * git log --pretty=oneline
    * git reflog
    * git log --pretty=oneline 文件名
    
* git 提交相关
    * git add -A  提交所有变化  
    * git add -u  提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)  
    * git add .   提交被修改(modified)和新文件(new)和，不包括被删除(deleted)文件  
    
* git 文件撤销相关
    * git checkout <hash> <filename>     将<hash>值的文件 恢复到当前的状态下
    * git checkout filename 未commit的文件都会被撤销更改 
    
* git tag 相关
    * git tag 查看本地tag
    * git tag v0.1.2-light  创建轻量标签
    * git tag -a v0.1.2 -m "0.1.2版本" 创建附注标签
    * git tag -a v0.1.1 commitid 在指定的版本上面打tag
    * git checkout [tagname]
    * git show tagname 查看tag的具体信息
    * git tag -d tagname 删除本地tag
    * git push origin -d tag tagName 删除远程的标签    
    * git push origin --tags 推送本地所有的tag     
    * git push origin tagName 推送指定的标签到远程仓库

* git branch 相关
    * git fecth 获取远程所有的分支
    * git branch -a 或者 git branch -r  查看远程所有的分支
    * git branch 查看本地分支
    * git branch branchname 创建本地分支
    * git checkout branchname 切换分支
    * git checkout -b branchname 创建并切换分支
    * git branch -d branchname 删除本地分支
    * git merge branchname 将branchname合并进当前的分支
    * git push origin branchname 推送本地分支到远程仓库
        * 远程先开好分支然后拉到本地  
        git checkout -b feature-branch origin/feature-branch    
        检出远程的feature-branch分支到本地
        * 本地先开好分支然后推送到远程  
            git push origin feature-branch:feature-branch   
            或者  git push origin branchname  git push origin :test   
            或者 git branch -r -d origin/branchname  删除远程分支 不会删除本地的分支
        * git branch 的替换
            git push origin dev:master -f 将master分支的内容替换为dev  
            git checkout master // 切换到旧的分支  
            git reset --hard develop  // 将本地的旧分支 master 重置成 develop  
            git push origin master --force // 再推送到远程仓库  
        
    * git 忽略文件  
    touch .gitignore
            
    * git 远程仓库的操作
        * git clone repository
        * git remote -v 查看远程仓库
        * git remote add [name] [url] 添加远程仓库 [name]远程仓库的名称 一般默认是origin
        * git remote rm [name] 删除远程仓库 仅仅是本地无法再进行push
        * git remote set-url --push [name][newUrl] 修改远程仓库
        * git pull [remoteName] [localBranchName] 拉取远程仓库
        * git push [remoteName] [localBranchName] 推送远程仓库
            
    * git 修改文件或者移动文件
        * git mv oldfile newfile
    
    * git 版本回退相关
        * git reset --hard HEAD~number 
        * git reset --hard commitid
        
    * git diff 相关
        * git diff # 查看尚未暂存的文件更新了哪些部分
        * git diff filename #查看尚未暂存的某个文件更新了哪些
        * git diff –cached #查看已经暂存起来的文件和上次提交的版本之间的差异
        * git diff –cached filename #查看已经暂存起来的某个文件和上次提交的版本之间的差异
        * git diff commitid commitid #查看某两个版本之间的差
        * git diff commitid:filename commitid:filename #查看某两个版本的某个文件之间的差异
    
    * git 配置信息
        * git config --local --list
        * git config --global --list
        * git config --local user.name yourname
        g* it config --local user.email youremail

#### npm 相关操作
* npm install -g cnpm -registry=https://registry.npm.taobao.org
* npm install packagename -D #开发依赖
* npm install packagename --save #运行时依赖
* npm install 安装依赖

* npm uninstall -g <package> 卸载全局依赖 
* npm uninstall 卸载本地模块
* npm uninstall 模块 --save 
* npm uninstall 模块 --save-dev 
* npm root # 查看项目中模块所在的目录
* npm root -g #查看全局安装的模块所在的目录
* npm view packagename dependencies #查看某个包的依赖关系
* npm view packagename repository.url #查看某个包的仓库地址
* npm view packagename engines #查看某个包依赖的最低node版本
* npm view packagename version #查看某个模块的在仓库的最新版本
* npm view packagename versions #查看模块的历史版本和当前版本
* npm view packagename #查看一个模块的所有信息
* npm list packagename version #查看某个模块的在当前项目下的版本号
* npm prune #清除未被使用到的模块
* npm help json  
 
#### npm tips
* npm shrinkwrap,可以将项目中的模块版本进行精确锁定这时候只需要运行命令 
npm shrinkwrap,便会产生一个npm-shrinkwrap.json文件，这个文件保存了所有
当前使用的依赖模块的版本：把该文件提交到git仓库中，这样其他人在clone你
的项目的时候，执行npm install命令时，npm检测到该文件中的信息会完整的还
原出完全相同的依赖树  

#### vue
```
cnpm install -g vue-cli  
vue init webpack my_vue_project
```
![](https://gss1.bdstatic.com/9vo3dSag_xI4khGkpoWK1HF6hhy/baike/h%3D452/sign=fc15f432b9fb4316051f7b7f12a54642/902397dda144ad3498fa137edba20cf430ad8586.jpg)

