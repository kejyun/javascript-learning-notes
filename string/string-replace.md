# 字串取代

## 取代第一個字

```javascript
var str = "Hello KeJyun! KeJyun Hi!";
// Hello KJ! KeJyun Hi!
var res = str.replace("KeJyun", "KJ");
```

## 取代全部的字

```javascript
var str = "Hello KeJyun! KeJyun Hi!";
// Hello KJ! KJ Hi!
var res = str.replace(new RegExp('KeJyun', 'g'), "KJ");
```


## 參考資料
* [JavaScript String replace() Method](https://www.w3schools.com/jsref/jsref_replace.asp)
* [regex - How to replace all occurrences of a string in JavaScript? - Stack Overflow](https://stackoverflow.com/questions/1144783/how-to-replace-all-occurrences-of-a-string-in-javascript)