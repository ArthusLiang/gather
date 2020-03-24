# Tween

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

In order to make the motion more smooth, we use easing formular. These formulars will be passed as tween.

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

## Preset Tween

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

## Access the tween

```
/*
    * @param t {num} current time
    * @param b {num} beginning value
    * @param c {num} change in value
    * @param d {num} duration
*/
mframe.Tween.linear(t, b, c, d);
```

## Add your own tween

```
mframe.Tween.add('yourTweenName', function(t, b, c, d) {
    return 0;
});
```