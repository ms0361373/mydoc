# Linux 基本應用
> vi 文字編輯器
有的 Unix Like 系統都會內建 vi 文書編輯器
很多個別軟體的編輯介面都會主動呼叫 vi (例如未來會談到的 crontab, visudo, edquota 等指令)；
vim 具有程式編輯的能力，可以主動的以字體顏色辨別語法的正確性，方便程式設計；
因為程式簡單，編輯速度相當快速。

## vi 三種模式

### 一般指令模式 (command mode)
> 可以使用『上下左右』按鍵來移動游標，你可以使用『刪除字元』或『刪除整列』來處理檔案內容， 也可以使用『複製、貼上』來處理你的文件資料。
### 編輯模式 (insert mode)
> 按下『i, I, o, O, a, A, r, R』等任何一個字母之後才會進入編輯模式。在畫面的左下方會出現『 INSERT 或 REPLACE 』的字樣，此時才可以進行編輯。而如果要回到一般指令模式時， 則必須要按下『Esc』這個按鍵即可退出編輯模式。
### 指令列命令模式 (command-line mode)
> 輸入『 : / ? 』三個中的任何一個按鈕，就可以將游標移動到最底下那一列。在這個模式當中， 可以提供你『搜尋資料』的動作，而讀取、存檔、大量取代字元、離開 vi 、顯示行號等等的動作則是在此模式中達成的！

## vi 使用

#### 建立檔案
> 直接輸入『 vi 檔名』就能夠進入 vi 的一般指令模式了。   
<img src="https://proton.vir000.com/Jason/jason_gao/-/raw/main/img/vi%E6%96%B0%E5%A2%9E%E6%AA%94%E6%A1%88.png" width="300" />

#### 編輯檔案
> 在一般指令模式之中，只要按下 i, o, a 等字元就可以進入編輯模式了  
<img src="https://proton.vir000.com/Jason/jason_gao/-/raw/main/img/vi%E7%B7%A8%E8%BC%AF%E6%AA%94%E6%A1%88.png" width="300" />

#### 回到一般指令模式
> 按下 [ESC] 按鈕回到一般指令模式

#### 離開 vi 環境  
> 輸入『:wq』即可存檔離開！ 
> 輸入『 ls -l 』即可看到我們剛剛建立的檔案.  
<img src="https://proton.vir000.com/Jason/jason_gao/-/raw/main/img/%E6%AA%94%E6%A1%88%E5%84%B2%E5%AD%98%E9%9B%A2%E9%96%8BVi.png" width="100" />

## 常用按鈕
|  快捷   | 用法  |
|  ----  | ----  |
| [Ctrl] + [f]  | 螢幕『向下』移動一頁，相當於 [Page Down]按鍵  |
| [Ctrl] + [b]  | 螢幕『向上』移動一頁，相當於 [Page Up] 按鍵 |
| 0 或功能鍵[Home]  | 移動到這一列的最前面字元處 |
| $ 或功能鍵[End]  | 移動到這一列的最後面字元處 |
| g  | 移動到這個檔案的最後一列 |
| gg  | 移動到這個檔案的第一列 |
| n<Enter>  | n 為數字。游標向下移動 n 列 |
| n<Enter>  | n 為數字。游標向下移動 n 列 |

## 搜尋與取代
|  快捷   | 用法  |
|  ----  | ----  |
| /word  | 向游標之下尋找一個名稱為 word 的字串。例如要在檔案內搜尋 vbird 這個字串，就輸入 /vbird |
| :n1,n2s/word1/word2/g  | n1 與 n2 為數字。在第 n1 與 n2 列之間尋找 word1 這個字串，並將該字串取代為 word2 ！舉例來說，在 100 到 200 列之間搜尋 vbird 並取代為 VBIRD 則：『:100,200s/vbird/VBIRD/g』。 |
| :1,$s/word1/word2/g  | 從第一列到最後一列尋找 word1 字串，並將該字串取代為 word2 ！ |
| :1,$s/word1/word2/gc  | 從第一列到最後一列尋找 word1 字串，並將該字串取代為 word2 ！且在取代前顯示提示字元給使用者確認 (confirm) 是否需要取代！ |

