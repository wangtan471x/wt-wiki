### IDEA

Ctrl + Y	删除光标所在行 或 删除选中的行 （必备）
Ctrl + X	剪切光标所在行 或 剪切选择内容
Ctrl+Shift+上下键   上下移动代码



### VisualStudio

Alt+O .h和.cpp切换

![VS](images\VS.png)



### Typroa

[参考网页](https://blog.csdn.net/fan521dan/article/details/89737140)
标题 1~6
开头#的个数表示，空格+文字。标题有1~6个级别，#表示开始，按换行键结束

对应的快捷键： ctrl + 1/2/3/4/5/6



### Git

1. 查看远程分支
    $ git branch -a

2. 查看本地分支
    $ git branch

3. 切换分支
    $ git checkout -b v0.9rc1 origin/v0.9rc1

4. 切换回master分支

  $ git checkout master

​	5.删除添加到缓存的文件

一种是 git rm --cached "文件路径"，不删除物理文件，仅将该文件从缓存中删除；



[git从主分支上拉取新分支以及提交代码、合并到主分支](https://www.cnblogs.com/wuqilang/p/12781270.html)

**从master上拉取一个新分支：**
git branch 查看当前分支，显示为master就行了
git checkout -b xxx 根据master分支切一个xxx分支出来
git branch 查看当前分支，显示为xxx分支就可以
git push -u origin xxx 将xxx分支推到远程上，因为远程上没有这个新的xxx分支，所以要加-u。第一次将新分支提交到远程上时需要加-u


**提交到当前开发分支：**
git branch 查看当前分支
git status 修改和添加的文件是红色的
git add . 将所有的文件推到暂存区
git status 此时修改和添加的文件是绿色的
git commit -m "" 将暂存区的代码推到本地仓库
git status 此时工作目录是干净的
git push origin xxx 将本地仓库xxx推到远程xxx，远程上有这个分支时可以不用写origin xxx


**合并到master分支：**
git checkout master 切换到master分支
git branch 查看当前分支

git pull origin master 保险起见先拉一下master分支上的代码

git merge xxx 将xxx合并到master分支
git push 将master分支代码推到远程，因为远程上有master分支，所以可以不用加origin master

 

**git如何撤销上一次commit操作：**

第一种情况，如果还没有push，只是在本地commit：git reset --hard <commit_id>

第二种情况，如果已经push：git revert <commit_id>

 

**强制将远程上代码覆盖本地：**

git fetch --all 

git reset --hard origin/master 

git pull



#### **git status中文乱码**

git config --global core.quotepath false



#### git 生成ssh锁

		1. 设置名称 git config --global user.name "yangjianliang"
  		2. 设置邮箱 git config --global user.email "526861348@qq.com"
  		3. 生成密钥 ssh-keygen -t rsa -C "526861348@qq.com"，按3次回车
  		4. 查看公钥 cat ~/.ssh/id_rsa.pub





### VSCode

1. 括号匹配 **Windows** Ctrl + Shift+\

2. 块注释:先选中需要注释的块，然后按

   ```c
   Alt + Shift + A
   ```

3. 删除指定行 ctrl+shift+k

### MkDocs

[环境设置](https://zhuanlan.zhihu.com/p/61492480)

[中文使用](https://markdown-docs-zh.readthedocs.io/zh_CN/latest/)

[中文应用](https://mkdocs.zimoapps.com/)

wt-wiki

```bash
cd wt-wiki
mkdocs serve
```

1. 在docs中添加对应的文章
2. 在mkdocs.yml中添加对应的连接
3. push到git上
4. 部署站点到git上 mkdocs gh-deploy
   1. 将Mardown文件转为静态HTML网页文件
   2. 将所有的静态HTML网页文件都推送到远程仓库的gh-pages分支
5. 指定端口 mkdocs serve --dev-addr=0.0.0.0:8001



### python

pip安装时会下载失败，报错信息：

During handling of the above exception, another exception occurred:

这是由于频繁访问网站或请求造成的，可以通过更换国内源的方法来解决此问题。示例如下：

> pip install scrapy -i http://pypi.douban.com/simple --trusted-host pypi.douban.com

其中-i指向要更换的国内源。
–trusted-host也是有必要的，否则会因为douban.com不被信任而报错。

最后附上pip国内的一些镜像：

中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
阿里云 http://mirrors.aliyun.com/pypi/simple/
中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/
豆瓣(douban) http://pypi.douban.com/simple/