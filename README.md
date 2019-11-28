# Git: Distributed Version Control Fundamentals and Workflows  
Git学习指南  
图书阅读摘记  

## 目录  

- [Git: Distributed Version Control Fundamentals and Workflows](#git-distributed-version-control-fundamentals-and-workflows)
  - [目录](#目录)
  - [第一章 基本概念](#第一章-基本概念)
  - [第二章 入门](#第二章-入门)
    - [准备git环境](#准备git环境)
    - [第一个git项目](#第一个git项目)
    - [Git的协作功能](#git的协作功能)

## 第一章 基本概念  
略  

## 第二章 入门  
### 准备git环境  
1. git官网下载安装git  
2. 用config配置git，如配置用户名和邮箱：  
`$ git config --global user.email "user@service.site"`  
### 第一个git项目  
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
`$ git status`  
用diff显示每个被修改的行  
`$ git diff your.file`  

4. 提交修改  
所有修改都必须先被归档成一次新提交。添加使用add命令，删除使用rm命令。  
`$ git add your.file1 your.file2`  
`$ git rm your.file3`  
然后提交修改  
`$ git commit --message "your changes"`  
`$ git commit -m "your changes"`  

5. 显示历史  
`$ git log`  

### Git的协作功能  
1. 克隆版本库  
`$ git clone /projects/first-steps /projects/first-steps-clone`  
2. 从另一版本库中获取修改  
在原始库中常见一次新提交：  
```shell
$ cd /projects/first-steps  
$ git add foo.txt  
$ git commit -m "A change in the original."  
```  
查看修改日志  
`$ git log --oneline`  
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
该过程就是所谓的合并（merge）。注意：合并可能会带来冲突，然后合并就会失败。  
图形显示修改log。  
`$ git log --graph`  