## 刪除、複製與貼上
|  快捷   | 用法  |
|  ----  | ----  |
|  x, X  | 在一列字當中，x 為向後刪除一個字元， X 為向前刪除一個字元  |
|  dd  | 刪除游標所在的那一整列  |
|  ndd  | n 為數字。刪除游標所在的向下 n 列，例如 20dd 則是刪除 20 列  |
|  yy  | 複製游標所在的那一列  |
|  nyy  | n 為數字。複製游標所在的向下 n 列，例如 20yy 則是複製 20 列  |
|  p, P  | p 為將已複製的資料在游標下一列貼上，P 則為貼在游標上一列！ 舉例來說，我目前游標在第 20 列，且已經複製了 10 列資料。則按下 p 後， 那 10 列資料會貼在原本的 20 列之後，亦即由 21 列開始貼。但如果是按下 P 呢？ 那麼原本的第 20 列會被推到變成 30 列。|
|  u  | 復原前一個動作。  |
|  [Ctrl]+r  | 重做上一個動作。  |
|  .  | 重複前一個動作的意思。 如果你想要重複刪除、重複貼上等等動作。  |

## 儲存、離開等指令
|  快捷   | 用法  |
|  ----  | ----  |
|  :w  | 將編輯的資料寫入硬碟檔案中  |
|  :q  | 離開 vi  |
|  :wq  | 儲存後離開，若為 :wq! 則為強制儲存後離開  |

## 常用指令圖
![常用指令圖](img/vim-commands.jpeg)

## 常用指令  
## rm  
移除指令
### 強行刪除 , 不再提示
> rm -f fileanme  
### 刪除前逐一詢問
> rm -i fileanme  
### 刪除所有檔案不做確認
> rm -rf fileanme  
### 刪除所有檔案並做確認
> rm -irf fileanme  

* -f：force，不會出現警告訊息；
* -i：刪除前詢問使用者是否動作
* -r：遞迴刪除(需特別注意!)

## cp 
複製檔案
### 複製目錄全部內容 需要加上 -Ｒ
> ex: cp -R /from/filename.txt /to/
### 加上-p 會連同屬性依同複製
> ex: cp -Rp /from/filename.txt /to/

* -a ：相當於 -dr --preserve=all 的意思，至於 dr 請參考下列說明；(常用)
* -d ：若來源檔為連結檔的屬性(link file)，則複製連結檔屬性而非檔案本身；
* -f ：為強制(force)的意思，若檔案已存在且無法開啟，則移除後再嘗試一次；
* -i ：若目標檔(destination)已經存在時，在覆蓋時會先詢問動作的進行(常用)
* -l ：進行硬式連結(hard link)的連結檔建立，而非複製檔案本身；
* -p ：連同檔案的屬性(權限、用戶、時間)一起複製過去，而非使用預設屬性
* -r ：遞迴持續複製，用於目錄的複製行為；(常用)
* -s ：複製成為符號連結檔 (symbolic link)，亦即『捷徑』檔案；
* -u ：destination 比 source 舊才更新 destination，或 destination 不存在的情況下才複製。

## mv
移動檔案
> 語法： mv 來源檔（或目錄） 目的檔（或目錄）
> ex: mv /.bashrc .(而將檔案移動至目前的工作目錄，則加上 ".")

* -f ：force 強制的意思，如果目標檔案已經存在，不會詢問而直接覆蓋；
* -i ：若目標檔案 (destination) 已經存在時，就會詢問是否覆蓋！
* -u ：若目標檔案已經存在，且 source 比較新，才會更新 (update)

## tar
壓縮
> tar -ckvf FileName.tar DirName
解壓縮
> tar -xkvf FileName.tar

* -c ：建立打包檔案，可搭配 -v 來察看過程中被打包的檔名(filename)
* -t ：察看打包檔案的內容含有哪些檔名，重點在察看『檔名』就是了；
* -x ：解打包或解壓縮的功能，可以搭配 -C (大寫) 在特定目錄解開
> 特別留意的是， -c, -t, -x 不可同時出現在一串指令列中。
 

* -z ：透過 gzip 的支援進行壓縮/解壓縮：此時檔名最好為 *.tar.gz
* -j ：透過 bzip2 的支援進行壓縮/解壓縮：此時檔名最好為 *.tar.bz2
* -J ：透過 xz 的支援進行壓縮/解壓縮：此時檔名最好為 *.tar.xz
> 特別留意， -z, -j, -J 不可以同時出現在一串指令列中

* -v ：在壓縮/解壓縮的過程中，將正在處理的檔名顯示出來！
* -k ：在解包的時侯不要覆蓋已存在的檔案！(會出現error提示)
* -f filename：-f 後面要立刻接要被處理的檔名！建議 -f 單獨寫一個選項囉！(比較不會忘記)
* -C 目錄 ：這個選項用在解壓縮，若要在特定目錄解壓縮，可以使用這個選項。
 

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
