# Just Start

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

## Css animation

We will let you start with a very easy demo. In this demo, you will learn how to change dom's css.

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

[Click here to try this demo online](https://codepen.io/arthusliang/pen/WNvpmoG)

## mframe

All the operation in mframe starting with creating an instance of motion object. The most importthing you need to do is to set up key frame status in frames. Then our lib will generator the motion automatically.


## Set multiple css attribution

It is also easy to control multiple attribution at the some time. Let's keep us the Css and Html and just do some small updates in Javascript. 

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

[Click here to try this demo online](https://codepen.io/arthusliang/pen/RwPpdpX)

## frames rule

+ If you set up the value to null, mframe will try to get the value of this attribute automatically. If it fails, mframe will ignore this attribution.

+ If you set up one attribution more the twice at the same frame time, the later one will overwrite the one before.

+ Each attribution will create its own time line. If you have 2 attributions with different tween at a same time, you can setup 2 attributions independently.

+ The time unit is based on frame, not million seconds.

