在預習 week3 的作業(第一期的 week2 )
剛好前幾天在臉書上看見六角學院分享兩個很實用的 Tip ，分享給同學

[原始文章](https://www.facebook.com/hexschool/posts/1137328509749794?__xts__[0]=68.ARBJz3ABGSzvtv_z5g58s_iQgqU0djyq2viuO8XlekR7i333HHEekM3MlCmOWCs95S_TN81Y7tZ_7gpfplpMfO_2RPB0NgIylB2FbmTJ5TSjHchDU7oYon6dTwvJQoDv3srjIpBJJarGXxZP3B_63dVofJBHERzAs3xvkMcPBELQsOfO12RbNQ&__tn__=-R)
<br>

簡單來說下圖紅框處有個 + 號，點擊後可以新增 CSS 屬性，請新增如下內容
```CSS
* {
    outline: 2px red solid;
}
```
- 2px: outline外框粗細
- red: 顏色
- solid: 外框線條樣式
可以自行換你想要的搭配，看的清楚都行<br>
ex: `* { outline: 4px yellow dashed }`

然後在黃框那裡也就是 Console 輸入 `document.DesignMode = 'on'`
這時候就可以在紅框中即時輸入文字觀察版面變化，可以試試字太多太少的時候會不會跑版

![Imgur](https://i.imgur.com/m2n7On9.jpg)

弄著弄著忽然在想 outline 跟 border 有什麼不同<br>
測試了一下之後發現 outline 跟 border 其實是很類似的東西，都包覆在元素的外圍<br>
但並不重疊，給一個 div 同時有 1px 的 outline 跟 1px 的 border 就看的出來<br>
作以這 1px 的框為分界點，outline 的 px 增加時會往外增加，border 則是往內<br>
且 border 的寬度會影響到整個元素的大小，所以如果跟其他元素有 margin 或 padding 等會改變相對位置的屬性關係時，座標就會產生變化<br>
而 outline 本身不會改變元素的大小，加到多寬都不會，也不會影響與其他元素的位置<br>
測試後得到這樣的結論後我反而不懂為什麼是 border 用的多了 ..<br><br>

用 outline 來顯示的原因應該是..一般設計的時候用 border 居多<br>
以 outline 來測試比較不會跟原始設計衝突
