# document-memorandum
![](https://img6.bdstatic.com/img/image/public/liuyifei.jpg)
#### 端口相关
* 查找端口
netstat -ano|findstr 8005
* 关闭端口
taskkill/pid 3116

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
    * git log filename
* git 查看某个版本的文件内容
    * git show commitid filename
* git 提交相关
    * git add -A  提交所有变化
    * git add -u  提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)
    * git add .   提交被修改(modified)和新文件(new)和，不包括被删除(deleted)文件

* git 文件撤销或者覆盖相关
    * git checkout commitId filename     将commitId的文件 恢复到当前的状态下
    * git checkout filename 未commit的文件都会被撤销更改
* git 暂存区相关
    * git rm --cache filename --删除暂存区文件
    * git rm -f filename --删除工作区和暂存区文件
* 删除错误提交的commit
    * git reset --soft 版本库ID 仅仅只是撤销已提交的版本库，不会修改暂存区和工作区
    * git reset --mixed 版本库ID 仅仅只是撤销已提交的版本库和暂存区，不会修改工作区
    * git reset --hard 版本库ID 彻底将工作区、暂存区和版本库记录恢复到指定的版本库
* git 版本回退相关
    * git reset --hard HEAD~number
    * git reset --hard commitid
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
    * git merge branchname 将branchname合并进当前的分支
	* 获取远程分支到本地 (创建并切换分支)
		- git checkout -b branchName origin/branchName
	* 本地先开好分支然后推送到远程
		- git push origin branchName:branchName 
		- git push origin branchname  
	* 删除本地分支
		- git branch -d branchname 删除本地分支
		- git branch -D branchname 强制删除本地分支
	* 删除远程分支	
		- git push origin :test 
		- git push origin -d branchName 
	* git branch 的替换
		git push origin dev:master -f 	// 远程dev分支替换master分支
		git checkout master 			// 切换到master的分支
		git reset --hard dev  			// 将本地的旧分支 master 重置成 dev
		git push origin master --force 	// 再推送到远程仓库 (不是必须)

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

    * git diff 相关
        * git diff 查看尚未暂存的文件更新了哪些部分 注意:是工作区和Index区的比较,如果Index区是空的则直接和当前版本区进行比较
        * git diff filename 查看尚未暂存的某个文件更新了哪些
        * git diff [HEAD^|HEAD~n|commitId] filename 查看已经暂存起来的文件和版本库之间的差异
        * git diff commitid commitid 查看某两个版本之间的差异
        * git diff commitid:filename commitid:filename 查看某两个版本的某个文件之间的差异

    * git stash 相关
        * git stash || git stash save "说明信息"
        * git stash list
        * git stash apply stash@{n}  保留stash记录
        * git stash pop || git stash pop stash@{n}       将stash弹出,同时会删除stash记录
        * git stash drop || git stash drop stash@{n}     删除stash记录
        * git stash clear
        * git show stash@{n}
        * git stash不针对特定的分支，切换分支后，stash内容不变，所以弹出时要小心
        * git stash pop或者drop后，stash的序号会自动改变，连续弹出时要注意。

    * git 配置信息
        * git config --local --list
        * git config --global --list
        * git config --local user.name yourname
        * git config --local user.email youremail

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
* npm list -g --depth 0 查看全局安装过的包


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
#### webpack 相关配置
* html-webpack-plugin
```
const HtmlWebpackPlugin = require('html-webpack-plugin');
module.exports = {
    ...
    plugins: [
        new HtmlWebpackPlugin({
            title: '',        // 设置HTML文件中的title
            filename: '',     // 设置HTML文件的名字，默认index.html
            template: '',     // 指定生成HTML文件的模板，使用自定义的模板文件时，要提前安装对应的loader
            inject: '[true | body | head | false]',    // 注入选项，决定js文件引用的位置
            favicon: '',      // 设置HTML文件中的shortcut icon favicon
            minify: [false | {html-minifier}],    // 压缩选项
            hash: [false | true],    // 给生成的js文件一个独特的hash值，默认值为false
            cache: [true | false],   // 默认值true，表示只有在内容变化时才生成一个新的文件
            showErrors: [true | false],    // webpack编译出现错误时，将错误信息包裹在pre标签内，默认为true，也就是显示错误信息
            chunks: [],            // 主要针对多入口文件，指定引入特定的文件，默认引用全部
            excludeChunks: [],     // 指定不引入特定的文件
            chunksSortMode: [dependency | auto | none | {function}],    // 决定引入文件的引用顺序
            xhtml: [false | true]    // 默认值false，为true时表示以兼容xhtml的模式引用文件
        })
    ]
}
```
1. 当同时设置title和template时，webpack会选择template中的title，即使其未设置。
2. inject选项：
    - true    默认值，script标签位于html文件的body底部
    - body    同true
    - head    script标签位于head标签内
    - false   不插入生成的js文件，只是单纯的生成一个html文件
3. minify选项：
    - false   默认值，不对生成的html文件进行压缩
    - {html-minifier}    https://github.com/kangax/html-minifier#options-quick-reference
4. chunksSortMode选项：
    - dependency    按照依赖关系排序
    - auto          默认值，按插件内置的排序方式
    - none
    - {function}


![](https://gss1.bdstatic.com/9vo3dSag_xI4khGkpoWK1HF6hhy/baike/h%3D452/sign=fc15f432b9fb4316051f7b7f12a54642/902397dda144ad3498fa137edba20cf430ad8586.jpg)

