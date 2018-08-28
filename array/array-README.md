# 陣列 Array


## 去除(插入)陣列指定位置資料 splice

*參數*

1. index: 去除資料的陣列起始位置
2. how_many_item_to_remove: 去除的資料數量，如果設定為 0 則不會有資料被移除
3. add_item1, add_item2,... add_itemX：要加入的資料

> array.splice(index , how_many_item_to_remove, add_item1, add_item2)

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
```


## 參考資料
* [JavaScript Array splice() Method](https://www.w3schools.com/jsref/jsref_splice.asp)
