集中式版本控制系统（SVN）
分布式版本控制系统（Git）

Git使用方式：命令，GUI，插件

# 基本命令

```
git -v  # 查看版本
git config --global --list  # 显示配置的内容
```

```
git add <>
git add .
git commit
git commit -m "message"
git status  # 查看当前仓库的状态
git log  # 查看仓库提交记录
git log --oneline  # 查看仓库简洁提交记录
git ls-files  # 查看暂存区的内容

```

![image.png|487x224](https://zxg-obsidian.oss-cn-beijing.aliyuncs.com/obsidian_picgo/20250301161122.png)

![image.png|582x282](https://zxg-obsidian.oss-cn-beijing.aliyuncs.com/obsidian_picgo/20250301165223.png)

git reset 的内容可以在[视频](https://www.bilibili.com/video/BV1HM411377j?t=377.2&p=6)重查看使用案例。
默认是git reset == git reset --mixed

```
git reflog  # 查看所有历史操作记录
git reset --hard b270efb  # 回退，reset操作也可以回退
```

```
git diff
git diff HEAD
git diff --cached
```

```
git rm <file>
git rm --cached <file> 只删除暂存区的文件
删除后要记得提交
git commit
```

.gitignore文件，忽略不应该加到版本库的文件
![image.png|628x290](https://zxg-obsidian.oss-cn-beijing.aliyuncs.com/obsidian_picgo/20250302142925.png)

eg:
```
echo access.log > .gitignore
```

这样就忽视了access.log文件
git status只会显示.gitinore

```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)
```

![image.png|453x312](https://zxg-obsidian.oss-cn-beijing.aliyuncs.com/obsidian_picgo/20250302145544.png)

# 远程仓库

```
git clone 
git push
```

push往上推，pull往下拉

```
git remote add git@github.com:XBXiaoBei/git_study.git
git remote -v
git branch -M main
git push -u origin main
git push -u <远程仓库名> <分支名>
git pull <远程仓库名> <远程分支名>:<本地分支名>
```

# GUI，IDE

![image.png|735x359](https://zxg-obsidian.oss-cn-beijing.aliyuncs.com/obsidian_picgo/20250302171155.png)

# Branch 分支

```
git branch  查看仓库的所有分支
git branch <branch-name>  创建一个分支
git checkout <branch-name>  切换到一个分支
git switch <branch-name>  切换到一个分支，更推荐用这个，上面那个会有出现bug
git merge dev   合并dev分支到当前分支
git branch -d dev  删除已经合并的dev
git branch -D dev  删除没有合并过的dev
```

## 解决合并冲突

小tips：git commit -a -m "message" 一个命令完成暂存和提交两个任务

main分支修改了a.txt，dev分支修改了a.txt，不能直接合并，执行 git merge dev 后需要在a.txt里面进行修改后重新暂存提交。

## rebase操作

![image.png|578x325](https://zxg-obsidian.oss-cn-beijing.aliyuncs.com/obsidian_picgo/20250302202633.png)


# 分支管理，工作流模型

TODO