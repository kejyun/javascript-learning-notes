# 關閉瀏覽器或頁籤

## 說明

在使用者編輯文章時，可能會`不小心`關閉了瀏覽器頁籤、視窗或者點選了連結離開準備離開頁面，導致原本編輯的文章未發表出去就不見了，為了做防呆機制，我們可以在使用者編輯文章頁加入監控關閉頁籤的事件監控，讓使用者再次確認是否真的要離開畫面。

## 使用原生 JavaScript

```javascript
window.onbeforeunload = function () {
    return "你還沒有完成你的文章，就這樣離開了嗎？";
};
```

```javascript
window.addEventListener("beforeunload", function (e) {
  var confirmationMessage = "你還沒有完成你的文章，就這樣離開了嗎？";

  (e || window.event).returnValue = confirmationMessage; //Gecko + IE
  return confirmationMessage;                            //Webkit, Safari, Chrome
});
```

## 使用 jQuery

```javascript
$(window).on('beforeunload', function (e) {
    return '你還沒有完成你的文章，就這樣離開了嗎？';
});
```

## 參考資料
* [javascript detect browser close tab/close browser](http://stackoverflow.com/questions/3888902/javascript-detect-browser-close-tab-close-browser)
