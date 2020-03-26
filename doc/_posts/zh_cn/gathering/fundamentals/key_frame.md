# 关键帧

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

在传统的动画制作工具中，设计师设计关键帧，然后AE,Flash等软件会自动完成补间动画。mframe也是如此。

### 参数

下列代码展示来如果定义一个关键帧。

```
{
    css: {},
    attr: {},
    prop: {},
    time: 0,
    tween: linear
}
```

+ css

    你可以通过css对象设置dom对象在这一帧的样式。如果你设置css对象的某个属性值为none，那么mframe会自动获取这个值。你也可以传递一个方法作为一个属性的值。

+ attr

    和css类似，attr会调用setAttribute和getAttribute方法。

+ prop

    和css类似，prop会使用.运算符号。直接读取或设置属性值。

+ time

    关键帧是第几帧，默认0

+ tween

    指定缓动公式

## mframe如何产生补间动画

    关键帧以参数形式传入mframe对象，mframe更具以为原则构建补间帧。

## 为同一时间传入两个对象

    每一个属性都会在mframe中单独构建一个时间轴。如果你需要为同一时间中的不同属性设置不同的缓动公式，你可以通过两个关键帧实现，后传入的对象有更高的优先级。

## 生成规则

    mframe会自动探测两个关键帧之间的同一属性能否生成动画，如果不能，mframe会在开始结束时分别设置值。

    所有的数字都默认返回整数补间值。如果你使用来浮点数来定义关键帧的属性值，那么生成的补间帧也会使用浮点数。

## Complie

    mframe会预编译每一帧，存在内存中。如果属性值是方法或者null,这一段补间动画会在动画立即执行期编辑，否则mframe在你传入参数的时候编译。