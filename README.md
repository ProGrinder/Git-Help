# Git-Help
Git命令基础操作=>自用

## 本地推送
- Step1: 右键=> git bash here,弹出git命令行窗口

- Step2: 初始化本地仓库

  git init;

- Step3: 本地仓库链接远程仓库

  git remote add origin `[仓库地址]`

- Step4: 查看本地仓库状态

  git status  		     

- Step5: 将文件添加到暂存区

  git add `[状态里的新文件] ` 

- Step6: 将文件添加到仓库

  git commit -m `'相关注释文字'` 

- Step7: 将本地某分支推送到远程仓库，如果远程没有此分支会自动创建该分支，默认为master

  gti push origin `[branchName]` 

---
## Tips

### git add

git add `-A`

*# Changes to be committed:*

*#   new file:   add-me*

*#   modified:   change-me*

*#   deleted:    delete-me*

​	可以一键添加所有未跟踪(new)、修改(modified)、被删除(deleted)文件，修改本地仓库再次提交很方便

### git push origin

gti push origin `--delete [branchName]` 

​	删除指定远程分支



## 常见问题

- Step7推送时: error: src refspec `[branchName]` does not match any

  修改本地分支名称
  git branch -m [oldName] [newName]
