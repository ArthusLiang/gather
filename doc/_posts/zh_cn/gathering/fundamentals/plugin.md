# 插件

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

mframe允许开发人员创建自己的插件来强大它的功能。目前mframe接受渲染插件和缓动插件

## Cpu

```
mframe.Cpu.install('yourOwnMode', {
    get: function(dom, key, val) {

    },
    set: function(dom, key) {

    }
});
```

+ 你可以自定义渲染引擎，就像css/attr/prop
+ Dom可以是一个Dom对象或者一组Dom对象数组 
+ 值可以是方法或者null

## Tween

```
mframe.Tween.add('yourTweenName', function(t, b, c, d) {
    return 0;
});
```