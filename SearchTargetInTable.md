### 表格大概長的像這樣

<table id="t123">
        <tbody>
            <tr>
                <th colspan="6">123</th>
            </tr>
            <tr>
                <th colspan="6"><span>請輸入樣品編號:</span><input type="text" id="123_sampleInput" onkeypress="snInputEnter(this)"><input
                        type="button" id="123" value="確定" onclick="snChecked(this)"></th>
            </tr>
            <tr>
                <th colspan="2"><input type="button" id="123_unselectAll" onclick="selectAll(this)" value="　全選　" style="width:50%;align-content:center;"><input
                        type="button" id="123_unselectAll" onclick="unselectAll(this)" value="取消全選" style="width:50%;align-content:center;"></th>
                <th colspan="4"><input type="button" id="123_writeToSql" onclick="writeToSql(this)" value="確認選取的資料並上傳"
                        style="width:100%"></th>
            </tr>
            <tr>
                <th>select</th>
                <th>Sample</th>
                <th>Description</th>
                <th>Raw Data</th>
                <th>Is Delete?</th>
                <th style="width:1px;display:none">Analysis</th>
            </tr>
            <tr>
                <td><input type="checkbox" value="1" checked=""></td>
                <td></td>
                <td>123</td>
                <td></td>
                <td><input type="button" value="刪除">[按鈕]</td>
                <td>Analysis Test</td>
            </tr>
            <tr>
                <td><input type="checkbox" value="1" checked=""></td>
                <td></td>
                <td>456</td>
                <td></td>
                <td><input type="button" value="刪除">[按鈕]</td>
                <td>Analysis Test</td>
            </tr>
            <tr>
                <td><input type="checkbox" value="1" checked=""></td>
                <td></td>
                <td>789</td>
                <td></td>
                <td><input type="button" value="刪除">[按鈕]</td>
                <td>Analysis Test</td>
            </tr>
        </tbody>
    </table>

基本上就是在按下 [按鈕] 的時候找到同一列的第 3 個 cell 中的值

目前有嘗試兩個做法:
1. 生成按鈕時給按鈕一個 id 或 name 叫 btn003 ， 第三個 td 給 id 或 name 叫 td003
   那我就取 btn003.substring(3,3) 後再 getElementById('td'+003) 就可以找到
   但我一個畫面上可能會好幾個這種表格，所以每個 table 就又要取名字 ..
   
2. 生成button的時候給一個 onclick 屬性，例如 <button onclick="searchValue(this)"/>
   然後在js裡頭加一個function
   ```javascript
   function searchValue(btn) {
      var result = btn.parentNode.parentNode.children[2].innerHTML;   
   }
   ```

只是在想說還有沒有什麼別的方法，雖然功能是寫出來了，但總覺得未來要是表單量很大
每次都這樣搞好累阿 'A`


這是自動生成的 Code ，因為 markdown 支援度的關係實際上跟上面會有點差別
```javascript
function createTable(deviceId){
    $('#show_area').append(
    '<table id="t'+deviceId+'">'+
        '<tr><th colspan="6">'+deviceId+'</th></tr>'+
        '<tr><th colspan="6"><span>請輸入樣品編號:</span>'+
        '<input type="text" id="'+deviceId+'_sampleInput" onkeypress="snInputEnter(this)"/><input type="button" id="'+deviceId+'" value="確定" onclick="snChecked(this)"></th></tr>'+
        '<tr><th colspan="2"><input type="button" id="'+deviceId+'_unselectAll" onclick="selectAll(this)" value="　全選　" style="width:50%;align-content:center;"/><input type="button" id="'+deviceId+'_unselectAll" onclick="unselectAll(this)" value="取消全選" style="width:50%;align-content:center;"/></th>'+
        '<th colspan="4"><input type="button" id="'+deviceId+'_writeToSql" onclick="writeToSql(this)" value="確認選取的資料並上傳" style="width:100%"/></th></tr>'+
        '<tr>'+
        '<th>select</th>'+
        '<th>Sample</th>'+
        '<th>Description</th>'+
        '<th>Raw Data</th>'+
        '<th>Is Delete?</th>'+
        '<th style="width:1px;display:none">Analysis</th>'+
        '</tr></table>'
    );
    var table = document.getElementById('t'+deviceId);
    var rowNumber = 20;
    for(j=0;j<rowNumber;j++){
    var row = table.insertRow(table.rows.length);
    
    for (i=0;i<6;i++){
        var cell = row.insertCell();
        if (i==0){
            cell.innerHTML = "<input type='checkbox' value='1' checked/>";
        }else if (i==4){
            cell.innerHTML = "<input type='button' value='刪除'/>";
        }else if (i==5){
            cell.innerHTML = "Analysis Test";
        }
    }
}
}
```

