# 立即开始

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

## Css 动画

让我们从一个简单的实例开始。通过以下代码，你会了解如何绘制简单的css动画

#### HTML

```
<body>
  <div id='ball' class='ball'></div>
</body>
```

#### CSS

```
.ball {
  position: absolute;
  border-radius: 50%;
  background-color: #279BE8;
  width: 50px;
  height: 50px;
  display:block;
}
```

#### JAVASCRIPT

```
var motion = mframe([{
  dom: document.getElementById('ball'),
  frames: [
    { css: { backgroundColor: '#279BE8' }, time: 0 },
    { css: { backgroundColor: '#E6F8FF' }, time: 120, tween:'easeInOut' },
  ]
}]);
motion.play();
```

[点击这里体验在线实例](https://codepen.io/arthusliang/pen/WNvpmoG)

## mframe

所有的动画都需要先构建mframe实例。你通过指定关键帧来创建动画，mframe会为你自动生成补间动画。


## 设置多个css属性

你可以同一设置css的多个属性。让我们保持css和html代码，修改以下javascript.

#### JAVASCRIPT

```
var motion = mframe([{
  dom: document.getElementById('ball'),
  frames: [
    { css: { backgroundColor: '#279BE8' , width: '20px', height: '20px'}, time: 0 },
    { css: { width: '50.0px', height: '50.0px'}, time: 60 },
    { css: { backgroundColor: '#E6F8FF' }, time: 120, tween:'easeInOut' },
  ]
}]);
motion.play();
```

[点击这里体验在线实例](https://codepen.io/arthusliang/pen/RwPpdpX)

## 帧规则

+ 如果你传入null为属性值，mframe会尝试获取该属性值。如果失败来，则忽略改属性。

+ 如果你设置来同一属性同一时间2次，后者有更高优先级。

+ 每一个属性都会在mframe中单独构建一个时间轴。如果你需要为同一时间中的不同属性设置不同的缓动公式，你可以通过两个关键帧对象实现。

+ 时间单位是帧，不是毫秒。

