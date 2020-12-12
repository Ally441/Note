## Git

版本管理工具

### Git与SVN

SVN是一个集中式版本工具

Git是分布式版本控制系统

![image-20201210214952522](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201210214952522.png)

```
使用当前目录作为Git仓库：
git init
如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交：
git add *.C
git add README
git commit -m '初始化项目版本'
```

### 工作区和暂存区

工作区：就是你在电脑里能看到的目录，比如reporstory文件夹就是一个工作区

暂存区：一般存放在 **.git** 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）

版本库：工作区有一个隐藏目录 .git，这个不算工作区，而是 Git 的版本库。

![image-20201210224601795](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201210224601795.png)

```
拷贝一份远程仓库(下载一个项目)
git clone <repo>
```

### git上传到github

```
git init
git add . 
git commit -m "版本号"
git branch -M main
git remote add origin https://github.com/Ally441/xxx.git
git push -u origin main
```



### 分支管理

