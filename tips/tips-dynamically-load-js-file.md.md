# 動態載入 js 檔案


```javascript
// 建立 js 元素
var script = document.createElement('script');
script.onload = function () {
    // 載入完成時執行的函式
    console.log('load js finish');
};
// 設定載入的 js 檔案
script.src = 'my/js/file.js';

// 將 script 元素加到頁面中（加進去後才會去載入 js 檔案）
document.head.appendChild(script);
```

## 參考資料
* [javascript - Dynamically load JS inside JS - Stack Overflow](https://stackoverflow.com/questions/14521108/dynamically-load-js-inside-js)
