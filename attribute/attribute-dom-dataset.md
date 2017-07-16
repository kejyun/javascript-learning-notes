# 取得 dom dataset

*DOM*

```html
<a href="#"
   data-field-id="field_1"
   data-type="type_1"
   id="link_id"
>Link</a>
```

## 使用原生 JavaScript 取得 data 屬性資料

```javascript
var link = document.getElementById('link_id'),
    field_id = link.dataset.fieldId,        // field_1
    type = link.getAttribute('data-type');  // type_1
```

## 使用 jQuery 取得 data 屬性資料狀況

JavaScript 的原生 dataset 資料與 jQuery 的 data 資料沒有互通

```javascript
// 取得資料
var field_id = $('#link_id').data('field-id'); // undefined

// 設定資料
$('#link_id').data('name', 'f2');
link = document.getElementById('link_id'),
var name = link.dataset.name;   // undefined
```

## 使用 jQuery 取得原生資料

```javascript
var field_id = $('#link_id').attr('data-field-id');     // field_1
```

## 參考資料
* [javascript - dataset vs .data - Difference? - Stack Overflow](https://stackoverflow.com/questions/23596751/dataset-vs-data-difference)
