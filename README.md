#### 克隆已有的项目下来，修改后提交
##### 1. 克隆项目(https方式)
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