markdown文档备份位置

### 验证是否成功 
ssh -T git@github.com

成功结果为：
Hi Musing93! You've successfully authenticated, but GitHub does not provide shell access.

第一次使用Git的clone或者push命令连接GitHub时，会得到一个警告，输入yes回车即可。


## 建立本地仓库与github关联

本地配置github
```
git config --global user.name "Musing"  
git config --global user.email "*****@qq.com"  
git config --list
```

### 本地与github连接

```
git  remote add origin https://github.com/leiakito/hexo_markdown.git

查看config文件，看是否关联成功：

cat ~/.git/config 
~ 代表root  

 但在此文件中只需要找到.git即可 

ls -a 查看隐藏文件 
关联成功 结果如下
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
[remote "origin"]
	url = https://github.com/leiakito/hexo_markdown.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master

```
### 相应命令 

1.创建说明文档 

echo "meesage">>~/leia/source/readme.md
2.文件添加到仓库 
```
git add readme.md
```
3.提交到本地
```
git add . //添加文件 
git status //查看文件状态
git commit -m "message" //文件备注
```
4.建立master分支 
由于远程仓库是空的，因此第一次推送文件需要执行命令：
```
 git push -u origin master
```
5.二次提交
```
vim readme.md
git add readme.md
git commit -m "message " 
git push  origin master 
//第二次之后的推送，push后面不需要加-u
```
参考文档  https://blog.csdn.net/weixin_37058227/article/details/90291368
