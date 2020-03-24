# Key Frame

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

In animation tools as AE, Flash and soon on, designer fines the key frames and the sofeware will generate the rest of frames automatically. We do the same thing in mframe. 

### Arugments

The following code shows what you can define in mframe's frame.

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

    You can set the style of a dom by passing an object. If you pass null of one attribution, mframe will try to get this attribution's value automattically. The value of one attribution could also be a function.

+ attr

    Similar to css. The mframe will call setAttribute and getAttribute.

+ prop

    Similar to css. The mframe will call dom[attribution] directly.

+ time

    The default value is 0. To set the when to setup this key frame.

+ tween

    If there is a keyframe before this keyframe, the motion will use this easing formular to generator each frame.

## How mframe generator frames

    The key frames are passed in an array of one object. So you may meet the following questions.

## Passing two key frames with the same time

    Each attribution of css/attr/prop has its own timeline. So if want to set up 2 different tween at the same time. You can set two key frames with the same time number. The latter object has a higher priority.

## Generator rule

    The mframe will detect if it can generate frames between 2 key frames. If not, mframe will only setup the value when rendering key frames.

    All the number generated will be converted to int unless either of the input is a float number.

## Complie

    Every frames will be generated and stored in the cache before mframe runs the animation. If you setup null value, mframe will complie related frames just before running animation. Otherwise, mframe will generate frames when you create the object.