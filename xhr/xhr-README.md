# XHR

```javascript
function reqListener () {
  console.log(this.responseText);
}

var oReq = new XMLHttpRequest();
oReq.addEventListener("load", reqListener);
oReq.open("GET", "http://www.example.org/example.txt");
oReq.send();
```

## 參考資料
* [使用 XMLHttpRequest - Web APIs | MDN](https://developer.mozilla.org/zh-TW/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)