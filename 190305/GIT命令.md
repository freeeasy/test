# GIT命令

工作区--（暂存区-本地仓库）--远程仓库

##### 个人操作

* 添加、修改、删除（工作区）

* git add 文件名  例如：git add .  表示将所有文件添加到本地仓库

* git rm 文件名

* git checkout 文件名

  ​

* git init   初始化仓库

* git config user.name ‘张三’

* git config user.email 'zhangsan@163.com'



* git status 查看文件状态（红色表示工作区的文件）
* git commit -m '版本信息' 提交到本地仓库
* git commit -am '版本信息' 提交到本地仓库
* git log或git reflog  查看历史历史版本
* git reset --HEAD·1 回退当前版本的前一个版本
* git reset --hard 版本号 回退到指定版本
* git checkout 文件名   撤销更改
* git diff HEAD --文件名 版本对比



* git clone 地址  克隆项目到本地

* git push 推送到远程仓库

* ```
  设置记住密码（默认15分钟）：
  git config --global credential.helper cache
  如果想自己设置时间，可以这样做(1小时后失效)：
  git config credential.helper 'cache --timeout=3600'
  长期存储密码：
  git config --global credential.helper store
  ```

  ##### 多人协通开发

* git pull 代码同步（及时更新代码，协同开发用）

* 编辑代码前要先`pull`，编辑完再`commit`，最后推送是`push`

  #####  代码冲突（多人同时修改了同一个文件中的同一行代码）

  原则：谁冲突谁解决

  修改完add，commit，push

  - 养成良好的操作习惯,先`pull`在修改,修改完立即`commit`和`push`
  - 一定要确保自己正在修改的文件是最新版本的
  - 各自开发各自的模块
  - 如果要修改公共文件,一定要先确认有没有人正在修改
  - 下班前一定要提交代码,上班第一件事拉取最新代码
  - 一定不要擅自修改同事的代码

  ##### 打标签

  ```
   git tag -a 标签名 -m '标签描述'
   例：
   git tag -a v1.0 -m 'version 1.0'
  ```

* 推送标签到远程仓库

  git push origin 标签名

  ```
  例：
   git push origin v1.0
  ```

* 删除标签

```
 # 删除本地标签
  git tag -d 标签名
  # 删除远程仓库标签
  git push origin --delete tag 标签名
```

##### 分支

* git branch查看当前分支

* git checkout -b dev   创建并且换到dev分支

* git push -u origin dev 将分支推送到远程

  * 将Dev分支合并到master分支

    * git branch(查看后有两个分支)

    * git merge dev

      ​