# Git常用命令
## Git
>分布式版本控制系统  
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency  
[Git官网](https://git-scm.com/)  
[淘宝镜像下载Git](https://registry.npmmirror.com/binary.html?path=git-for-windows/) 
### 配置全局
#### 配置用户名
```bash
git config --global user.name "username"
 ```
#### 配置邮箱
```bash
git config --global user.email "email"
 ```
### 本地仓库搭建
```bash
git init
 ```
### 克隆远程仓库
```bash
git clone [url]
 ```
### 查看文件状态
#### 查看指定文件状态
```bash
git status [filename]
 ```
#### 查看所有文件状态
```bash
git status
 ```
### 分支命令
#### 列出所有分支
```
git branch
```
#### 列出所有远程分支
```
git branch -r
```
#### 新建分支
```
git branch [branchname]
```
#### 新建一个分支，停留在原分支
```
git checkout [branchname]
```
#### 新建一个分支并切换分支
```
git checkout -b [branchname]
```
#### 合并指定分支到当前分支
```
git merge [branchname]
```
#### 删除分支
```
git branch -d [branchname]
```
#### 删除远程分支
```
git push origin --delete [branchname]
git branch -dr [remote/branchname]
```