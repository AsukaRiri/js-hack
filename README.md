# js-hack


```js
// iPad
if (window.devicePixelRatio >= 2) {
  $('head').append('<meta name="viewport" content="width=device-width, maximum-scale=1.0, user-scalable=no">');
} else {
  $('head').append('<meta name="viewport" content="width=640, maximum-scale=1.0, user-scalable=no">');
}
```

```js
if (window.addEventListener) {
  window.addEventListener('orientationchange', function(e) {
    viewportInit();
  });
} else {
  window.attachEvent('onorientationchange', function(e) {
    viewportInit();
  });
}
```
