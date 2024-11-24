# Git

## git 概念
. 本地版本控制
. 集中版本控制
. 远端版本控制
![](assets/17321190223971.png)
![git repository概念](assets/17321190995430.png)

## 本地搭建git仓库步骤
### 一、安装git，brew install git
    1、brew install git,安装后的位置在/Users/计算机用户名目录下
    2、安装完成后，在终端输入git --version查看版本号

### 二. Git配置
    1、git config --global user.name "levi"
    2、git config --global user.email "1zhenweilevi@gmail.com"
    3、查看是否成功？git config --global --list

配置成功
![](assets/17323734952385.png)

git config --local 作用域小,仅对当前项目有效
git config --global 作用域中，对当前用户有效
git config --system 作用域大，对整台计算机用户都有效

### 配置远程仓库
SSH git@github.com:momolevi/JavaPrivateSpace.git
![创建新仓库](assets/17323736740878.png)

![准备生成public key](assets/17323739408133.png)
git remote add origin git@github.com:momolevi/JavaPrivateSpace.git

生成public key
mac@macdeMacBook-Pro-3 Git % ssh-keygen -t rsa -C "zhenweilevi@gmail.com" 

Generating public/private rsa key pair.
Enter file in which to save the key (/Users/mac/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/mac/.ssh/id_rsa
Your public key has been saved in /Users/mac/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:b6EZ9zalkhIrI8l9KhcmFqWv8kpiBHfJLLJPP7hQXhc zhenweilevi@gmail.com
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|   o ..          |
|o o =oE          |
|.+ oo  .         |
|..o .o. S o   .  |
|.= =o++  O + o   |
|o.=.*++.* = =    |
|.+..oo.= o o .   |
|  o+.o.          |
+----[SHA256]-----+

### 提取public key，将公钥粘贴到github上
mac@macdeMBP-3 ~ % cd /Users/mac/.ssh   

![](assets/17323741766424.png)


确认本地和远程仓库是否建立连接
mac@macdeMacBook-Pro-3 ~ % ssh -T git@github.com
Hi momolevi! You've successfully authenticated, but GitHub does not provide shell access.

在目标目录下创建新的文件夹

现在可利用新创建的远程仓库保存、同步代码了。
-------------

### clone
在新的目标路径下先同步远程仓库
git clone git@github.com:momolevi/JavaPrivateSpace.git

在新的目标路径下创建文件 如：HelloGit.txt
### 上传
git add .
git commit -m "XXX"
git push
git status         --查询状态

### End
End
---------------
### 中途遇到的报错
git push --set-upstream origin main
--fatal: unable to access 'https://github.com/momolevi/JavaPrivateSpace.git/': HTTP/2 stream 1 was not closed cleanly before end of the underlying stream

fatal: unable to access 'https://github.com/xxx/': HTTP/2 stream 1 was not closed cleanly before end of the underlying stream
方法一：关闭所有github所有页面，关闭所有和github之间的连接，然后再次push，就成功了。
---------------- 
