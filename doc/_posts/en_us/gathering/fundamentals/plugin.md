# Plugin

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

The mframe enable you to develop plugins for the rendering engine and easing formular.

## Cpu

```
mframe.Cpu.install('yourOwnMode', {
    get: function(dom, key, val) {

    },
    set: function(dom, key) {

    }
});
```

+ You need set up get and set in your own cpu mode.

+ Dom could also be an array of doms.

+ The key could also be null and function.

## Tween

```
mframe.Tween.add('yourTweenName', function(t, b, c, d) {
    return 0;
});
```