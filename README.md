# Git: Distributed Version Control Fundamentals and Workflows  
  Git学习指南  
  图书阅读摘记  

## 目录  

- [Git: Distributed Version Control Fundamentals and Workflows](#git-distributed-version-control-fundamentals-and-workflows)
  - [目录](#目录)
  - [第一章 基本概念](#第一章-基本概念)
  - [第二章 入门](#第二章-入门)
    - [2.1 准备git环境](#21-准备git环境)
    - [2.2 第一个git项目](#22-第一个git项目)
    - [2.3 Git的协作功能](#23-git的协作功能)
    - [2.4 本章小结](#24-本章小结)
  - [第三章 提交究竟是什么](#第三章-提交究竟是什么)
    - [3.1 访问权限与时间戳](#31-访问权限与时间戳)
    - [3.2 add命令与commit命令](#32-add命令与commit命令)
    - [3.3 再谈提交散列值](#33-再谈提交散列值)
    - [3.4 提交历史](#34-提交历史)
    - [3.5 一种略有不同的提交查看方法](#35-一种略有不同的提交查看方法)
    - [3.6 同一项目的多部不同历史](#36-同一项目的多部不同历史)
  - [第四章 多次提交](#第四章-多次提交)
    - [4.1 status](#41-status)
    - [4.2 存储在暂存区中的快照](#42-存储在暂存区中的快照)
    - [4.3 怎样的修改不该被提交](#43-怎样的修改不该被提交)
    - [4.4 用.gitignore忽略非版本控制文件](#44-用gitignore忽略非版本控制文件)
    - [4.5 储藏](#45-储藏)
  - [第五章 版本库](#第五章-版本库)

---
## 第一章 基本概念  
略  

---
## 第二章 入门  
### 2.1 准备git环境  
1. git官网下载安装git  
2. 用config配置git，如配置用户名和邮箱：  
```shell
$ git config --global user.email "user@service.site"  
```  
### 2.2 第一个git项目  

fisrt-steps目录下有两个文件，如下图所示：  
![first-steps](./images/2.1_first_steps.png)  
1. 创建版本库
```shell
$ cd /target/dir/projects/first-steps  
$ git init  
```
2. 首次提交  

第一步，add文件。  
第二步，commit，完成后会有一个散列值标识本次提交。  
```shell
$ git add foo.txt bar.txt  
$ git commit --message "Sample project imported."  
```  
3. 检查状态  
```shell
$ git status  
```  
用diff显示每个被修改的行  
```shell
$ git diff your.file  
```  

4. 提交修改  

所有修改都必须先被归档成一次新提交。添加使用add命令，删除使用rm命令。  
```shell
$ git add your.file1 your.file2  
$ git rm your.file3  
```
然后提交修改  
```shell
$ git commit --message "your changes"  
$ git commit -m "your changes"  
```

5. 显示历史  
```shell
$ git log  
```

### 2.3 Git的协作功能  
1. 克隆版本库  
```shell
$ git clone /projects/first-steps /projects/first-steps-clone
```
2. 从另一版本库中获取修改  

在原始库中常见一次新提交：  
```shell
$ cd /projects/first-steps  
$ git add foo.txt  
$ git commit -m "A change in the original."  
```
查看修改日志  
```shell
$ git log --oneline
```
修改克隆版本库中的文件：  
```shell
$ cd /projects/first-steps-clone  
$ git add bar.html  
$ git commit -m "A change in the clone"  
$ git log --oneline  
```
把原版本库中的新提交克隆给它的克隆体。  
```shell
$ cd /projects/first-steps-clone  
$ git pull  
```
pull命令取回了新的修改，并于克隆体的本地修改进行对比，并在工作区合并了两边的修改，创建了一次新提交。  
该过程就是所谓的合并（merge）。注意：合并可能会带来冲突，然后合并就会失败。图形显示修改log。  
```shell
$ git log --graph
```

3. 从任意版本库中取回修改  

无参情况下，pull命令旨在克隆版本库中发挥作用。也可以用参数指定任意版本库的路径，以便从某一特定开发分支中
提取相关修改。  
把克隆体中的修改pull到原版本库，代码如下：  
```shell
$ cd /projects/first-steps  
$ git pull /projects/first-steps-clone master
```

4. 创建共享版本库  

可以用push命令将提交传送给其他版本库。不过，push命令只适合用于那些没有开发者在上面开展具体工作的版本库。
最好的方法就是创建一个不带工作区的版本库（裸版本库，bare repository），可以使用`clone --bare`选项创建
一个裸版本库。裸版本库通常可被用来充当开发者们传递提交（使用push命令）的汇聚点，以便其他人可以从中拉回他
们所做的修改。  
```shell
$ git clone --bare /projects/first-steps /projects/first-steps-bare.git
```

5.  用push命令上载修改  
```shell
$ cd /projects/first-steps 
$ git add foo.txt  
$ git commit -m "changes "  
```
把上述修改向共享版本库传送改提交。  
```shell
$ git push /projects/first-steps-bare.git master
```  

6. Pull命令：取回修改  

让克隆版本库也得到响应的修改
```shell
$ cd /projects/first-steps-clone  
$ git pull /projects/first-steps-bare.git master  
```

### 2.4 本章小结  
* **工作区与版本库**：工作区是一个包含 *.git* 子目录中的目录，我们可以用**init**命令在当前目录中
创建版本库。
* **版本提交**：一次版本提交通常定义了版本库中所有文件的一个版本，它详细说明了该版本是由何人在何时何
地创建的。用**add**命令来确定哪些文件被纳入下一次提交，然后用**commit**命令创建新的版本提交。  
* **查看信息**：通过**status**命令，查看哪些文件被修改和将被提交。此外，**log**用来显示提交历史，
**diff**用来显示两个版本文件之间的差异。  
* **克隆**：用**clone**创建的版本库副本被称为克隆体。  
* **推送和拉回**：**push**和**pull**。  

---
## 第三章 提交究竟是什么  
通过`$ git log --stat -1`查看提交中包含的信息。主要包括：散列值（commit hash）、作者信息、时间、以及修改
内容。  
### 3.1 访问权限与时间戳  
Git会保存每个文件所有的访问权限，但不会保留文件的修改时间。在执行检出操作时，文件的修改时间会被设置为当前
时间。

### 3.2 add命令与commit命令  
通过，提交中会包括当前所有的修改，新增和删除。唯一例外的就是在 **.gitignore**文件中的列出的。  

### 3.3 再谈提交散列值  
* 提交的散列值可以在本地生成。
* 散列值中的信息比单纯的软件版本的名称要多得多。
```shell
# git fsck查看版本库的完整性
$ git fsck
```

### 3.4 提交历史
略。

### 3.5 一种略有不同的提交查看方法
> 通过diff命令，比较出两次提交之间的差异  
> 1. 两次提交  
> 两次提交之间有一份完整的差异清单，在不提交散列值的情况下，靠指定相关特定的符号名称（分支、标签、HEAD等）也
> 能获取到它。  
> `$ git diff 77d231f HEAD`  
> 2. 与上一次提交进行比较  
> ```shell
> # 通过使用^!  
> $ git diff 77d231f^!  
> ```
> 3. 限制文件范围  
> ```shell
> $ git diff 77d231f 05bcfd1 - book/bisection/  
> ```
> 4. 统计修改情况
> ```shell
> # --stat选项显示文件中的修改数量  
> $ git diff --stat 77d231f 05bcfd1  
> ```

### 3.6 同一项目的多部不同历史
```shell
# 部分输出  
$ git log -n 3  # only the last three.  
# 格式化输出： --format, --oneline. --format=fuller可显示更多细节
$ git log --oneline  
# 统计信息  
$ git log --shortstat --oneline  
# 图形显示  
$ git log --graph --oneline  
```

---
## 第四章 多次提交
### 4.1 status
```shell
$ git status
$ git status --short
```
输出选项：  
* changes to be committed
* changed but not updated
* untracked files

### 4.2 存储在暂存区中的快照
```shell
$ git diff -staged  # stageing vs. repository  
$ git diff  # staging vs. workspace  
```
### 4.3 怎样的修改不该被提交

不应提交情况：  
* 调试
* 意外添加
* 尚未准备好
* 自动生成文件
从暂存区中撤回：
```shell
$ git rest HEAD .  
# or  
$ git reset HEAD foo.txt /src/test/  
```
应对方法：  
* **reset**重置
* 写入 _.gitignore_

### 4.4 用.gitignore忽略非版本控制文件
```shell
#
# Simple file path
# 
somehow/test.txt
#
# Directories ending with a "/"
#
generated/
#
# File types as glob expressions
#
*.bak
#
# "!" marked exceptions.
#
!demo.bak
```
注意： _.gitignore_ 文件中的条目只能影响还未提交有Git管理的文件。  

### 4.5 储藏
```shell
# 储存栈（stash stack）  
$ git stash

# 恢复  
$ git stash pop

# 查看  
$ git stash list

# 查看栈中修改内容  
$ git stash pop stash@{1}
```

---
## 第五章 版本库
