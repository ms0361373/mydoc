# Git 應用
### 下載
> git pull
### 上傳
> git push
### 查看狀態
> git status
### 新增／修改 加入索引
> git add
### 加入說明 and Commit
> git commit -m "XXXXX"
### 建立分支
> git branch < branchname >
### 切換分支
> git checkout < branch >
### 合併分支
> git merge < commit >
### 刪除分支
> git branch -d < branch >
### 使用 rebase 合併
![常用指令圖](https://backlog.com/git-tutorial/tw/img/post/stepup/capture_stepup2_8_1_1.png)
> (issue3) git rebase master

![常用指令圖](https://backlog.com/git-tutorial/tw/img/post/stepup/capture_stepup2_8_1.png)

### 取消過去提交  
> git revert HEAD  
![常用指令圖](https://backlog.com/git-tutorial/tw/img/post/stepup/capture_stepup7_2_2.png)
### 放棄提交  
> git reset HEAD^  
> 每一個 ^ 符號表示「前一次」
### 提取提交  
> git cherry-pick HEAD

![常用指令圖](https://backlog.com/git-tutorial/tw/img/post/stepup/capture_stepup6_4_1.png)
### 合併提交  
> git rebase -i HEAD~~
### 修改提交
> --amend
### 暫存修改檔  
> git stash
### 列出暫存檔列表
> git stash list
### 叫出暫存檔
> git stash pop
### 指定叫出暫存檔
> git stash pop stash@{n}
### 丟棄暫存檔
> git stash drop
### 丟棄指定暫存檔
> git stash drop stash@{n}
### 清空暫存檔案列表
> git stash clear
