# Git-Help
Git命令基础操作=>自用

## 本地推送流程
- Step1: 右键=> git bash here,弹出git命令行窗口

- Step2: 初始化本地仓库

  ```bash
  git init
  ```

  > 本地默认创建主分支master

- Step3: 本地仓库链接远程仓库

  ```bash
  git remote add [`远程仓库名`] [`远程仓库地址`]
  ```

  > 这里的远程仓库名，习惯上一般使用 origin

- Step4: 查看本地仓库状态

  ```bash
  git status  
  ```

  > 该命令显示已修改但未同步的文件

- Step5: 将文件同步添加到暂存区

  ```bash
  git add [`状态里的新文件`]  
  ```

  >可用git add -A一键添加

- Step6: 将文件添加到仓库

  ```bash
  git commit -m '[`相关注释文字`]' 
  ```

  > 注意-m后的 注释文字要用引号

- Step7: 将本地某分支推送到远程仓库，如果远程没有此分支会自动创建该分支，默认为master

  ```bash
  git push origin [`本地分支名`]
  ```
  
  > origin 为上面提到的默认远程仓库名

---
## Tips[额外需求]

### git add

1. 一键添加

```bash
 git add -A
```

*# Changes to be committed:*

*#   new file:   add-me*

*#   modified:   change-me*

*#   deleted:    delete-me*

> ​	可以一键添加所有未跟踪(new)、修改(modified)、被删除(deleted)文件，修改本地仓库再次提交很方便

### git push origin

1. 删除远程仓库的指定远程分支

```bash
git push origin --delete [`远程分支名`]
```

2. 强制推送

```bash
git push -f 
```

> 用于解决一些本地和远程始终不能同步[当前git pull无效]的问题，比如
>
> Updates were rejected because the tip of your current branch is behind  its remote counterpart. Integrate the remote changes(e.g.'git pull ...') before pushing again. 

### git remote

1. 查看远程仓库

```bash
git remote
```

> 显示当前已链接的`[远程仓库名]`  (但不显示远程仓库地址)

2. 取消指定链接的远程仓库

```bash
git remote remove [`远程仓库名`]   
```

3. 链接的远程仓库端口不是默认的port:22

```bash
git remote origin ssh://[`用户名`]@xx.xx.xx.xx:[`端口号`]/../../xxx.git
```

> 当远程开放的ssh不是port:22时，使用2、3命令重写绑定链接远程仓库
>
> __PS__:一般github的.git开放ssh端口都是port:22，不用管这个;
>
> git远程推送你自己的云服务器时，需要查看你自己设定的ssh端口,当然一般也是port:22，但可自主修改

## 常见问题

- Step7推送时: error: src refspec `[branchName]` does not match any

  修改本地分支名称
  
  ```bash
  git branch -m [oldBranchName] [newBranchName]
  ```
  
  
  
  
