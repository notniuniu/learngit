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
git branch -d <branch_name># 删除指定的本地分支
git log --graph # 以图形化方式展示分支的合并历史

3. **提交**

git init # 初始化一个Git仓库
git add <file># 添加文件到Git仓库
git commit -m "<message>"# 提交到Git仓库
git checkout -- <file># 放弃工作区修改（不会影响暂存区）
git reset HEAD <file># 放弃工作区修改并取消暂存
git rm <file>删除工作区中的文件，并同时删除Git仓库中的文件

4. **远程仓库**

git remote add origin git@server-name:path/repo-name.git # 关联远程仓库
git push -u origin main # 推送本地提交到远程仓库（第一次推送）
git push origin master # 推送本地修改到远程仓库

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





