## 克隆已有的远程仓库项目下来，修改后提交
##### 1. 克隆项目(https方式，其实可以使用ssh方式，秘钥生成方法随后就到)1
```
// 随便举个栗子
// 格式 git clone "your project adress"
git clone https://github.com/larry0442/How2UseGit.git
```
##### 2. 本地有修改后合并项目到github
1. 添加文件到仓库
```
// add 后面的 .不要漏掉
git add .
```
2. 提交的文件注释说明，需要有说明，方便出错时溯源
- 命令

```
git commit -m "这里写注释说明，比如这次修改了什么功能"
```
3. 将主分支代码从远程仓库pull到本地（可选）
- 命令

```
git pull origin master 

```
- 结果

得到的结果提示大概如下：
```
// 结果
From https://github.com/larry0442/How2UseGit
 * branch            master     -> FETCH_HEAD
Already up to date.
```
4. 将代码提交到GitHub上
- 命令
```
git push -u origin master 
```
- 结果 

这一个操作得到提示如下：
```
// 结果
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 275 bytes | 275.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/larry0442/How2UseGit.git
   622bb8b..2d35f9e  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

```

## 已有的本地项目，关联远程仓库，并提交代码
#####  1、进入本地项目目，将本地项目git化
```
// 初始化本地项目为git项目
git init 
// 一顿操作后，会看到多了一个隐藏的 .git 目录
```
##### 
##### 2、本地项目关联远程仓库(ssh方式)
```
git remote add origin git@github.com:larry0442/How2UseGit.git
```
##### 3、添加项目文件到本地仓库，提交
```
git add .
git commit -m "这里填写提交的备注信息，例如：登录校验代码优化"

```
##### 4、将本地项目文件上传到远程仓库
```
git push -u origin master 
// 首次提交加上 -u 
```
##### 5、完成  


## 生成ssh秘钥（windows 10）
以我的为例子：
.ssh文件夹在C:\Users\yangxinchi\.ssh
#### 1、进入文件夹
```
//进入文件夹的方法
//在桌面右键 git bash here
cd ~/.ssh
//如果提示没有这个文件夹,就先创建
cd ~
mkdir .ssh
//创建完成后进入.ssh
cd .ssh
```
#### 2、创建秘钥
接着上面的步骤键入命令：
```
// 这里留一个邮箱
ssh-keygen -t rsa -C "xxxxmail@exemple.com"
```
接着确认秘钥保存的地址
```
//直接回车就好 默认保存在当前文件夹 
```
接着设置一个密码和确认密码
```
// 可以不设置密码连续两次回车
// 如果设置密码，那密码一定要记得
```
生成秘钥后查看公钥（后缀带有_pub的）
```
使用文本编辑软件（如sublime、atom、notepad++等）打开，  
并全选复制内容
```
打开github or gitlab，找到设置-添加ssh
```
把秘钥里面的内容复制到指定区域，设置好名称，保存
```
最后，愉快地使用ssh方式clone 或者pull/push

## 克隆远程非 master分支
git clone只能clone远程库的master分支，无法clone所有分支，解决办法如下：
1. 找一个干净目录，假设是git_work
2. cd git_work
3. git clone http://myrepo.xxx.com/project/.git ,这样在git_work目录下得到一个project子目录
4. cd project
5. **git branch -a**，列出所有分支名称如下：
remotes/origin/dev
remotes/origin/release
6. **git checkout -b dev origin/dev**，作用是checkout远程的dev分支，在本地起名为dev分支，并切换到本地的dev分支
7. **git checkout -b release origin/release**，作用参见上一步解释
8. **git checkout dev**，切换回dev分支，并开始开发。
   
## 本地创建新分支并推送到远程
```bash
  // 创建(dev为例子)
  git checkout -b dev

  // 推送
  git push --set-upstream origin dev
```
###### end
