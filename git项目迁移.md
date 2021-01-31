<!--
 * @Author: your name
 * @Date: 2021-01-31 14:48:27
 * @LastEditTime: 2021-01-31 14:49:00
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /How2UseGit/git项目迁移.md
-->
### git 项目迁移指南
#### 诉求1: 迁移到新的 group
#### 诉求2：保留旧的 git 提交记录等一切信息
1. git clone --bare 旧仓库地址
2. git 创建空的项目，并记住新的仓库地址
3. 进入 1 克隆的项目目录， git push --mirror 新仓库地址1
