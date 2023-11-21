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

# Build your own repo on local(本地端）
成功 example code:(前方需兩個tab)

    #進入桌面創建一個新的資料夾 project_git
    $ cd~ /desktop return shell_exec("echo $input | $markdown_script");
    $ cd~ /desktop return shell_exec("echo $input | $markdown_script");
    $ mkdir project_git return shell_exec("echo $input | $markdown_script");





