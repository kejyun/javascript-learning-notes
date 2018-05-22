# 圖片 Lazy Loading (Intersection Observer)

## 使用 Intersection Observer 做圖片 Lazy Loading

### 安裝 IntersectionObserver polyfill 套件

Intersection Observer 是後來新版瀏覽器提供一個觀察元素狀態的功能，若想要支援舊版瀏覽器的話，可以下載套件

*下載套件*

```shell
npm install intersection-observer
```

*引用套件*

```html
<!-- Load the polyfill first. -->
<script src="path/to/intersection-observer.js"></script>

<!-- Load all other JavaScript. -->
<script src="app.js"></script>
```


### 設定圖片元素為 Lazyloading 元素

```html
<img class="js-lazy-image" src-image="burger.png">
```

## 觀察所有圖片元素

```javascript
var ObserveImages = document.querySelectorAll('.js-lazy-image');

var config = {
  // 如果圖片距離螢幕下緣，再 50px 就要瀏覽到了，開始下載圖片
  rootMargin: '50px 0px',
  // 圖片元素出現 (或消失) 0.01 % 觸發 observer
  threshold: 0.01
};

// 觀察圖片元素條件設定
var observer = new IntersectionObserver(onIntersection, config);

// 設定觀察的元素
lazyLoadingImg.each(function(key, image){
    observer.observe(image);
});
```


```javascript
// 當元素觸發 observe 時執行
function onIntersection(imagesEntries) {
    // 找尋每個圖片目前狀況
    imagesEntries.forEach(function(imageEntry){
        if (imageEntry.intersectionRatio > 0) {
            // 如果圖片現在是可視的狀態
            var $imageEntry = $(imageEntry.target);
            // 載入圖片
            $imageEntry.attr('src', $imageEntry.attr('src-image'));
            // 不再觀察此元素狀態
            observer.unobserve(imageEntry.target);
        }
    });
}
```

這樣就可以很快的完成圖片的 Lazy Loading 了～


## 參考資料
* [Intersection Observer API - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)
* [Intersection Observer API - Web API 接口 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Intersection_Observer_API)
* [IntersectionObserver/polyfill at master · w3c/IntersectionObserver](https://github.com/w3c/IntersectionObserver/tree/master/polyfill)
* [Lazy loading images using Intersection Observer](https://deanhume.com/lazy-loading-images-using-intersection-observer/)
* [How to lazy-load images to improve loading time and save bandwidth - José M. Pérez](https://jmperezperez.com/lazy-loading-images/)
* [Five Techniques to Lazy Load Images for Website Performance — SitePoint](https://www.sitepoint.com/five-techniques-lazy-load-images-website-performance/)
* [IntersectionObserver API 使用教程 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2016/11/intersectionobserver_api.html)
* [How to lazy-load images to improve loading time and save bandwidth - José M. Pérez](https://jmperezperez.com/lazy-loading-images/)
* [Lazy Loading Images and Video  |  Web Fundamentals  |  Google Developers](https://developers.google.com/web/fundamentals/performance/lazy-loading-guidance/images-and-video/)