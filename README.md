Linux 基本應用
=
> vi 文字編輯器
有的 Unix Like 系統都會內建 vi 文書編輯器
很多個別軟體的編輯介面都會主動呼叫 vi (例如未來會談到的 crontab, visudo, edquota 等指令)；
vim 具有程式編輯的能力，可以主動的以字體顏色辨別語法的正確性，方便程式設計；
因為程式簡單，編輯速度相當快速。

vi 三種模式
=
一般指令模式 (command mode)
-
> 可以使用『上下左右』按鍵來移動游標，你可以使用『刪除字元』或『刪除整列』來處理檔案內容， 也可以使用『複製、貼上』來處理你的文件資料。
編輯模式 (insert mode)
-
> 按下『i, I, o, O, a, A, r, R』等任何一個字母之後才會進入編輯模式。在畫面的左下方會出現『 INSERT 或 REPLACE 』的字樣，此時才可以進行編輯。而如果要回到一般指令模式時， 則必須要按下『Esc』這個按鍵即可退出編輯模式。
指令列命令模式 (command-line mode)
-
> 輸入『 : / ? 』三個中的任何一個按鈕，就可以將游標移動到最底下那一列。在這個模式當中， 可以提供你『搜尋資料』的動作，而讀取、存檔、大量取代字元、離開 vi 、顯示行號等等的動作則是在此模式中達成的！


vi 建立檔案
-
直接輸入『 vi 檔名』就能夠進入 vi 的一般指令模式了。   
<img src="https://proton.vir000.com/Jason/jason_gao/-/raw/main/img/vi%E6%96%B0%E5%A2%9E%E6%AA%94%E6%A1%88.png" width="300" />

vi編輯檔案
-
在一般指令模式之中，只要按下 i, o, a 等字元就可以進入編輯模式了  
<img src="https://proton.vir000.com/Jason/jason_gao/-/raw/main/img/vi%E7%B7%A8%E8%BC%AF%E6%AA%94%E6%A1%88.png" width="300" />

按下 [ESC] 按鈕回到一般指令模式

進入指令列模式，檔案儲存並離開 vi 環境  
-
輸入『:wq』即可存檔離開！ 
輸入『 ls -l 』即可看到我們剛剛建立的檔案.  
<img src="https://proton.vir000.com/Jason/jason_gao/-/raw/main/img/%E6%AA%94%E6%A1%88%E5%84%B2%E5%AD%98%E9%9B%A2%E9%96%8BVi.png" width="100" />

