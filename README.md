# git 指令介紹

檢查git版本
git --version

檢查設定檔
git config --list

設定user.name & user.eamil
git config --global user.name "yourname"
git config --global user.eamil "youreamil"

文字編輯器
:q 離開

cd 切換目錄
cd ..切換到上一個目錄
ls -al 檢視目錄全部

此資料夾被git控管 生成.git檔案
git init

檢視現在資料夾狀態
git status

新增檔案到暫存區 or被git控管
git add 檔名.副檔名
git add *.副檔名
全部一起新增到暫存區
git add --all 

commit將檔案放到本機儲存區
-m 是參數 留訊息
git commit -m "message"
只有被git控管的檔案才可以一次跳過暫存區
儲存到本機儲存區
git commit -am "message"
git commit -a -m "message"
=============================
#為什麼會兩次動作
1.類似倉庫管理
2.逐筆確認
3.codereview

甚麼時候commit
1.沒有一定
2.階段性功能完成一次
3.一天至少一次
===============================
檢視commit紀錄
git log
檢視commit紀錄精簡模式
git log --oneline

文字編輯器
:q 離開
:w 儲存
:wq 儲存並離開

把異動紀錄修改到最近一次commit
git commit --amend --no-edit
修改最近一次的commit訊息
git commit --amend -m "new message"

修改後檔案在工作區內還沒有加到暫存區 會還原成異動前的狀態 
*會改變程式
git restore <檔名>
修改後檔案已加入暫存區 還原後會移動到工作區內保留異動狀態
git restore --staged <檔名>

把檔案設定成不被git控管
git rm --cached <檔名>
通常不想被git控管就記錄在.gitignore

檢視工作區的異動比較
git diff

檢視暫存區的異動比較
git diff --staged 

檢視兩個commit比較
git diff <資訊碼> <資訊碼>

檢視該檔案每一行程式碼紀錄
git blame <檔名>

移動你的commit版本變成該版本 回到工作區
git reset <資訊碼>
git reset HEAD~
git reset HEAD^

移動你的commit版本變成該版本 回到暫存區
git reset --soft <> 

移動你的commit版本變成該版本 
*異動程式
git reset --hard <>

檢視歷史commit紀錄
git reflog

========================================
分支
檢視目前分支
git branch

創建分支 會複製目前所在分支全部內容到新分支
git branch <new branch name>

移動分支
git checkout <branch name>
git switch <branch name>

合併分支
git merge <branch name>

merge confilct
git不會幫你決定 要自行或雙方討論異動程式
>>>>> <<<<< ====== 自行移除
確認好程式後再git add 
git commit 

刪除分支
git branch -d <branch name>

創建並移動分支
git checkout -b <branch name>
git switch -c <branch name>
