# 我的交作業流程

作業環境 : Win7 64bit / Cmder

## Step. 1 - 取得你的 GitClassroom Repository

Slack 聊天室中最上方有個連結<br>
https://docs.google.com/document/d/15JheTGzjOlkeXal6mrrRLKOCrf0xJfvntLHj2B9gx28/edit?usp=sharing

點進去後會連到〔程式導師實驗計畫第二期相關資源〕的文件<br>
裡面有個連結 https://classroom.github.com/a/aaTx7yGC <br>
點了連結按提示操作後會連結到一個 github 的 repository

會看到如下圖所示的內容，標紅線的部份會是你的 git 帳號
![Imgur](https://i.imgur.com/PztUVED.jpg?1)

這個 repository 的參與人就是你跟 Huli 老師

<br>

## Step. 2 - 將這個 Repository 下載到本地端電腦

開啟 Cmder
利用 CD 指令移動到你想放這個 repository 的目錄 例: D:\Lidemy_MTR02\

在這個目錄下輸入指令
```
git clone https://github.com/Lidemy/mentor-program-2nd-你的github帳號.git
範例: git clone https://github.com/Lidemy/mentor-program-2nd-Rainbowrain-TW.git
```

接著應該會出現下述的內容
```
Cloning into 'mentor-program-2nd-Rainbowrain-TW'...
remote: Counting objects: 102, done.
remote: Compressing objects: 100% (65/65), done.
remote: Total 102 (delta 25), reused 102 (delta 25), pack-reused 0Receiving objects:  82% (84/102), 4.28 MiB | 1005.Receiving objects: 100% (102/102), 4.56 MiB | 996.00 KiB/s, done.
Resolving deltas: 100% (25/25), done.
```
就下載完成了

<br>

## Step. 3 - 先寫作業

我的流程是 clone 完就先寫作業，但要先做 branch 也可以，都還沒動手的話就參考看看
CD 移動到剛剛下載的目錄時應該會看見像這樣的內容
```
D:\0_0_LidemyMTR02\homework\mentor-program-2nd-Rainbowrain-TW (master -> origin) (mentor-program-2nd@1.0.0)
```
目錄路徑後面會出現 (master -> origin) (mentor-program-2nd@1.0.0)
這時候 (master -> origin) 的顏色是亮白色

<br>

## Step. 4 - 開 branch

作業寫完了，接下來要準備交作業。<br>
這時候 (master -> origin) 的顏色是暗紅色(代表有檔案被修改過)<br>
在 `homeworks\week1` 的目錄下輸入 `git status` 會看見類似下圖的內容
![Imgur](https://i.imgur.com/m2KnOXk.jpg)

modified 那區會有所有你修改過的檔案
然後建立新的 branch 輸入指令 
```
git branch "branch名稱"
範例: git branch "week1"
```

然後把世界線(?)移動到剛剛新開啟的 branch
```
git checkout "branch名稱"
```
畫面會出現
```
Switched to branch 'week1'
M       homeworks/week1/hw1.js
M       homeworks/week1/hw2.js
M       homeworks/week1/hw3.js
M       homeworks/week1/hw4.js
M       homeworks/week1/hw5.js
M       homeworks/week1/hw6.md
```
這是告訴你已經成功切換到 week1 這條 branch 了<br>
不放心的話可以輸入 `git branch -v` 看看 week1 是不是綠色且開頭有個 * 號<br>
這就是現在所在的branch

<br>

## Step. 5 - 做 commit

輸入 `git add .` 將所有修改過的檔案加入commit暫存區<br>
這時候輸入 `git status` 就會看見剛剛暗紅色的檔案變成暗綠色(即準備被 commit )<br>
![Imgur](https://i.imgur.com/HFNWM43.jpg)

接著輸入 `git commit -m "commit名稱"` 會看到類似如下的內容代表 commit 完成
```
[week1 7bf4801] 你取的commit名稱
 6 files changed, 97 insertions(+), 7 deletions(-)
```

<br>

## Step. 6 - 把作業 push 到 github

輸入 `git push origin week1` week1是你取的branch名稱<br>
這時候會進行一個 ssh 連線，如果有留意看 Cmder 下面的狀態列的話會看見<br>
等一下子後應該會跳一個 github 的登入視窗，輸入帳號密碼完成登入後會看見如下內容
```
Counting objects: 10, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (10/10), done.
Writing objects: 100% (10/10), 3.16 KiB | 3.16 MiB/s, done.
Total 10 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Lidemy/mentor-program-2nd-Rainbowrain-TW.git
 * [new branch]      week1 -> week1
 ```
 
 這時候回到 github 看你的 repository ，如圖示紅線處點 Branch: master 會有下拉式選單
 ![Imgur](https://i.imgur.com/51Y6vSs.jpg?1)
 
 看見你剛剛 push 的 branch 名稱就表示成功推上去 github 了

<br>

## Step. 7 - 發 PR (pull request) 請老師來改作業

這部份都網頁操作就都貼圖，先點擊紅框標示的 branches
![Imgur](https://i.imgur.com/oGIL5cr.jpg)

這邊會看見 Your branches 跟 Active branches ，目前裡面都是一樣的，兩個紅框的 New pull request選一個點
![Imgur](https://i.imgur.com/84gWOMO.jpg)

按著輸入你的要附在 PR 內的訊息，可以輸入 @aszx87410 來標記老師，然後按紅框內的 Create pull request
![Imgur](https://i.imgur.com/pawofwx.jpg)

接著會看見這個畫面，就表示你成功把作業交出去啦～(灑花
![Imgur](https://i.imgur.com/uY3R3iy.jpg)



















