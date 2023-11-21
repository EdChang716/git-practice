# git-practice
Git practice as a Tuturial
Git 是一種分散式版本控制系統，主要用於追蹤和管理軟體開發項目的代碼變更。以下是 Git 的一些基本概念和操作：

1. 版本控制系統： Git 可以幫助開發者追蹤代碼的變化，記錄每一次修改的內容，以及誰、什麼時候進行了這些修改。這使得團隊成員可以協同工作，而不會擔心代碼的混亂或遺失。
2. 倉庫（Repository）： Git 的基本工作單位是倉庫，它是包含項目所有文件和歷史記錄的地方。倉庫可以分為本地倉庫（存在於開發者的本地機器上）和遠程倉庫（存在於遠程伺服器上，可以是在互聯網上的一個共享存儲庫）。
3. 克隆（Clone）： 將遠程倉庫複製到本地稱為克隆。這將在本地創建一個與遠程倉庫相同的副本，開發者可以在本地工作而不會影響遠程項目。
4. 分支（Branch）： 開發者可以基於主分支（通常是master）創建不同的分支，以便同時進行多個並行的開發工作。分支使得開發者可以在不影響主要代碼的情況下進行實驗、修復錯誤或添加新功能。
5. 提交（Commit）： 提交是將代碼更改保存到版本庫的操作。每次提交都有一個相應的提交消息，用於描述這次修改的內容。
6. 合併（Merge）： 當一個分支的工作完成後，可以將其合併回主分支或其他分支。這將將分支上的修改合併到目標分支中。
7. 推送（Push）： 將本地的修改推送到遠程倉庫，以使遠程倉庫的內容保持最新。
8. 拉取（Pull）： 從遠程倉庫獲取最新的修改，以保持本地倉庫與遠程倉庫同步。
9. 衝突（Conflict）： 當合併操作無法自動完成時，就會發生衝突。這可能是因為同一行代碼在不同的分支上進行了修改。解決衝突需要手動處理，以確保合併後的代碼是正確的。

## Git Work flow
<img width="794" alt="截圖 2023-11-21 下午2 49 26" src="https://github.com/EdChang716/git-practice/assets/151502659/d5e3acbf-2228-4322-812e-7258ab400701">

## First time using Git with Mac
$ git config --global user.name "your username"
$ git config --global user.email your_email
$ git config -- list
#應該會看到剛剛設定的帳戶名稱與email

## Git 基本指令
1. `git init`：初始化當前位置，讓 Git 對這個目錄進行版控
2. 建立 `.gitignore` 忽略不需版本控制的檔案
3. `git add .`：把所有檔案加入版本控制（把東西放到一個暫存資料夾 temp ）
4. `git commit -am "message"`：新建一個版本（把 temp 資料夾改名為"版本號"）
   *若有新檔案，需重複步驟 3. 把所有檔案加進版本控制，才能執行 commit*
5. 在 commit 之前，可用 `git diff` 查看與上一版的差異
6. `git checkout <版本號>`： 可以切換各個版本（去到某個資料夾底下） git checkout master ： 回到最新版本
ref: [Git基本指令教學](https://hackmd.io/@Heidi-Liu/note-git)

# Build your own repo on local(本地端)  
1. 先在桌面建立一個資料夾，以及一個空的txt檔案  
    
    #進入桌面創建一個新的資料夾 project_git
    $ cd~ /desktop
    $ mkdir project_git
    #建立一個空檔案 hello_git.txt
    $ cd ~/desktop/project_git/
    $ touch hello_git.txt
    
   
3. 建立本地Git repo
    
    $ git init
    Initialized empty Git repository in /Users/edward/Desktop/project_git/.git/
    #查看目前的git狀態
    $ git status
    On branch main
    No commits yet

    Untracked files:
    (use "git add <file>..." to include in what will be committed)
	  hello_git.txt

    nothing added to commit but untracked files present (use "git add" to track)
可以看出尚未有檔案被追蹤，需使用 `git add .` 將整個資料夾加入追蹤！
Note:
  *輸入git add 主檔名.副檔名將修改推到Staging Area。如果只打git add不輸入檔案名稱，就會將整個資料夾的檔案都一起推送上去到Staging Area。*

5. 進入暫存區(add)，提交版本(commit)
打開hello_git.txt，隨便做一點修改
<img width="668" alt="截圖 2023-11-21 下午3 21 06" src="https://github.com/EdChang716/git-practice/assets/151502659/26cbfadb-2fbe-44ed-820f-c390614395dd">

**將.txt加入暫存區**
    $ git add hello_git.txt
**將.txt commit**
    # -m 代表輸入訊息(only one line)
    $ git commit -m 'Add a line'
       [main (root-commit) 3491550] Add a line
    1 file changed, 1 insertion(+)
    create mode 100644 hello_git.txt

Note:
  *由於 git commit -m僅能輸入一行評論；如果想要比較詳細的評論時，可改為輸入git commit -e就能打開編輯器、撰寫超過一行的評論。*
    
    # 查看修改後的檔案狀態
    $ git status
    On branch main
    nothing to commit, working tree clean
表示目前暫存區沒有東西

    # 利用另外一個功能git log查看所有的commit紀錄：
    $ git log
    ommit 3491550d4ca2b6924f1c859627c82c078a342366 (HEAD -> main)
    Author: Edward Chang <edward.chang.0716@gmail.com>
    Date:   Tue Nov 21 15:24:26 2023 +0800

        Add a line

Note:若反悔想將檔案移出暫存區 
要移除Staing Area中的檔案，我們必須根據檔案狀態採用不同的指令：
1. **若該檔案不在repository內 : git rm –cached 檔案名稱**
2. **若檔案已經在repository內 : git reset HEAD 檔案名稱**

5. **Summary**
    $ git clone 
    clone下來別人的專案到local端
    $ git init  
    創建一個新的Repository (打開任何一個專案資料夾打上git init)
    $ add add 主檔名.副檔名   
    將檔案提交入Staging Areagit add 整個資料夾提交入Staging Area 
    $ git commit -m '一行解說文字'  
    將檔案提交入Repository git commit -e 能用編輯器撰寫多行解說文字
    $ git rm --cached 檔案名稱 
    將不在Repository的檔案移出Staging Area
    $ git reset HEAD 
    將已經在Repository的檔案移出Staging Area
    $ git status
    查看目前檔案的狀態
    $ git log
    查看目前所有commit的歷史紀錄
    $ git diff
    可以看到修改過後的檔案內部紀錄
    $ git show 
    詳細列出該次commit的修改內容

# 將本地端repo or files 推送至 Remote (Github repo) 中

