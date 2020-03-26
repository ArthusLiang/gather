# 滚动条动画

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

很多情况下，我们需要建立滚动条动画。通过prop属性，我们可以轻松实现。

#### HTML

```
<body>
  <div class='con' id='con'>
    <div class='inner'></div>
  </div>
</body>
```

#### CSS

```
.con {
  position: absolute;
  width: 200px;
  height: 200px;
  overflow-y:scroll;
  overflow-x:hidden;
}
.inner {
  background: linear-gradient(#e66465, #9198e5);
  width:200px;
  height:800px;
}
```

#### JAVASCRIPT

```
var motion = mframe([{
  dom: document.getElementById('con'),
  frames: [
    { prop: { scrollTop: 0 }, time: 0 },
    { prop: { scrollTop: 600 }, time: 120, tween: 'easeOut' },
    { prop: { scrollTop: 0 }, time: 240, tween: 'easeIn' }
  ]
}]);
motion.repeat(Infinity);
```

[点击这里体验在线实例](https://codepen.io/arthusliang/pen/poJemaj)