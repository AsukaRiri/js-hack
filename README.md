# js-hack

###Detect Device Pixel Ratio
```js
if (window.devicePixelRatio >= 2) {
  $('head').append('<meta name="viewport" content="width=device-width, maximum-scale=1.0, user-scalable=no">');
} else {
  $('head').append('<meta name="viewport" content="width=640, maximum-scale=1.0, user-scalable=no">');
}
```

###Detect Device Orientation Change
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

###Read XML with mustache-like
```js
var tmpl = $('#tmpl').html();
var nodes = [ 'id', 'title' ];
var html = '';

var arr = [];
$(xml).find("event").each(function(i){
  arr[i] = {};
  var dump = tmpl;
  for (var j=0; j<nodes.length; j++) {
    if (!$(this).children(nodes[j]).text() || !$(this).children(nodes[j])) {
      // if node is null or empty
      var re = new RegExp('{{'+nodes[j]+'}}',"g");
      dump = dump.replace(re, '');
    } else {
      var val = $(this).children(nodes[j]).text().trim();
      promotions[i][nodes[j]] = val;
      var re = new RegExp('{{'+nodes[j]+'}}',"g");
      dump = dump.replace(re, val);
    }
  }
  html += dump;
});
console.log(arr);
console.log(html);
```

###JS Filter
```js
var result = $(directories).filter(function() {
  if (value == '') {
    return directories;
  } else {
    return this.key == value;
  }
}
```

###JS Sorting
```js
result.sort(function(a, b) {
  if (a.name.toLowerCase() < b.name.toLowerCase())
    return -1;
  if (a.name.toLowerCase() > b.name.toLowerCase())
    return 1;
  return 0;
});
```

###Google Map
```js
function initMap() {
  var zoom = 18;

  var image = 'pin.png';
  var map = new google.maps.Map(document.getElementById('map'), {
    zoom: zoom,
    center: {lat: 22.37110145, lng: 114.11800985},
    mapTypeId: google.maps.MapTypeId.ROADMAP,
    streetViewControl: false
  });
  var beachMarker = new google.maps.Marker({
    position: {lat: 22.3702281, lng: 114.1176214},
    map: map,
    icon: image
  });
  var beachMarker2 = new google.maps.Marker({
    position: {lat: 22.3715748, lng: 114.1183983},
    map: map,
    icon: image
  });
}
```

