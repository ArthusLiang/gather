# 动画对象

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

## 创建动画对象

你可以使用mframe方法直接创建动画对象。

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
## 方法

### add

add方法同动画对象的构造函数

#### 例

```
motion.add([{
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

### append

append方法同动画对象的构造函数。有所不同的是，append对象中第0帧会指向当前动画实例的最后一帧。相当于追加一段动画。

#### 例

```
motion.add([{
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

### bind

bind方法提供一种灵活绑定事件的实现。

```
motion.bind('start' , function() {});
```

### play

从当前帧开始播放动画

```
motion.play();
```

### stop

停止播放动画，并设置当前帧为第0帧

```
motion.stop();
```

### pause

停止播放动画

```
motion.pause();
```

### run

```
motion.start();
```

#### 参数

+ start frame - 默认0

+ end frame - 默认最后一帧

### reverse

倒叙播放动画

```
motion.reverse();
```

### repeat

重复播放指定次数动画

```
motion.repeat(1);
```