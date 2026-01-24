# Linux的基本指令和操作
## 文字界面和xwindow切換
xwindow是linux的視窗管理員(像是windows的GUI)，因為我們是安裝包含GUI的版本，所以一開始登入會是預設使用xwindow  

Ubuntu的GUI & CLI (command line interface) 切換可以透過以下指令
1. 從GUI切換至CLI: ctrl + alt + [f3 ~ f6]
2. 從CLI切換回GUI: ctrl + alt + f2
3. 回到GUI登入畫面: ctrl + alt + f1

\*不同的linux distribution指令會有所不同

# Tab
在linux中，[tab]是作補全功能，例入命令打一半，按下tab它會幫忙把指令補全，如果是檔案，它會搜尋目前資料夾下的檔案把檔名補全  

若有多個指令或檔名符合條件時，按[tab]兩下則會列出所有符合條件的

# ctrl + c
這個是中斷的意思，若某個指令跑太久，可以用ctrl + c來中斷目前執行  

# ctrl + d
通常代表鍵盤輸入結束或exit

# shift + PageUP/PageDown
有些訊息太長會導致被畫面截掉，但CLI因為沒辦法用滑鼠來往上滾，因此這時可以用shift + PageUp/PageDown來往上or往下  

\*要注意，如果今天是用筆電且筆電沒有單獨的PageUp/PageDown鍵，需要變成fn + shift + 方向鍵，但fn通常是綁硬體的，因此vm裡面很有可能讀不到fn導致無法使用

# man & info
man是manaul的縮寫，可以讓你查看操作說明，其中第一行會有指令名稱和1個數字，每個數字有分別的含意  
例如:  
```
man date
```

info和man相似，一樣是查詢操作說明，差別在於man是一次把它全部show出來在一頁，而info則是用link list把它弄成分頁像書的模式  
例如:
```
info man
```

# root帳號登入
在ubunut要使用root權限，要下以下指令
```
sudo -i
```

# sync
在linux為了加快使用速度，會將一些載入記憶體的資料不寫回硬碟，但若此時不正常關機，則會導致資料丟失  
因此這個指令是將那些在記憶體中尚未寫回硬碟中的資料寫回硬碟
```
sync
```

# shutdown
關機指令，若是使用ssh連到主機，則只有root有權利  
```
shutdown [-krhc] [time] [message]
-k: 不是真的關機，警告而已
-r: reboot
-h: 系統服務停掉後關機
-c: cancel，取消關機指令
```

還有其他類似的指令，reboot, halt, poweroff, systemctl等等也可作到類似功能
