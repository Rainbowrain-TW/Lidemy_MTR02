## Number 類型的內建函式
### Number(n)
- 將字串轉數字
<br>

### parseInt(n, 幾進位)
- 將字串轉數字
- 若字串有小數時，只轉整數，例如：“20.35” -> 20
<br>

### parseFloat(n, 幾進位)
- 將小數字串轉小數，例如：“20.35” -> 20.35
<br>

### .toFixed(參數)
- 當小數很多位時，截取至哪一位，例如：(20.3555555555).toFixed(2) -> 20.35
- 參數可不輸入，不輸入時為0
- 當數字為整數時，則補小數，例如：(20).toFixed(2) -> 20.00
<br>

### Number.MAX_VALUE
- 在JS中可存的最大數字，console.log(Number.MAX_VALUE)
<br>

### Number.MIN_VALUE
- 在JS中可存的最小數字，console.log(Number.MIN_VALUE)
<br>

### .toString()
- 數字變字串，例如：2.toString() -> "2"
- 另一種方式：數字加空字串，例如：2+"" -> "2"
<br>

## Math 類型的內建函式
### Math.PI
- 圓周率
<br>

### Math.ceil(n)
- 無條件進位，例如：Math.ceil(10.1) -> 11
<br>

### Math.floor(n)
- 無條件捨去，例如：Math.floor(10.1) -> 10
<br>

### Math.round(n)
- 四捨五入，例如：Math.round(10.1), Math.round(10.5) -> 10, 11
<br>

### Math.sqrt(n)
- 開根號，例如：Math.sqrt(9) -> 3
<br>

### Math.pow(n, 幾次方)
- 次方，例如：Math.sqrt(2, 10) -> 1024
<br>

### Math.random()
- 產生一個隨機數，範圍0<=n<1，例如：Math.random() -> 0.5766180877640525
- 取1~10的隨機數，Math.floor(Math.random()*10 + 1)
<br>

## String 類型的內建函式
### .toLowerCase()
- 大寫轉小寫，例如："ABC".toLowerCase() -> abc
- 另一種方式：String.fromCharCode("A".charCodeAt(0)+32)
<br>

### .toUpperCase()
- 小寫轉大寫，例如："abc".toUpperCase() -> ABC
- 另一種方式：String.fromCharCode("a".charCodeAt(0)-32)
<br>

### .charCodeAt(字母位置)
- 得到ASCII CODE，例如："ABC".charCodeAt(0) -> 65 (A的ASCII CODE)，a -> 97
<br>

### String.fromCharCode(ASCII CODE)
- 由ASCII CODE取回字，例如：String.fromCharCode(65) -> A
<br>

### .indexOf()
- 在字串中找某字存不存在，若有，則回傳第一個字母的位置；若無，則回傳-1，例如："hey hello world".indexOf("hello") -> 4
<br>

### .replace("原字串", "新字串")
- 取代字串，例如："hey hello world".replace("hey", "!!!") -> !!! hello world
- 只會換第一個，例如："hey hello world".replace("h", "!") -> !ey hello world
- 正規表達式可以取代全部，例如："hey hello world".replace(/h/g, "!") -> !ey !ello world
<br>

### .split(切割方式)
- 將字切成陣列，例如：
```
"hey hello world".split(" ") -> ["hey", "hello", "world"]、"hey hello world".split("h") -> ["", "ey ", "ello world"]
```  
- 若沒有切割方式，則不切割塞進陣列中，例如："hey hello world".split() -> ["hey hello world"]
<br>

### .trim()
- 去除前後空格，例如：" hey hello world ".trim() -> hey hello world
<br>

### .length
- 字串長度，例如："abc".length -> 3
<br>

## Array 類型的內建函式
### .join(接合方式)
- 將陣列元素接成字串，例如：[1,2,3].join("!") -> 1!2!3
<br>

### .map(函式)
- 回傳值取代陣列元素，例如：
```
[1,2,3].map(function(x){
  return x*2
})
-> [2,4,6]
```
<br>

### .filter(函式)
- 刪除回傳false的陣列元素，例如：
```
[1,2,3,-1].filter(function(x){
  return x>0
})
-> [1,2,3]
```
<br>

### .slice(起始位置, 結束位置)
- 得到陣列的某部分，例如：[0,1,2,3,4,5,6].slice(3, 5) -> [3,4]
- 回傳一個新的陣列；結束位置可不填
<br>

### .splice(起始位置, 刪除數量, 新增元素)
- 刪除或新增陣列元素，例如：
```
var arr = [0,1,2,3]
arr.splice(0, 0, -1)
console.log(arr)
-> [-1,0,1,2,3]
```
- 原陣列；結束位置、新增元素可不填
<br>

### .sort(函式)
- 排序，例如：['a','c','d','b'].sort() -> ['a','b','c','d']
- 原陣列
- 數字排序有問題，例如：[1,30,4,21].sort() -> [1,21,30,4]
若要由小到大，要寫函式，例如：
```
[1,30,4,21].sort(function(a, b){
	if(a===b) return 0
	if(b>a) return -1  //-1代表不換位置
	return 1  //1代表換位置
})
[1,30,4,21].sort(function(a, b){
	return a-b
})
由大到小
[1,30,4,21].sort(function(a, b){
 if(a===b) return 0
 return a>b > -1 : 1
})
[1,30,4,21].sort(function(a, b){
	return b-a
})
```
