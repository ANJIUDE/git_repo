# git

##### 基础指令

- 提交命令：git commit
- 创建分支：git branch name
- 切换分支：git checkout name
- 一键创建并切换分支：git checkout -b name

##### 进阶指令

- 查看工作区用户信息：git config -l
- 提交工作区用户信息：git config user.name "'name'"
- 提交工作区用户信息：git config user.email "email"
- 查看工作区待提交文件：git status
- 添加工作区文件：git add .
- 给文件添加描述信息：git commit -m"描述信息"
- 提交远程服务器：git push



## 合并分支

##### git merge name

- 这个合并方式是属于将当前分支和另一个分支合并并且归纳起来
- name  的意义就是被合并到当前所在分支

##### git rebase name

- 这个合并方式是属于将当前分支备份一份副本归纳到另一个分支底下，属于线性归纳，更加直观
- name  的意义就是将当前分支的副本归纳到这个分支之下



## 分离HEAD

- git checkout C4   (C4可以理解为一个提交记录)
- 这样的目的是将HEAD从分支上转移到提交节点上，也可以说提交记录上



## 相对引用 ^ ~

- 一般用于转移HEAD
- 通常格式：git checkout main^   /   git checkout main~3
- 前一个的意义是将main分支上的HEAD上移一个节点
- 后一个的意思与上面相同，不过是移动多个节点，例如3个节点
- 





