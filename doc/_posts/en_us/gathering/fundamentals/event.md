# Event

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

When you code an animation install of playing a video, there must be something you want to control. In mframe, you can bind event to every frame you want.

There are 2 places which you can setup the events.

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

### The second argument of mframe

+ start

    The events will be emitted when the motion starts.

+ end

    The events will be emitted when the motion ends.

+ each

    The events will be emitted in every frame rendering. The function you passed will accepted the frame index as the first argument.

+ frame index

The events will be emitted when rendering the frame you defined.

### The attribution events of each item in the array.

+ each

The events will be emitted in every frame rendering. The function you passed will accepted the frame index as the first argument.

+ frame index

The events will be emitted when rendering the frame you defined.

