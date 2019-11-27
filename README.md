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

