# 载入动画

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

这篇文章会指导你如果构建一个载入动画。

## 一次控制多个dom

在立即开始文章中, 你已经学会为一个dom添加动画。你应该已经注意动mframe方法的第一个参数是一个数组，这就是我们如果构建多dom动画的关键。

#### HTML

```
<body>
  <div class='con' id='con'>
    <div id='ball' class='ball'></div>
  </div>
</body>
```

#### CSS

```
.con {
  top:200px;
  left:200px;
  position: absolute;
  width: 200px;
  height: 200px;
}
.ball {
  top:80px;
  left:0px;
  position: absolute;
  border-radius: 50%;
  background-color: #279BE8;
  width: 40px;
  height:40px;
}
```

#### JAVASCRIPT

```
var motion = mframe([{
  dom: document.getElementById('con'),
  frames: [
    { css: { transform: 'rotate(0deg)' }, time: 0 },
    { css: { transform: 'rotate(360deg)' }, time: 120, tween: 'easeInOut' },
  ]
},{
  dom: document.getElementById('ball'),
  frames: [
    { css: { transform: 'scale(0.4)', opacity: '0' }, time: 0 },
    { css: { opacity: '1.0' }, time: 40},
    { css: { transform: 'scale(1.5)', opacity: '1.0' }, tween: 'easeInOut', time: 100},
    { css: { opacity: '0' }, time: 120},
  ]
}]);
motion.repeat(Infinity);
```

[点击这里体验在线实例](https://codepen.io/arthusliang/details/mdJWoGe)

这个例子中，我们在改变小球的同时，旋转了它的容器。

### repeat

通过repeat方法你可以重复播放动画。

### dom

dom可以是一个对象或者一组对象。注意，使用null或者某个属性值时，如果dom是数组，mframe只返回第一元素的值。

## Make a spinner

让我们再加入更多的球来完善动画

#### HTML

```
<body>
  <div class='con' id='con1'>
    <div id='ball1' class='ball'></div>
  </div>
    <div class='con' id='con2'>
    <div id='ball2' class='ball'></div>
  </div>
    <div class='con' id='con3'>
    <div id='ball3' class='ball'></div>
  </div>
</body>
```

#### CSS

```
.con {
  top:200px;
  left:200px;
  position: absolute;
  width: 200px;
  height: 200px;
}
.ball {
  opacity: 0;
  top:0px;
  left:80px;
  position: absolute;
  border-radius: 50%;
  background-color: #279BE8;
  width: 40px;
  height:40px;
}
```

#### JAVASCRIPT

```
var createMotionObject = function(id) {
  let delay = (id-1)*12;
  return [{
    dom: document.getElementById('con'+id),
    frames: [
      { css: { transform: 'rotate(0deg)' }, time: delay },
      { css: { transform: 'rotate(360deg)' }, time: 120 + delay, tween: 'easeInOut' },
    ]
  },{
    dom: document.getElementById('ball'+id),
    frames: [
      { css: { transform: 'scale(0.4)', opacity: '0' }, time: delay },
      { css: { opacity: '1.0' }, time: 40 + delay },
      { css: { transform: 'scale(1)', opacity: '1.0' }, tween: 'easeInOut', time: 100+ delay},
      { css: { opacity: '0' }, time: 120 + delay},
    ]
  }];
};

var args = createMotionObject(1).concat(createMotionObject(2)).concat(createMotionObject(3));
var motion = mframe(args);

motion.repeat(Infinity);
```

[Click here to try this demo online](https://codepen.io/arthusliang/pen/poJeYXL)