# 缓动

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

为了使动画更加顺滑，你可以传入缓动公式。

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

## 预设的缓动公式

+ linear

+ easeIn

+ easeOut

+ easeInOut

+ easeInCubic

+ easeOutCubic

+ easeInOutCubic

+ easeInQuart

+ easeOutQuart

+ easeInOutQuart

+ easeInQuint

+ easeOutQuint

+ easeInOutQuint

+ easeInSine

+ easeOutSine

+ easeInOutSine

+ easeInExpo

+ easeOutExpo

+ easeInOutExpo

+ easeInCirc

+ easeOutCirc

+ easeInOutCirc

+ easeInBounce

+ easeOutBounce

+ easeInOutBounce

## 获取缓动方法

```
/*
    * @param t {num} current time
    * @param b {num} beginning value
    * @param c {num} change in value
    * @param d {num} duration
*/
mframe.Tween.linear(t, b, c, d);
```

## 自定义缓动

```
mframe.Tween.add('yourTweenName', function(t, b, c, d) {
    return 0;
});
```