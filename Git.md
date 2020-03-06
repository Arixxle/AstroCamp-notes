# Git

## 關於Git

### 眾多版本管理工具其中一種

### 不分程式語言，是現代工程師必備技能

### 但是很多人會用，但不知道用法是否正確

### 不好學

- 指令多，10X個，使用情境跟指令搭不起來
- 基本認知有誤，不了解本質

	- 許多人把Git當FTP用

### 誰適合用

- 你經常需要新增、修改、編輯、存檔

	- V10 V12 ...final  finalfinal

		- 以前的版本用法

	- 二進位檔（.psd .key .ai .jpg）

		- 不是純文字，無法看出檔案內容的差別

- 文字型的檔案非常適合用Git控管

	- 只看檔名，看不出檔案內容的差別

### 版本控制類型

- 分散式

	- 不需透過中控伺服器，檔案分散在每一個人手上。

- 集中式

	- 檔案存在一個固定的地方，以他為版本依據，但如果中控伺服器掛了，就全部掛了。沒有網路就無法備份。

		- e.g CVS SVN

### 開發者

- Linus Torvalds

	- 1天做出來
	- 三面白牆，專注工作

### Git不是GitHub

- * GitHub就是用Rails寫的

	- GitLab也是

- 這是一個商業服務

## 用途

### 歷史紀錄與證據

- 追溯所有的修改歷程，知道誰在什麼時間做了什麼修改，知道每一行是誰寫的。

### 備份

- 就像玩遊戲時，需要儲存遊戲進度

	- 確保遇到問題時，可以重新來過

### 原理

- 版本

	- 任何一點改動，就會形成一個版本

- 控制

	- 有時間軸，你可以隨時回到你想去的地方

### 同時支援本地及遠端操作

- 沒有網路時也可以做版本控制，7-8成時間都在本地備份

### 適用於多人協作

## 圖形介面 GUI

### 推薦

- GitHub Desktop

	- 免費使用，授權可用

- SourceTree

	- 免費使用，限制授權

- Windows

	- TortoiseGit

		- 小烏龜

### 盡量用終端機學習指令、運作邏輯。用GUI確認結果。

## 開始使用

### 不要害怕終端機指令，仔細看他給你的回饋，唸出聲音更有效果。

### 指令

- $ git config --list

	- 查設定檔資訊

		- 按q 結束
		- 看到「：」

			- 按空白鍵就可以展開更多資訊

- $ git config --global user.name "name"
- $ git config --global user.email "abc@gmail.com"
- 新增檔案 touch XXX.html

	- Q 要一次新增多個檔案怎麼做？

		- A 用空格隔開就可

- ls 列出檔案

	- ls -al 列出詳細資訊

-  新增檔案夾 mkdir name
- git log 看你的git 操作記錄
- 查詢官方指令聖經

	- git help log 查有哪些log參數可用
	- git help commit  查有哪些log參數可用

### /tmp

- Mac暫存夾，適合用來做練習

### git init

- 初始化(initialize)，做一次即可

	- 在所在資料夾建立一個.git資料夾，整個git的寶藏都在這，包括：歷史紀錄、版本．．．

- 讓Git知道這個資料夾要進行版控！！！

	- 從初始化後開始記錄，包含該曾、下層、下下層

		- 若上層也版控？？

	- 若不小心做錯怎辦？

		- 1 刪.git

			- $ rm -rf .git

### 工作區

- working 工作目錄

	- 不是目錄，只是貼一個標籤的狀態

- staging 暫存區域
- repository 儲存庫（本地）
- $ git status

	- 顯示檔案現在的狀態

- $ git add XXX.html

	- $ git add --all / gjt add .

- $ git commit -m "文字訊息"

	- "XXX" 很重要，不要亂寫，要能清楚描述你做了什麼事

		- (O)

			- "#23 bug fixed"

		- (X)

			- "WTF" "update"

- 檔案不是被放到某個地方，實際上是狀態改變
- 為什麼要兩段式這麼麻煩？

	- 學一個技術一定要思考，這個技術為什麼要這樣設計？
	- 不是每次就全部都commit，有可能你有一些要commit，有一些你正在做，就可以做更精細的控制。

- 什麼時間要commit

	- 你想commit就commit

		- 就像打遊戲存檔一樣，可以隨時，或是離開座位時，或是下班

## 情境

### 不小心刪除檔案？

- git checkout xxx.html

	- 從.git 把被刪除的檔案挖回來

- git check . 

	- 還原這一整層

### 這個程式碼誰寫的？

- git blame xxx.html

	- 查這個檔案中的程式碼的某一行誰寫的

### 只看某個檔案的log

- git log -p xxx.html

	- 不常用，多半直接用GUI來看

## 分支

### 為什麼要使用？

- 分支就像分身，讓你嘗試做某些嘗試，一但成功，本體就可以合併成功，若失敗，就退回來重做就好。

### 什麼時候要用？

- 什麼時候都可以

### 分支其實是貼紙

- 內建分支 master (貼紙)
- head 貼紙  表當前你所在的分支(位置／宇宙)

### 如何建立分支？

- git branch 分支名稱

	- e.g git branch cat

		- 建立分支就是在貼貼紙

### 如何跳轉分支？

- 移交主控權（head）- 主要鏡頭

	- git checkout cat

### 如何合併分支？

- git merge cat

	- 前提，head要回到master
	- fast-forward 到 cat

### 不小心跌入Vim怎辦

- 若指令只打 git commit 就會跑到Vim

	- 離開的方法
https://gitbook.tw/chapters/command-line/vim-introduction.html

### 萬一沒切換分支，讓master commit怎辦？

- 分支只是貼紙，換貼紙就好

	- git branch -m cat ccc

		- git checkout ccc

			- git branch -m master cat

				- git checkout cat

					- git branch -m ccc master

### 刪除分支（貼紙）

- 刪除末端分支(推出去的那些)，實際上不會消失，只是隱藏而已

	- 若刪除的是沒有做改動的分支，則沒有影響

### 複雜的分支（多分支合併）

- 先切到分支a

	- git merge 分支b -m"XXX"

		- 不會快轉合併

### 刪除分支

- git branch -d cat

### 分支發生衝突怎解？（具體怎麼解？還沒練習過）

- git會提醒你

	- 你就去那個檔案打開，編輯一下

		- 重新add . 

			- 重新commit

				- 再次合併

### rebase

- 將其中一個分支，轉到另一個分支上，延續下去。（實際上是複製一份貼過去另一個base後面）

### 回到上一步

- git reset XXXX

	- --mixed

		- 修改記錄放到working

	- --soft

		- 修改記錄放到staging

	- --hard

		- 修改記錄移除(但也不是真的消失)

	- 相對位置移動

		- 代名詞(或版號)^

			- 倒退一步

		- 代名詞(或版號)~5

			- 倒退5步

- 在Git 沒有刪除Commit的事

### reset跟checkout的差別

*XMind: ZEN - Trial Version*