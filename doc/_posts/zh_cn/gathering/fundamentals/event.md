# 事件

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe


当你编写代码来制作动画，而不是直接使用动画素材时，你一定是想控制动画中地一些东西。非常幸运，mframe可以帮你控制动画中地每一帧。

在mframe中，你有两个地方可以设置事件。

```
var motion = mframe([{
  dom: document.getElementById('ball'),
  frames: [
    { css: { backgroundColor: '#279BE8' }, time: 0 },
    { css: { backgroundColor: '#E6F8FF' }, time: 120, tween:'easeInOut' },
  ],
  events: {
      0: ()=> {},
      'each': (index)=> {}
  }
}], events);
```

### mframe方法的第二个参数

+ start

    start事件在动画开始时触发。

+ end

    end事件在动画结束时触发。

+ each

    start事件每一帧都会触发，并且接受一个参数作为来获取当前的帧序数。

+ frame index

    你也可以传递自然数，指定一个某一帧触发的动画

### mframe方法的第一个参数数组中，每一个对象的events属性

+ each

    start事件每一帧都会触发，并且接受一个参数作为来获取当前的帧序数。帧序数相对当前对象，而不是整个动画对象

+ frame index

    你也可以传递自然数，指定一个某一帧触发的动画

