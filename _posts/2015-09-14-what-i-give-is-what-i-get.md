---
layout: post
title: How to Build a Blog
date: 2017-10-28
categories: blog
tags: [总结、经验]
description: 
---


## 购买域名
godaddy购买域名
1.查你想要的域名
2.查到合适的域名后选择“添加到购物车”
3.确认购买 修改购买年限
4.结算。登陆或注册界面，填完必要信息后，选择用支付宝结算
5.激活 买完域名后到邮箱查看激活邮件，否则域名无法激活

## 安装准备软件
依次下载安装
-  [Node.js](https://nodejs.org/en/)
-  [Git](https://git-scm.com/)

## 怎样打开Git
### Win平台操作
 - 1.开始菜单Git Bash
 - 2.鼠标右键打开Git Bash
### Mac平台操作
安装Git之后可直接在Terminal操作

## 注册GitHub
- 访问[GitHub](https://github.com/)
- 注册(邮箱十分重要，许多重要通知都通过邮箱发送)

## 配置SSH keys
我们如何让本地 git 项目与远程的 GitHub 建立联系呢？用 SSH keys。
### 检查 SSH keys的设置
首先我们需要检查你电脑上现有的 ssh key：
```
$ cd ~/.ssh 检查本机的ssh密钥
```
如果提示：No such file or directory 说明你是第一次使用 git。
### 生成新的 SSH Key
```
$ ssh-keygen -t rsa -C "邮件地址@youremail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):<回车就好>
```
注意：此处的邮箱地址，你可以输入自己的邮箱地址
然后输入密码
```
Enter passphrase (empty for no passphrase):<输入加密串>
Enter same passphrase again:<再次输入加密串>
```
![看到这个就设置好了！](http://upload-images.jianshu.io/upload_images/8613291-7349657c3c05ef47.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
###将SSH keys 添加到github
在本机设置 SSH Key 之后，需要添加到 GitHub上，以完成 SSH 链接的设置。
- 1、打开本地 id_rsa.pub 文件（ 参考地址 C:\Documents and Settings\Administrator.ssh\id_rsa.pub）。此文件里面内容为刚才生成的密钥。如果看不到这个文件，你需要设置显示隐藏文件。准确的复制这个文件的内容，才能保证设置的成功。
- 2、登陆 GitHub 系统。点击右上角的 Account Settings—>SSH Public keys —> add another public keys
- 3、把你本地生成的密钥复制到里面（ key 文本框中）， 点击 add key 就可以了 
![](http://upload-images.jianshu.io/upload_images/8613291-8cdb8b47408b9491.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
输入下面的指令检测是否设置成功
```
$ ssh -T git@GitHub.com
```
如果你看到了：
The authenticity of host 'GitHub.com (207.97.227.239)' can't be established. RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48. Are you sure you want to continue connecting (yes/no)? 
输入yes即可
然后你就会看到
Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.
这样的话就设置成功了，你已经可以通过 SSH 链接到 GitHub 了，还有一些个人信息需要完善的。

Git 会根据用户的名字和邮箱来记录提交。GitHub 也是用这些信息来做权限的处理，输入下面的代码进行个人信息的设置，把名称和邮箱替换成你自己的，名字必须是你的真名，而不是GitHub的昵称。
##修改个人信息
```
$ git config --global user.name "cnfeat"//用户名
$ git config --global user.email  "cnfeat@gmail.com"//*填写自己的邮箱*
```
### Fork别人的仓库
![](http://openmindclub.qiniudn.com/omt/BuildBlog019.jpg)
- 点击fork
- 点击setting，修改Repository name，格式是格式是：用户名.github.io
### 在浏览器中搜索“用户名.github.io”即可看到自己的博客










