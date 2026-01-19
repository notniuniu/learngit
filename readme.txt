0.  **标准流程** 
github上创建新仓库
git clone git@xxx.git至本地
main #发布版本
dev0 #分支版本
dev1 #分支版本

1. **管理版本**

git status # 查看工作区状态
git diff # 查看修改内容
git log # 查看提交历史
git reflog# 查看命令历史
git reset --hard <commit_id> # 回退到指定版本（通过commit_id

2. **分支**

git switch -c <branch_name> # 创建新分支并切换到该分支
git merge <branch_name> #  将指定分支的更改合并到当前分支
git rebase <branch> # 将当前分支的修改“搬到”指定的 <branch> 分支的末尾
git branch -d <branch_name># 删除指定的本地分支
git branch -D <name> # 强行删除未被合并的分支
git branch --set-upstream branch-name origin/branch-name # 设置本地 branch-name 分支的上游分支为远程的 origin/branch-name
git log --graph # 以图形化方式展示分支的合并历史


3. **提交**

git init # 初始化一个Git仓库
git add <file># 添加文件到Git仓库
git commit -m "<message>"# 提交到Git仓库
git checkout <branch># 切换分支
git checkout -- <file> # 放弃工作区修改（不会影响暂存区）
git checkout <commit-id> -- <file> # 将指定的文件 <file> 恢复到某个提交 <commit-id> 中的版本
git checkout -b <new-branch-name> # 创建并切换到新分支
git checkout -b branch-name origin/branch-name # 创建并切换到本地分支 branch-name，基于远程仓库 origin 的 branch-name 分支
git reset HEAD <file># 放弃工作区修改并取消暂存
git rm <file>删除工作区中的文件，并同时删除Git仓库中的文件

4. **远程仓库**

git remote add origin git@server-name:path/repo-name.git # 关联远程仓库
git push -u origin main # 推送本地提交到远程仓库（第一次推送）
git push origin master # 推送本地修改到远程仓库
git pull # 从远程仓库拉取最新的提交并自动合并到当前分支


5. **临时储藏**

git stash # 储藏当前工作区的修改，暂时保存未提交的更改
git checkout main # 切换到 main 分支
git checkout -b issue-101 # 创建并切换到新的分支 issue-101
git switch master # 切换到 master 分支
git add readme.txt # 将 readme.txt 文件添加到暂存区，准备提交
git commit -m "fix bug 101" # 提交更改并附带提交信息 "fix bug 101"
git merge --no-ff -m "merged bug fix 101" issue-101 # 合并 issue-101 分支到当前分支，使用 --no-ff 保持合并记录
git switch dev # 切换到 dev 分支
git stash list # 列出所有储藏的工作区修改
git stash pop # 恢复最后一次储藏的工作区修改并从储藏中移除
git cherry-pick <commit> # 将指定的提交 <commit> 应用到当前分支

6. **标签tag管理**
默认标签是打在最新提交的commit上的，标签总是和某个commit挂钩。
如果这个commit既出现在master分支，又出现在dev分支，那么在这两个分支上都可以看到这个标签。
git tag v1.0 # 创建一个新的标签 v1.0，指向当前提交
git tag -d v0.1# 删除本地标签 v0.1
git push origin v1.0 # 将标签 v1.0 推送到远程仓库
git push origin --tags # 推送所有本地标签到远程仓库
git push origin :refs/tags/v0.9 # 删除远程仓库中的标签 v0.9

