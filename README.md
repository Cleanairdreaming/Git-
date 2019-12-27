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
    - [5.1 一种简单而高校的存储系统](#51-一种简单而高校的存储系统)
    - [5.2 存储目录：Blob与Tree](#52-存储目录blob与tree)
    - [5.3 相同数据只存储一次](#53-相同数据只存储一次)
  - [第六章 分支](#第六章-分支)
    - [6.1 并行式开发](#61-并行式开发)
    - [6.2 修复旧版本中的bug](#62-修复旧版本中的bug)
    - [6.4 当前活跃分支](#64-当前活跃分支)
    - [6.6 重置分支指针](#66-重置分支指针)
    - [6.7 删除分支](#67-删除分支)
    - [6.8 清理提交对象](#68-清理提交对象)
  - [第七章 合并分支](#第七章-合并分支)
    - [7.2 冲突](#72-冲突)
    - [7.3 编辑冲突](#73-编辑冲突)
    - [7.4 冲突标志](#74-冲突标志)
    - [7.5 解决编辑冲突](#75-解决编辑冲突)
    - [7.6 内容冲突](#76-内容冲突)
    - [7.7 开进合并](#77-开进合并)
    - [7.8 第一父级提交历史](#78-第一父级提交历史)
    - [7.9 棘手的合并冲突](#79-棘手的合并冲突)
    - [7.10 终有可行的方式](#710-终有可行的方式)
  - [第八章 通过变基净化历史](#第八章-通过变基净化历史)
    - [8.2 避免钻石链](#82-避免钻石链)
    - [8.3 什么情况下会遇到冲突呢](#83-什么情况下会遇到冲突呢)
    - [8.4 移植分支](#84-移植分支)
    - [8.5 执行变基后原提交的情况](#85-执行变基后原提交的情况)
    - [8.7 捡取](#87-捡取)
  - [第九章 版本库间的交换](#第九章-版本库间的交换)
    - [9.1 克隆版本库](#91-克隆版本库)
    - [9.2 如何告知Git其他版本库的位置](#92-如何告知git其他版本库的位置)
    - [9.3 给别处的版本库起个名字](#93-给别处的版本库起个名字)
    - [9.4 获取数据](#94-获取数据)
    - [9.5 远程跟踪分支：监控其他分支](#95-远程跟踪分支监控其他分支)
    - [9.6 利用本地分支操作别处的版本库](#96-利用本地分支操作别处的版本库)
    - [9.7 Pull = Fetch + Merge](#97-pull--fetch--merge)
    - [9.8 讨厌钻石链的人：请用--rebase选项](#98-讨厌钻石链的人请用--rebase选项)
    - [9.9 Push: Pull的反面](#99-push-pull的反面)
    - [9.10 命名分支](#910-命名分支)
  - [第十章 版本标签](#第十章-版本标签)
    - [10.1 创建标签](#101-创建标签)
    - [10.2 当前究竟存在哪些标签](#102-当前究竟存在哪些标签)
    - [10.3 打印标签的散列值](#103-打印标签的散列值)
    - [10.4 将标签添加到日志输出中](#104-将标签添加到日志输出中)
    - [10.5 究竟在哪个版本里呢](#105-究竟在哪个版本里呢)
    - [10.6 如何修改标签呢](#106-如何修改标签呢)
    - [10.7 当我们需要一个浮动标签时](#107-当我们需要一个浮动标签时)
  - [第十一章 版本库之间的以来](#第十一章-版本库之间的以来)
  - [第十二章 技巧](#第十二章-技巧)
  - [第十三章 工作流简介](#第十三章-工作流简介)
  - [第十四章 项目设置](#第十四章-项目设置)
    - [14.1 概述](#141-概述)
    - [14.2 使用要求](#142-使用要求)
    - [14.3 工作流简介：设置项目](#143-工作流简介设置项目)
    - [14.4 执行过程及其实现](#144-执行过程及其实现)
      - [14.4.1 基于项目目录创建一个新的版本库](#1441-基于项目目录创建一个新的版本库)
      - [14.4.2 以文件访问的方式共享版本库](#1442-以文件访问的方式共享版本库)
      - [14.4.3 用Git daemon来共享版本库](#1443-用git-daemon来共享版本库)
      - [14.4.4 用HTTP协议来共享版本库](#1444-用http协议来共享版本库)
      - [14.4.5 用SSH协议来共享版本库](#1445-用ssh协议来共享版本库)
    - [14.5 何不换一种做法](#145-何不换一种做法)
  - [第十五章 相同分支上的开发](#第十五章-相同分支上的开发)
    - [15.1 概述](#151-概述)
    - [15.2 使用要求](#152-使用要求)
    - [15.3 工作流简述：相同分支上的开发](#153-工作流简述相同分支上的开发)
    - [15.4 执行过程及其实现](#154-执行过程及其实现)
    - [15.5 何不换一种做法](#155-何不换一种做法)
  - [第十六章 基于特性分支的开发](#第十六章-基于特性分支的开发)
    - [16.1 概述](#161-概述)
    - [16.2 使用要求](#162-使用要求)
    - [16.3 工作流简介：基于特性分支的开发](#163-工作流简介基于特性分支的开发)
    - [16.4 执行过程及其实现](#164-执行过程及其实现)
      - [16.4.1 创建特性分支](#1641-创建特性分支)
      - [16.4.2 在master分支上继承某一特性](#1642-在master分支上继承某一特性)
      - [16.4.3 将master分支上所发生的修改传递给特性分支](#1643-将master分支上所发生的修改传递给特性分支)
    - [16.5 何不换一种做法](#165-何不换一种做法)
  - [第十七章 二分法排错](#第十七章-二分法排错)
    - [17.1 概述](#171-概述)
    - [17.2 使用要求](#172-使用要求)
    - [17.3 工作流简介：二分法排错](#173-工作流简介二分法排错)
    - [17.4 执行过程及其实现](#174-执行过程及其实现)
      - [17.4.1 用二分法人工排错](#1741-用二分法人工排错)
      - [17.4.2 用二分法自动排错](#1742-用二分法自动排错)
    - [17.5 何不换一种做法](#175-何不换一种做法)
  - [第十八章 基于构建服务器的工作](#第十八章-基于构建服务器的工作)
    - [18.1 概述](#181-概述)
    - [18.2 使用要求](#182-使用要求)
    - [18.3 工作流简述：基于构建服务器的工作](#183-工作流简述基于构建服务器的工作)
    - [18.4 执行过程及其实现](#184-执行过程及其实现)
      - [18.4.1 预备构建服务器](#1841-预备构建服务器)
      - [18.4.2 构建服务器上的Git](#1842-构建服务器上的git)
      - [18.4.3 对比本地开发版本库与最后成功构建版本库之间的差异](#1843-对比本地开发版本库与最后成功构建版本库之间的差异)
      - [18.8.4 基于构建历史的排错](#1884-基于构建历史的排错)
    - [18.5 何不换种做法](#185-何不换种做法)
  - [第十九章 发行版交付](#第十九章-发行版交付)
    - [19.1 概述](#191-概述)
    - [19.2 使用要求](#192-使用要求)
    - [19.3 工作流简述：“发行版交付”](#193-工作流简述发行版交付)
    - [19.4 执行过程及其实现](#194-执行过程及其实现)
      - [19.4.1 预备阶段：创建stable分支](#1941-预备阶段创建stable分支)
      - [19.4.2 预备并创建发行版](#1942-预备并创建发行版)
      - [19.4.3 创建补丁](#1943-创建补丁)
    - [19.5 何不换一种做法](#195-何不换一种做法)
  - [第二十章 拆分大项目](#第二十章-拆分大项目)
    - [20.1 概述](#201-概述)
    - [20.2 使用要求](#202-使用要求)
    - [20.3 工作流简述：“拆分大项目”](#203-工作流简述拆分大项目)
    - [20.4 执行过程及其实现](#204-执行过程及其实现)
      - [20.4.1 拆分模块版本库](#2041-拆分模块版本库)
      - [20.4.2 将拆分出的模块作为外部版本库集成](#2042-将拆分出的模块作为外部版本库集成)
    - [20.5 何不换一种做法](#205-何不换一种做法)
  - [第二十一章 合并小型项目](#第二十一章-合并小型项目)
    - [20.1 概述](#201-概述-1)
    - [20.2 使用要求](#202-使用要求-1)
    - [20.3 工作流简介：“合并小项目”](#203-工作流简介合并小项目)
    - [20.4 执行过程及其实现](#204-执行过程及其实现-1)
    - [21.5 何不换一种做法](#215-何不换一种做法)
  - [第二十二章 外包长历史纪录](#第二十二章-外包长历史纪录)
    - [22.1 概述](#221-概述)
    - [22.2 使用要求](#222-使用要求)
    - [22.3 工作流简述：“外包长历史记录”](#223-工作流简述外包长历史记录)
    - [22.4 执行过程及其实现](#224-执行过程及其实现)
      - [22.4.1 外包项目历史](#2241-外包项目历史)
      - [22.4.2 链接到当前活动版本库](#2242-链接到当前活动版本库)
    - [22.5 何不换一种做法](#225-何不换一种做法)
  - [第二十三章 与其他版本控制系统并行使用](#第二十三章-与其他版本控制系统并行使用)
    - [23.1 概述](#231-概述)
    - [23.2 使用要求](#232-使用要求)
    - [23.3 工作流简介：“与其他版本控制系统并行使用”](#233-工作流简介与其他版本控制系统并行使用)
    - [23.4 执行过程及其实现](#234-执行过程及其实现)
      - [23.4.1 初始部署版本库](#2341-初始部署版本库)
      - [23.4.2 得到中央版本控制管理中的更新修改](#2342-得到中央版本控制管理中的更新修改)
      - [23.4.3 将修改提交传输到中央版本控制系统](#2343-将修改提交传输到中央版本控制系统)
    - [20.5 何不换一种做法](#205-何不换一种做法-1)
  - [第二十四章 迁移到Git](#第二十四章-迁移到git)
  - [第二十五章 还有一些其他任务](#第二十五章-还有一些其他任务)
  - [第二十六章 Git的缺点](#第二十六章-git的缺点)

---

## 第一章 基本概念  

略  

---

## 第二章 入门  

### 2.1 准备git环境  

1. git官网下载安装git  
2. 用config配置git，如配置用户名和邮箱：  

```shell
> git config --global user.email "user@service.site"  
```  

### 2.2 第一个git项目  

fisrt-steps目录下有两个文件，如下图所示：  
![first-steps](./images/2.1_first_steps.png)  

1. 创建版本库

```shell
cd /target/dir/projects/first-steps  
git init  
```

2. 首次提交  

第一步，add文件。  
第二步，commit，完成后会有一个散列值标识本次提交。  

```shell
git add foo.txt bar.txt  
git commit --message "Sample project imported."  
```  

3. 检查状态  

```shell
git status  
```  

用diff显示每个被修改的行  

```shell
git diff your.file  
```  

4. 提交修改  

所有修改都必须先被归档成一次新提交。添加使用add命令，删除使用rm命令。  

```shell
git add your.file1 your.file2  
git rm your.file3  
```

然后提交修改  

```shell
git commit --message "your changes"  
git commit -m "your changes"  
```

5. 显示历史  

```shell
git log  
```

### 2.3 Git的协作功能  

1. 克隆版本库  

```shell
git clone /projects/first-steps /projects/first-steps-clone
```

2. 从另一版本库中获取修改  

在原始库中常见一次新提交：  

```shell
cd /projects/first-steps  
git add foo.txt  
git commit -m "A change in the original."  
```

查看修改日志  

```shell
git log --oneline
```

修改克隆版本库中的文件：  

```shell
cd /projects/first-steps-clone  
git add bar.html  
git commit -m "A change in the clone"  
git log --oneline  
```

把原版本库中的新提交克隆给它的克隆体。  

```shell
cd /projects/first-steps-clone  
git pull  
```

pull命令取回了新的修改，并于克隆体的本地修改进行对比，并在工作区合并了两边的修改，创建了一次新提交。  
该过程就是所谓的合并（merge）。注意：合并可能会带来冲突，然后合并就会失败。图形显示修改log。  

```shell
git log --graph
```

3. 从任意版本库中取回修改  

无参情况下，pull命令旨在克隆版本库中发挥作用。也可以用参数指定任意版本库的路径，以便从某一特定开发分支中
提取相关修改。  
把克隆体中的修改pull到原版本库，代码如下：  

```shell
cd /projects/first-steps  
git pull /projects/first-steps-clone master
```

4. 创建共享版本库  

可以用push命令将提交传送给其他版本库。不过，push命令只适合用于那些没有开发者在上面开展具体工作的版本库。
最好的方法就是创建一个不带工作区的版本库（裸版本库，bare repository），可以使用`clone --bare`选项创建
一个裸版本库。裸版本库通常可被用来充当开发者们传递提交（使用push命令）的汇聚点，以便其他人可以从中拉回他
们所做的修改。  

```shell
git clone --bare /projects/first-steps /projects/first-steps-bare.git
```

5. 用push命令上载修改  

```shell
cd /projects/first-steps 
git add foo.txt  
git commit -m "changes "  
```

把上述修改向共享版本库传送改提交。  

```shell
git push /projects/first-steps-bare.git master
```  

6. Pull命令：取回修改  

让克隆版本库也得到响应的修改

```shell
cd /projects/first-steps-clone  
git pull /projects/first-steps-bare.git master  
```

### 2.4 本章小结  

- **工作区与版本库**：工作区是一个包含 *.git* 子目录中的目录，我们可以用**init**命令在当前目录中
创建版本库。
- **版本提交**：一次版本提交通常定义了版本库中所有文件的一个版本，它详细说明了该版本是由何人在何时何
地创建的。用**add**命令来确定哪些文件被纳入下一次提交，然后用**commit**命令创建新的版本提交。  
- **查看信息**：通过**status**命令，查看哪些文件被修改和将被提交。此外，**log**用来显示提交历史，
**diff**用来显示两个版本文件之间的差异。  
- **克隆**：用**clone**创建的版本库副本被称为克隆体。  
- **推送和拉回**：**push**和**pull**。  

---

## 第三章 提交究竟是什么  

通过`git log --stat -1`查看提交中包含的信息。主要包括：散列值（commit hash）、作者信息、时间、以及修改
内容。  

### 3.1 访问权限与时间戳  

Git会保存每个文件所有的访问权限，但不会保留文件的修改时间。在执行检出操作时，文件的修改时间会被设置为当前
时间。

### 3.2 add命令与commit命令  

通过，提交中会包括当前所有的修改，新增和删除。唯一例外的就是在 **.gitignore**文件中的列出的。  

### 3.3 再谈提交散列值  

- 提交的散列值可以在本地生成。
- 散列值中的信息比单纯的软件版本的名称要多得多。

```shell
# git fsck查看版本库的完整性
git fsck
```

### 3.4 提交历史

略。

### 3.5 一种略有不同的提交查看方法

> 通过diff命令，比较出两次提交之间的差异  
> 1. 两次提交  
> 两次提交之间有一份完整的差异清单，在不提交散列值的情况下，靠指定相关特定的符号名称（分支、标签、HEAD等）也
> 能获取到它。  
> `git diff 77d231f HEAD`  
> 2. 与上一次提交进行比较  
> ```shell
> # 通过使用^!  
> git diff 77d231f^!  
> ```
> 3. 限制文件范围  
> ```shell
> git diff 77d231f 05bcfd1 - book/bisection/  
> ```
> 4. 统计修改情况
> ```shell
> # --stat选项显示文件中的修改数量  
> git diff --stat 77d231f 05bcfd1  
> ```

### 3.6 同一项目的多部不同历史

```shell
# 部分输出  
git log -n 3  # only the last three.  
# 格式化输出： --format, --oneline. --format=fuller可显示更多细节
git log --oneline  
# 统计信息  
git log --shortstat --oneline  
# 图形显示  
git log --graph --oneline  
```

---

## 第四章 多次提交

### 4.1 status

```shell
git status
git status --short
```

输出选项：

- changes to be committed
- changed but not updated
- untracked files

### 4.2 存储在暂存区中的快照

```shell
git diff -staged  # stageing vs. repository  
git diff  # staging vs. workspace  
```

### 4.3 怎样的修改不该被提交

不应提交情况：  

- 调试
- 意外添加
- 尚未准备好
- 自动生成文件

从暂存区中撤回：

```shell
git rest HEAD .  
# or  
git reset HEAD foo.txt /src/test/  
```

应对方法：  

- **reset**重置
- 写入 _.gitignore_

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
git stash

# 恢复  
git stash pop

# 查看  
git stash list

# 查看栈中修改内容  
git stash pop stash@{1}
```

---

## 第五章 版本库

Git主要由两个层面构成。顶层就是我们所用的命令，例如log、reset或commit等；底层我们称之为管道（plumbing）。  

### 5.1 一种简单而高校的存储系统  

git的核心是一个对象数据库，可用来存储文本或二进制数据。  

```shell
# 插入数据  
git hash-object -w hello.txt
# 返回一个40字符的代码，这是被存储对象的键值，利用键值访问对象。
>>>28cf67640e5...
# 访问对象  
git cat-file -p 28cf67640e5  
```

### 5.2 存储目录：Blob与Tree

Git使用了一种包含两种节点类型的简单树结构。

### 5.3 相同数据只存储一次

```shell
# 下面命令返回相同散列值  
git hash-object -w foo.txt  
git hash-object -w copy-of-foo.txt  
```

---

## 第六章 分支

### 6.1 并行式开发

并行式开发会创建分支。  

### 6.2 修复旧版本中的bug

当前版本检测到错误，而新版本又尚不能交付，就会创建基于当前版本的分支。  

### 6.4 当前活跃分支

```shell
# 列出当前分支  
git branch  
# 改变当前分支  
git checkout a-branch  

# 为任意一批提交创建分支  
git branch still-a-branch 28b7da45e  
# 从现有分支中创建分支  
git branch still-a-branch older-branch  

# 创建并切换到新分支  
git checkout -b a-branch
```

Checkout操作被拒绝时怎么办  

```shell
# 提交修改并切换  
git commit --all  
git checkout a-branch  
# 放弃修改并切换  
git checkout --force a-branch  
# 储藏并切换  
git stash  
git checkout a-branch  
```

### 6.6 重置分支指针

```shell
git reset --hard 39er21a
```

### 6.7 删除分支

```shell
# 删除一个已被终止的分支  
git branch -d b-branch  
# 删除一个打开的分支  
git branch -D b-branch  

# 恢复分支，已知散列值  
git branch a-branch 742dcdf  
# 不知散列值  
git reflog # 查找散列值  
git branch b-branch HEAD@{1}  
```

### 6.8 清理提交对象

gc命令可用于清理版本库，移除所有不属于当前分支的提交对象。

---

## 第七章 合并分支

### 7.2 冲突

- 编辑冲突
- 内容冲突
  
### 7.3 编辑冲突

git status中，“Changes to be committed”显示的是自动合并的文件，“Unmerged paths”是用户必须手动
编辑的文件。

### 7.4 冲突标志

```shell
# 设置成三路显示格式  
git config merge.conflictstyle diff3  
```

### 7.5 解决编辑冲突

```shell
# 启动合并工具  
git mergetool  

# 合并出现错误，通过reset取消  
git reset --merge  
```

### 7.6 内容冲突

Git无法识别内容冲突。

- 借助自动化测试构建保护机制
- 使用断言、以及前置与后置条件
- 定义清晰的接口，使其实现松耦合
- 静态类型检查

### 7.7 开进合并

```shell
# 强制快进提交产生一次新的提交  
git merge --no-ff a-branch  
```

### 7.8 第一父级提交历史

```shell
git log --merges  
# 显示第一父级提交历史  
git log --first-parent --oneline R1.0..master
```

### 7.9 棘手的合并冲突

```shell
# a..b可用来标识来源于分支b，但不属于a的提交
git log MERGE_HEAD..HEAD  
# 显示别人做的事情  
git log HEAD..MERGE_HEAD  
# 图形化显示
git log --graph --oneline --decorate HEAD MERGE_HEAD  
# log限制只输出合并提交  
git log --merge  

git merge-base HEAD MERGE_HEAD  # 输出散列值
>>> 3d3bde
git diff --stat 3d3bde HEAD # 我们的更改  
git diff --stat 3d3bde MERGE_HEAD # 他人的修改  
```

### 7.10 终有可行的方式

- 分支重构
- 分小步合并
- 丢弃与捡取
- 评级和测试

---

## 第八章 通过变基净化历史

**rebase**命令。  

- 如果你不小心在错误的分支上执行了一次提交。
- 当多个开发者致力于开发同一软件时，他们会频繁的整合自己的修改。如果不进行变基，可能会创建出钻石链。

### 8.2 避免钻石链

```shell
# Branch "feature-a" is active  
git rebase master  
```

会做下面的事。

- 确认涉及到哪些提交
- 确认目标位置
- 复制提交
- 将活动分支重置

### 8.3 什么情况下会遇到冲突呢

如果rebase命令在执行过程中遇到冲突，相关文件会出现冲突标志。需要对文件进行清理，并重新将他们添加到
暂存区，然后再执行rebase命令加--continue选项，从该点继续之前的进程。也可以用--abort选项取消这次的
rebase命令，或者--skip选项跳过引起冲突的提交。

### 8.4 移植分支

```shell
# Branch "feature-a" is active  
git rebase master --onto release1  
```

### 8.5 执行变基后原提交的情况

原件依然还可以通过散列值来访问。

### 8.7 捡取

```shell
git cherry-pick 23dfjk33
```

- cherry-pick不会参考历史纪录
- 捡取操作有时候会被用来将一些小bug的修复传递到各种不同的发行版中。
- 该操作的另一种应用是从即将删除的分支中转移出有用的提交。
- 警告：捡取操作有可能会引发重复提交问题。

---

## 第九章 版本库间的交换

### 9.1 克隆版本库

- 开发者需要至少一个克隆版本库才能用Git开展工作。
- 通常我们需要一份克隆体充当中央版本库。
- 多点开发条件下，每个开发点都会有一份属于自己的主克隆版本库，用于定期与各点的克隆版本比较。
- 对于与主项目不同方向的独立开发，通常也必须要克隆一份版本库来用，简称为分叉（fork）。
- 作为防止意外损坏的备份。
- 与Git相关的操作工具通常也会要求使用独立的克隆版本库。

通常情况下Git创建版本库之后会直接签出工作区。可以用--bare选项创建一个不带工作区的版本库。

### 9.2 如何告知Git其他版本库的位置

```shell
# 克隆本地库  
git clone /Users/path/git-book.git  
# 不同来源的版本库  
git clone file:///Users/path/git-book.git  
# 还有其他协议，ssh  
git clone ssh://user@server.com:git-book.git  
# 此外还有http、https、ftp、ftps和rsync，或者git的专有协议  
```

### 9.3 给别处的版本库起个名字

```shell
git remote add myClone file:///tmp/git-book-clone.git
# 当某个版本库被克隆时，Git会自动将原版本库路径的路径存储为它的源版本库。  
git remote --verbose  # 显示用于推送或获取的路径  
# 删除昵称  
git remote rm myClone  
```

### 9.4 获取数据  

```shell
# 获取其他版本库中所有分支中尚未再本地版本库中存在的提交  
git fetch myClone
```

### 9.5 远程跟踪分支：监控其他分支

```shell
# 存在着两种类型的分支，本地的和被远程跟踪的。  
git branch -r  
# 对比版本不同  
git diff feature-a clone/feature-a  
# 查看远程版本的新增提交  
git log --oneline feature-a..clone/feature-a  
# 从远程跟踪分支中分岔出一个本地分支  
git checkout -b feature-b clone/feature-b  
```

### 9.6 利用本地分支操作别处的版本库

```shell
# clone feature-b到本地，如果本地不存在my-feature-b的库，就创建它，如果有更新它  
git fetch clone feature-b:my-feature-b
```

### 9.7 Pull = Fetch + Merge

```shell
git pull
```

### 9.8 讨厌钻石链的人：请用--rebase选项

```shell
git pull --rebase
```

### 9.9 Push: Pull的反面

```shell
git push clone feature-a
```

- 写访问：push只能用在我们对其他版本有写访问权限时
- 只针对快进合并：push操作通常不会带来合并。
- 无远程跟踪分支。
- 无参数调用push：在无参数的情况下，push命令将只发送那些在其他版本库中有相同名字匹配的本地分支。与之不同的是
pull和fetch所选取的都是全部分支。

> **推送被拒绝后，下一步怎么做**
> 1. 找到冲突  
> `git push clone feature-a`  
> 2. 改变分支  
> `git checkout feature-a`  
> 3. 执行一次拉取操作  
> `git pull`  
> 4. 在必要情况下，清理合并冲突  
> `git mergetool`  
> `git commit -all`  
> `git checkout feature-a`  
> 5. 重新推送  
> `git push clone feature-a`  

### 9.10 命名分支

```shell
git pull clone feature-a:favorite-feature
# pull命令从clone版本库中导入了feature-a分支，并命名成favorite-feature
```

> **删除远程版本库中的分支**  
> 1. 删除远程版本库中的分支  
> `git push clone :feature-a`  
> 2. 必要的情况下，也要删除本地的相应分支  
> `git branch -d feature-a`  

---

## 第十章  版本标签

### 10.1 创建标签

> **标签化某次提交**  
> 1. 创建一个普通标签  
> `git tag 1.2.3.4 master -m "Freshly built."`  
> 2. 推送某单一标签  
> `git push origin 1.2.3.4 `  

用--tags参数，推送分支标签。

```shell
git push --tags  
```

添加GnuPG标签，前提是git中输入了默认email地址，同时该账户也是注册GnuPG时所用的用户ID。

```shell
git tag 1.2.3.4 master -s -m "Signed."
```

### 10.2 当前究竟存在哪些标签

```shell
git tag -1 1.2.*
```

### 10.3 打印标签的散列值

```shell
git show-ref --dereference --tags
```

### 10.4 将标签添加到日志输出中

```shell
git log --oneline --decorate
```

### 10.5 究竟在哪个版本里呢

```shell
git tag --contains f63cd72  
git log --oneline 1.2.3.3 | grep "a comment"
```

### 10.6 如何修改标签呢

建议不去修改它。

### 10.7 当我们需要一个浮动标签时

应该使用一个分支，而不是标签。

---

## 第十一章  版本库之间的以来

在Git中版本库是发行单位，代表的是一个版本，而分支或标签则只能被创建在版本库这个整体中。对于主项目与子项目之间的关系，可以通过Git中的**submodule**或**subtree**命令实现。  
子模块和子树这两个概念之间的主要区别在于：带子模块的主版本库只能发布模块版本库，而模块版本库的内容中带有子树的话，该模块版本库就被导入了主版本库中。

略。

---

## 第十二章  技巧

略。

---

## 第十三章  工作流简介

略。

---

## 第十四章  项目设置

工作流具体包含如下内容：

- 如何将项目目录转换为一个版本库
- 如何版本化空目录
- 如何处理行尾终止问题
- 中央版本库有哪些服访问选项可用，它们应该如何设置
- 团队成员应该如何访问中央版本库

### 14.1 概述

工作流分成两个步骤：1、为项目创建相应的版本库；2、为所有开发者提供一个可用的中央版本库。  
目前Git支持了集中不同协议的变体：

- __file__：经由共享网络设备访问的协议。
- __git__：专用服务器服务的网络通信协议。
- __http__：经由Web服务器访问的协议。
- __ssh__：经由安全壳架构访问的协议。

在实际例子中，我们常常会为匿名读取访问配置HTTP协议，为写访问配置SSH协议。

### 14.2 使用要求

- __共享服务器__：对于Git的协同环境，我们可以选择某种共享网络设备，也可以选择一台启动相关服务的服务器，或者选择一台支持CGI或SSH基架构的Web服务器。
- __分配项目级权限__：Git只能识别版本库整体的读写权限，不能将权限细化到单个目录。

### 14.3 工作流简介：设置项目

将项目目录导入到一个新的版本库中，并让该版本库来充当中央版本库。

### 14.4 执行过程及其实现

#### 14.4.1 基于项目目录创建一个新的版本库

- 准备空目录

```shell

cd projecta/EmptyDir
touch .gitignore
# 在 .gitignore 中插入一个带“*”的行，表示该目录中的所有文件都将被忽略
echo "*" > .gitignore
```

- 忽略不需要的文件和目录

```shell
# TempDir目录下所有扩展名为.bak的文件都会被忽略
/TmepDir
*.bak
```

- 创建一个版本库
  
```shell
cd projecta
git init
```

- 定义行尾终止符

> Git对于行尾结束符主要有三种不同的处理方式   
> core.autocrlf false: 该方案会忽略行尾结束符。  
> core.autocrlf true: 该方案会（用LF）执行标准化，但也会根据相应的平台来回切换。  
> core.autocrlf input: 该方案在引入标准化（LF）时不会调整行尾结束符，当会将其来回切换。  
> Windows系统，应设为true；Unix系统上首次导入前应设置为input。  

设置core-autocrlf成input

```shell
git config --global core.sutocrlf input
```

- 导入文件

```shell
git status
git add .
git commit -m "init"
```

- 创建一个裸版本库

```shell
git clone --bare projecta projecta.git
```

#### 14.4.2 以文件访问的方式共享版本库

- 复制裸版本库

```shell
cp -R projecta.git /shared/gitrepos/.
```

- 克隆中央版本库

```shell
git clone /shared/gitrepos/projecta.git
# or 
git clone file:///shared/gitrepos/projecta.git
```

- 管理读写权限

在这里，对版本库的读写访问是由文件系统来管理的。

#### 14.4.3 用Git daemon来共享版本库

- 为git daemon准备好相应的版本库

```shell
cd projecta.git
touch git-daemon-export-ok
```

- 启动git daemon

```shell
git daemon
# 具体的url如下：
# git://server-42/shared/gitrepos/projecta.git

# 设置基本路径
git daemon --base-path=/shared/gitrepos
# 可以用'git://server-42/projecta.git'来访问该版本库
# 默认daemon导出来的版本库往往只有读取权限。
# 打开写权限命令如下：
git daemon --base-path=/shared/gitrepos --enable=receive-pack
```

- 克隆中央版本库

```shell
git clone git://server-42/projecta.git
```

- 管理读写访问权限

版本库的读写访问权限不能由开发者各自来单独定义。

#### 14.4.4 用HTTP协议来共享版本库

- 启用Apache2中的相关模块

```shell
# 加载模块
LoadModule cgi_module libexec/apache2/mod_cgi.so
LoadModule cgi_module libexec/apache2/mod_alias.so
LoadModule cgi_module libexec/apache2/mod_env.so
```

- 允许对CGI脚本进行访问

```html
<!--
假定CGI脚本位于'/usr/local/git-core'
# 给Apache2赋予调用权限
-->
<Directory "/usr/local/git-core">
  AllowOverride None
  Options None
  Order allow,deny
  Allow from all
</Directory>
```

- 赋予HTTP协议访问版本库权限

```shell
cd /shared/gitrepos/projecta.git
touch git-daemon-export-ok

# 在httpd.conf文件中指定带导入版本库所在的根目录
SetEnv GIT_PROJECT_ROOT /shared/gitrepos

# 为CGI脚本设置一个别名，如'./git'
ScriptAlias /git/ /usr/local/git/libexec/git-core/git-http-backend/

# 重启Apache2之后，就可以访问'/shared/gitrepos'目录下的所有版本
```

- 克隆中央版本库

```shell
git clone http://server-42/git/projecta.git
```

- 管理读写访问权限

```html
<!-- 
  读写访问权限可以用一般Web服务器的访问权限来定义。
  写权限的配置如下：
  有了这个配置项，每次push命令所发出的请求都会交由git-receive-pack处理
 -->
<LocationMatch "^/git/.*/git-receive-pack$">
  AuthType Basic
  AuthName "Git Access"
  AuthUserFile /shared/gitrepos/git-auth-file
  Require valid-user
</LocationMatch>
```

```html
<!--
  将某个版本库读写都纳入密码保护，需要配置如下
-->
<LocationMatch /git/projecta.git>
  AuthType Basic
  AuthName "Git Access"
  AuthUserFile /shared/gitrepos/git-auth-file
  Require valid-user
</LocationMatch>

```

#### 14.4.5 用SSH协议来共享版本库

- 复制裸版本库

```shell
scp -r projecta.git server-42:/shared/gitrepos/projecta.git
```

- 克隆中央版本库

```shell
git clone ssh://server-42:/shared/gitrepos/projecta.git
# or
git clone server-42:/shared/gitrepos/projecta.git
```

- 管理读写访问权限

版本库的读写权限由掌管SSH服务和文件系统权限管理员来管理。

### 14.5 何不换一种做法

- 何不放弃推送操作

通常在一个开源项目中，我们往往使用的是一个纯拉取的动作序列。所有开发者只在自己版本库中完成相关的工作，并且只有负责整合的人员（集成负责人，integrator）才有更新中央软件版本的权限。

---

## 第十五章 相同分支上的开发

本章介绍的工作流包含如下内容：

- 如何在本地的master分支上进行开发工作
- 如何将自己的成果发布到中央版本库
- 如何让其他开发者使用这些成果

### 15.1 概述

略。

### 15.2 使用要求

略。

### 15.3 工作流简述：相同分支上的开发

本章的工作流中，所有开发者都将现在本地版本库的同一分支上开展工作，然后将工作结果合并到中央版本库的master分支上去。

### 15.4 执行过程及其实现

- 在master分支上操作

```shell
# 1 更新master分支
# 去中央版本库获取最新版本，并保证本地提交不会被传送给中央版本库
git pull --ff-only

# 2 进行本地更改
# 在进入下一步步骤前需要提交
git commit -m "Method X revised"

# 3 将中央版本库中发生的修改合并到本地修改中
git pull

# 4 将本地修改上传到中央版本库
git push
# 如果中央版本库有更新，可以用reset命令可以把之前的提交删除掉
git reset --hard ORIG_HEAD
# 然后再用pull从中央版本库获取更改
```

### 15.5 何不换一种做法

- 用变基来代替合并

```shell
# 采用变基的方式，将中央版本库中的修改合并到本地
git pull --rebase
# 如果工作中会大量使用变基操作，可以将其配置成pull命令的默认行为
git config branch.master.rebase true
# 其中分支名（master）可以被替换成任何其他的分支名
```

---

## 第十六章 基于特性分支的开发

本章将详细介绍特性分支的使用，以便我们：

- 能轻松定位实现了某一特性的提交
- 且让master分支上的第一父级历史中只保留能充当发行版本文档的粗粒度提交
- 并行特性的交付也成为了可能
- 以及master上所发生的重大变更也能在特性开发期间使用

### 16.1 概述

合并操作必须要在master分支上发起，并且不能使用快进式合并，这样就能在master分支上得到一个清晰的第一父级历史，因为该分支上将只包含特性分支的合并提交。

### 16.2 使用要求

- **基于特性的开发方略**：项目计划或产品计划必须要立足于特性开发，即项目中的各种功能性需求要能被转化成相应的特性工作包。
- **特性的小型化**：即一个特性必须要能在几小时或者几天内开发完成。费时较长的特性开发会与其他部分的开发并行运作，这种情况下，特性集成的成本越高，其带来的风险就越大。
- **在本地执行回归测试**：将新特性提交给master分支之前，应先在自己的开发机器上进行本地的回归测试。检查一下该特性所带来的变更是否与其他特性兼容，以及是否有我们不希望看到的副作用。

### 16.3 工作流简介：基于特性分支的开发

先用独立的专用分支来开发各个特性或进行错误修复，然后在特性开发或错误修复完成之后将其合并到master分支上去。

### 16.4 执行过程及其实现

一旦使用了特性分支，本地版本库中往往会存在多个分支。在没有参数情况下，push命令只会将当前活动分支中的内容传送给远程版本库。可以通过设置'push.default'来更改这一行为

```shell
git config push.default upstream
```

该选项的默认值匹配所有与远程版本库中有相同分支的本地分支，因此我们每次执行push命令时必须明确指定分支。

#### 16.4.1 创建特性分支

```shell
# 1 更新master分支
git checkout master
git pull --ff-only
# --ff-only表示只允许快进式合并，如果这时存在本地修改，该合并操作就会被取消

# 2 创建特性分支
git checkout -b feature-a

# 3 (可选)在中央版本库上维护特性分支
git push --set-upstream origin feature-a
# --set-upstream参数将本地的特性分支何远程版本库中的新分支连接起来，这样执行push和pull就可以免去显式指定远程分支。
# 后面直接push就可以了
git push
```

#### 16.4.2 在master分支上继承某一特性

相关的合并必须始终在master分支上执行。

```shell
# 1 更新master分支
git checkout master
git pull --ff-only

# 2 合并特性分支
git merge feature-a --no-ff --no-commit

# 3 做一下回归测试，并为其创建一次提交
# 如果测试缺失引发了错误，用reset命令丢弃当前执行的这次合并
git reset --hard HEAD
# 如果测试没有问题，直接提交
git commit -m "Delivering feature-a"

# 4 将master分支传递给中央版本库
git push
# 如果出现错误，可能是其他特性已经被集成进来。通常时先执行一下pull，将其修改合并到本地，执行pull命令后第一级副理事就不能再发挥作用了
# 但第一父级历史中应该要纳入所有的特性，所以push命令失败后，本地特性分支上的合并田炯必须要用reset命令移除掉
git reset --hard ORIG_HEAD
# 然后再从第一步开始再执行一遍之前的操作。

# 5 删除或继续使用该特性分支（二选一）
# 5.1 删除该特性分支
git branch -d feature-a
# 如果被删除的特性分支再中央版本库中有对应的维护分支，则那边的分支也会被删除。
git push origin :feature-a
# 5.2 继续特性开发
git checkout feature-a
```

#### 16.4.3 将master分支上所发生的修改传递给特性分支

```shell
# 1 更新master分支
git checkout master
git pull --ff-only

# 2 将修改引入到特性分支中
git checkout feature-a
git merge --no-ff master
```

|Git-Flow: 高级的OperationsGit Flow。  
|`git flow feature start feature-a`  
|`git flow feature finish feature-a`

### 16.5 何不换一种做法

略。

---

## 第十七章 二分法排错

- 如何有效的用二分法找出引发问题的提交
- 如何用二分法实现自动化排错

### 17.1 概述

略。

### 17.2 使用要求

- 可重现的错误检测
- 误差检测的成本不能太高

### 17.3 工作流简介：二分法排错

略。

### 17.4 执行过程及其实现

#### 17.4.1 用二分法人工排错

```shell
# 1 定义错误标志

# 2 分别找出没问题和有问题的提交

# 3 执行二分法排错
git bisect start 202d25d 87ac59e  # 最后分别代表有问题、无问题提交的散列值
# 接下来位于这两个提交之间的提交会被激活
# 执行检测，用一下命令对当前提交进行标志
bisect good  # 错误不在其中
bisect bad  # 错误不在其中
bisect skip  # 当前提交无法被测试。

# 4 停止或取消二分查找
git bisect reset
```

#### 17.4.2 用二分法自动排错

```shell
# 1 定义错误标志

# 2 准备好测试脚本
# 准备测试shell脚本，根据错误是否存在情况范围不同的推出码
# Exit code 0: 没找到错误，标识为"good"
# Exit code 1-124, 126, 127: 错误被找到，标识位"bad"
# Exit code 125: 测试未被执行，二分查找直接跳过该提交。

# Tips： 测试要在一个新文件中实现，它不应被Git纳入版本控制。

# 3 分别找出没问题和有问题的提交

# 4 执行二分法的自动化排错
git bisect start 202d25d 87ac59e  # 最后分别代表有问题、无问题提交的散列值
git bisect run ./bisect-test.sh

# 5 完成二分查找操作
git bisect reset
```

### 17.5 何不换一种做法

- 何不用合并操作将测试脚本添加到旧提交中去

将测试脚本纳入到一个新分支中，在该二分查找的shell脚本中，二分查找进程会在每次测试运行之前将bisect-test分支合并到当前提交中，然后用--nocommit选项防止其变成一个永久性提交。  
然后测试完成后，再用reset命令重置掉合并操作。  
操作序列和示例脚本可以在bisect命令的在线文档的Example一节中找到。  

---

## 第十八章 基于构建服务器的工作

- 当前版本的构建与定期测试
- 开发者可以随时拿最后成功测试的版本与他们工作区的内容进行比对
- 创建一份记录成功的版本历史，以供日后排错只用

### 18.1 概述

在构建服务器中，我们通常会设置两个分支。last-build分支会直接只想master分支中最后构建成功的那个版本；buildhistory分支中则将会包含该软件所有被成功构建的版本。

### 18.2 使用要求

- 中央版本库
- 持续性继承
- 构建服务器
- 测试套件

### 18.3 工作流简述：基于构建服务器的工作

略。

### 18.4 执行过程及其实现

#### 18.4.1 预备构建服务器

```shell
# 1 创建一个空的版本库
mkdir buildrepo
cd buildrepo
git init

# 2 获取中央版本库master分支
git remote add -t master origin <central repo>
# -t master: 表示只有master分支在将来执行fetch和pull命令时被自动船速
# orgin: 表示新增远程版本库的名称。我们选择了目标相同的远程名称，以便clone命令也能使用这个名称
# <central repo>: 表示连接到中央版本库的url
git fetch

# 3 创建一个build-history分支
# 找到第一次提交
git log --oneline --first-parent origin/master | tail -1
# 构建build-history，并激活它
git checkout -b build-history 3a05e36
```

#### 18.4.2 构建服务器上的Git

```shell
# 1 获取中央版本库中的修改
git fetch

# 2 检查是否存在构建请求
git diff --shortstat --exit-code origin/master

# 3 清理工作区
git reset --hard HEAD
# or 
git clean --force

# 4 将修改纳入到本地build-history分支中
git merge --no-ff --no-commit origin/master

# 5 完成构建

# 6 完成提交
git commit -m "build <build-number>"

# 7 标记最后一次被成功构建的版本
# 用branch命令创建一个新的last-build或者现有的，使其只想origin/master
git branch --force last-build HEAD^2
# 传递到中央版本库的last-build
git push --forece origin last-build:last-build
```

#### 18.4.3 对比本地开发版本库与最后成功构建版本库之间的差异

```shell
# 1 检查中央版本库中的提交
git log origin/last-build..origin/master
git diff origin/last-build origin/master

# 2 反思本地提交
git diff origin/last-build
```

#### 18.8.4 基于构建历史的排错

```shell
# 1 连接到构建版本库
git remote add build <build-repo-url>

# 2 搬运构建历史
git fetch build

# 3 构建一个本地分支
git checkout -b history build/build-history

# 4 执行bisect命令
git bisect start HEAD <good-commit>
git bisect good
# or
git bisect bad

# 5 解释结果
git log <bad-commit>^1^2..<bad-commit>^2

# 6 清理
git bisect reset
git checkout master
git branch -D build-history
git remote rm build
```

### 18.5 何不换种做法

- 使用标签
- 构建历史放在中央版本库中

---

## 第十九章 发行版交付

- 产品发行版支持打补丁的功能
- 在代码冻结阶段并行开发新版本的可能
- 确保在开发阶段能以补丁形式修复所有错误，或则测试阶段的工作能回流到开发阶段
- 发行版的历史以及补丁的历史记录要能很容易的被访问
- 发行版与开发版之间的对比工作也要很容易进行

### 19.1 概述

略。

### 19.2 使用要求

- 产品发行版只有一个
- 开发的稳定性
- 发行版的完整性

### 19.3 工作流简述：“发行版交付”

略。

### 19.4 执行过程及其实现

#### 19.4.1 预备阶段：创建stable分支

```shell
git checkout stable
git log --first-parent -oneline

# 1 确认首次提交的位置
git log --oneline --first-parent | tail -1

# 2 创建stable分支
git branch stable 3a05e25
```

#### 19.4.2 预备并创建发行版

```shell
# 1 创建codefreeze分支
git checkout -b codefreeze master

# 2 稳定codefreeze分支
git checkout master
git merge codefreeze

# 3 创建发行版
git log codefreeze..stable --oneline
# 注释明确表示一下这个发行版的新提交
git checkout stable
git merge codefreeze --no-ff -m "Release-2.0.0"
# 为发行版创建一个新的标签
git tag -a release-2.0.0 -m "Release-2.0.0"
# 最后删除codefreeze，其只存在于项目的稳定阶段
git branch -d codefreeze

# 4 更新master分支
git checkout master
git merge stable -m "Nach Release-2.0.0"
```

#### 19.4.3 创建补丁

```shell
# 1 创建hotfix分支进行排错
git checkout -b hotfix-al stable

# 2 验证补丁被并行化创建的可能性
git log hotfix-al..stable --oneline
git rebase stable

# 3 发布补丁
git checkout stable
git merge hotfix-al --no-ff -m "Hotfix-Release-2.0.1"
git tag -a release-2.0.1 -m "Hotfix-Release-2.0.1"

# 4 在其他分支上接受补丁所做的修改
# 代码冻结阶段
git checkout codefreeze
git merge stable -m "Hotfix 2.0.1"
git checkout master
git merge codefreeze -m "Hotfix 2.0.1"
# 代码没冻结阶段
git checkout master
git merge stable -m "Hotfix 2.0.1"
```

### 19.5 何不换一种做法

- 为什么不能只用标签
- 何不干脆不使用标签
- 为什么不能用快进式合并
- 为什么卜直接在stable分支上实现补丁

---

## 第二十章 拆分大项目

- 只有该模块所需要的文件被导入到新版本库
- 模块文件历史将被保留在新版本库中
- 模块可以作为外来模块再次被集成到主项目中

### 20.1 概述

略。

### 20.2 使用要求

- 项目内部需要模块化时
- 模块文件被分置于不同的目录中时

### 20.3 工作流简述：“拆分大项目”

略。

### 20.4 执行过程及其实现

```shell
git clone --no-hardlinks --bare project.git project.backup.git
```

#### 20.4.1 拆分模块版本库

```shell
# 1 克隆主版本库
git clone --no-hardlinks --bare project.git modul3-work.git

# 2 删除无用的文件和提交
# 以下示例filter-branch命令删除src/module1目录下内容
cd module3
git filter-branch --force --index-filter \
    'git rm -r --cached --ignore-unmatch src/module' \
    --tag-name-filter cat --prune-empty -- --all

# 3 删除无用的分支和标签
git tag -d v1.0.1
git branch -D v2.0_bf

# 4 缩减模块版本库的规模
git clone --no-hardlinks --bare module3-work.git module3.git
rm -rf modul3-work.git

# 5 定制模块版本库文件架构
git clone module3.git module3
cd module3
mv src/module3 module3
rmdir src
mv module3 src
mv test/module3 module3
rmdir test
mv module3 test

git add --all
git commit -m "Directory structure adapted"
git push

# 6 在主项目中删除已被拆分出来的模块目录
```

#### 20.4.2 将拆分出的模块作为外部版本库集成

```shell
git submodule add /global-path-to/module3.git extern/module3
git add -all
git commit -m "Module3 added"
```

### 20.5 何不换一种做法

- 采用一个全新的版本库
- 为什么不采用--subdirctory-filter选项

---

## 第二十一章 合并小型项目

- 保留所有文件的历史版本
- 保留所有版本库的标签

### 20.1 概述

略。

### 20.2 使用要求

- 不同的标签

### 20.3 工作流简介：“合并小项目”

略。

### 20.4 执行过程及其实现

```shell
# 1 创建一个主版本库
git clone backend common
cd common

# 2 将文件移到改目录专属文件目录下
mkdir backend
git mv src test backend
git commit -m "backend directory created"

# 3 导入另一个版本库
cd common
git remote add ui ../ui/
git fetch ui

# 4 将导入的文件移到该目录专属文件目录下
git checkout -b uimaster ui/master
mkdir ui
git mv src test ui
git commit -m "ui directory created"

# 5 合并项目
git checkout master
git merge uimaster
git log --graph --oneline
git branch -d uimaster
```

### 21.5 何不换一种做法

- 为什么不直接合并，跳过创建项目文件目录

---

## 第二十二章 外包长历史纪录

- 新项目版本库占用较少的资源
- 依然可以使用log、blame和annotate命令搜索历史版本提交

### 22.1 概述

- grafts文件配置
- filter-branch操作
- alternates操作

### 22.2 使用要求

- 一致切断时
- 项目历史罕有需要
- 提交的散列值不被在意

### 22.3 工作流简述：“外包长历史记录”

略。

### 22.4 执行过程及其实现

#### 22.4.1 外包项目历史

```shell
cd project.git
git log --pretty=oneline

# 1 创建移植标签
git tag -a grafts/master
# 2 创建一个克隆
cd ..
git clone --bare project.git temp-project.git

# 3 通过grafts文件来转换历史
cd temp-project.git
echo 79puipipfs > info/grafts
git log --pretty=oneline

# 4 永久性的改变版本库
git filter-branch --tag-name-filter cat --all

# 5 缩小版本库
git clone --bare temp-project.git new-project.git
rm -rf temp-project.git
cd new-project.git
git gc --prune
```

#### 22.4.2 链接到当前活动版本库

```shell
# 1 克隆档案版本库
git clone --bare project.git archive-project.git

# 2 链接档案版本库
cd new-project
echo /gitrepos/archive-project.git/objects >> .git/objects/info/alternates

# 3 连接到历史版本
git show grafts/master --pretty=oneline
tag grafts/master
echo 686yiyi 79997ouououou > ./git/info/grafts
git log --pretty=oneline
```

### 22.5 何不换一种做法

- 为什么不获取档案版本库

---

## 第二十三章 与其他版本控制系统并行使用

- 即使技术无法通信到中央版本库，也可以本地提交
- 可以细粒度地划分版本，即使开发中的中间产品，版本管理成为开发过程中的安全保障
- 可以专为产品原型何新功能开发工作一一分配对应的本地分支
- Git更好的支持合并何变基操作

- 中央版本中的新变化可以被导入本地Git版本库
- 本地提交的修改可以被传输到中央版本库中

### 23.1 概述

略。

### 23.2 使用要求

- 支持乐观锁
- 支持忽略文件和文件目录
- 项目目录的灵活性

### 23.3 工作流简介：“与其他版本控制系统并行使用”

略。

### 23.4 执行过程及其实现

- 如何从版本控制器中获取初始代码 csv checkout命令
- 版本控制系统中元数据是如何在何处储存的 CSV文件目录
- 如何在版本管理中忽略某些文件 .csvignore文件
- 如何在中央版本管理中得到最新的修改 csv add命令
- 如何将修改提交到中央版本中 csv commit

#### 23.4.1 初始部署版本库

```shell
# 1 创建同步版本库
cd csvproject
git init

# 2 配置.gitignore文件
echo CSV/ > .gitignore

# 3 配置.csvignore文件
echo .git >> .csvignore
echo .gitignore >> .csvignore
csv add .csvignore
csv commit

# 4 在同步版本库中添加文件
git add .
git commit -m "Initial import of CSV"

# 5 在同步版本库中创建一个csv分支
git checkout -b csv

# 6 创建工作版本库
cd ..
git clone csvproject gitproject
```

#### 23.4.2 得到中央版本控制管理中的更新修改

```shell
# 1 将修改过的文件传输到同步版本库
cd csvproject
csv update
git add -all .
git commit -m "Changes from CSV"

# 2 提交修改到工作版本库
cd gitproject
git fetch origin

# 3 将修改应用到主分支
git merge origin/csv
```

#### 23.4.3 将修改提交传输到中央版本控制系统

```shell
# 1 获得中央版本控制系统中最新的版本

# 2 主分支上的修改传输到同步版本库
cd gitproject
git push

# 3 在csv分支上接受修改
cd csvproject
git merge --no-commit --no-ff master

# 4 将修改传输到中央版本控制系统
csv commit
git reset --hared HEAD

# 5 从中央版本中获取更i性能
csv update

# 6 在csv分支执行提交操作
git add .
git commit -m "Changes from git recorded"

# 7 更新工作版本库的主分支
cd gitproject
git fetch origin
git merge origin/csv
```

### 20.5 何不换一种做法

- 为什么不选择一个Git版本库

---

## 第二十四章 迁移到Git

略。

---

## 第二十五章 还有一些其他任务

略。

---

## 第二十六章 Git的缺点

- 高复杂度
- 复杂的子模块
- 大型二进制文件的资源消耗
- 版本库只能作为一个整体被处理
- 版本库只能作为整体被授权
- 能用于历史分析的图形化工具偏弱
