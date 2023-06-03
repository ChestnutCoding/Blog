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
### Git日常操作流程
1. 克隆远程仓库
```bash
  git clone <远程仓库的网址> 
```
2. git add 添加到暂存区
```bash
  git add --all # 当前项目下的所有更改
```
 ```bash
  git add .  # 当前目录下的所有更改
```
 ```bash
  git add xx/xx.py xx/xx2.py  # 添加某几个文件
```
3. 提交到本地仓库
```bash
  git commit -m"描述信息"
```
4. 推送到远程仓库
```bash
  git push -u origin master # 第一次需要关联上
```
```bash
  git push
```
```bash
  git push -f orgin master # 强制覆盖远程分支
```

### Git新建本地关联仓库
1. 初始化本地仓库
```bash
  git init
```
2. 添加远程仓库
```bash
  git remote add <远程仓库的别名> <远程仓库的URL地址>
```
3. git add 添加到暂存区
```bash
  git add --all # 当前项目下的所有更改
```
 ```bash
  git add .  # 当前目录下的所有更改
```
 ```bash
  git add xx/xx.py xx/xx2.py  # 添加某几个文件
```
4. 提交到本地仓库
```bash
  git commit -m"描述信息"
```
5. 推送到远程仓库
```bash
  git push -u origin master
```
### 切换合并分支
1. 查看分支
```bash
  git branch # 列出所有本地分支
```
```bash
  git branch -r # 列出所有远程分支
```
```bash
  git branch -a # 列出所有本地分支和远程分支
```
2. 创建分支
```bash
  git checkout -b <new-branch-name>
  #如果仅新建，不切换，则去掉参数 -b
```
3. 切换分支
```bash
  git checkout <branch-name>
```
4. 把副分支合并到主分支
```bash
  git checkout <主分支> # 切换至主分支
```
```bash
  git merge <副分支> # 将副分支合并到主分支
```
5. 删除本地分支
```bash
  git branch -d <branch-name>
```
6. 删除远程分支
```bash
  git push origin --delete <branch-name>
```
```bash
  git remote prune origin
  # 删除远程分支后，更新本地无效分支
```
7. 新建远程分支
```bash
  git push origin <branch-name>
```
