# Canvas

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

This article will teach you how to create canvas animation. You can also use these Api to play music!

#### HTML

```
<body>
  <canvas id='canvas' width='400' height='300' class='canvas'></canvas>
</body>
```

#### JAVASCRIPT

```
var canvas = document.getElementById('canvas'),
    ctx = canvas.getContext('2d');

var motion = mframe([{
  dom: ctx,
  frames:[
    { arg:{r1:60,r2:55, r3:50}, time:0},
    { arg:{r1:70,r2:62, r3:56}, time:40, tween:'easeIn'},
    { arg:{r1:60,r2:55, r3:50}, time:60, tween:'easeInOut'}
  ],
  events: {
    beforeEach: function() {
      ctx.clearRect(0,0,400,300);
    },
    each: function(i, args){
      ctx.beginPath();
      ctx.arc(200,150,args.r1,0,2*Math.PI);
      ctx.fillStyle='#e6f9fc';
      ctx.fill();
      ctx.closePath();
      ctx.beginPath();
      ctx.arc(200,150,args.r2,0,2*Math.PI);
      ctx.fillStyle='#73e3ff';
      ctx.fill();
      ctx.closePath();
      ctx.beginPath();
      ctx.arc(200,150,args.r3,0,2*Math.PI);
      ctx.fillStyle='#00a0d1';
      ctx.fill();
      ctx.closePath();
    }
  }
}]);

motion.repeat(Infinity);
```

[Click here to try this demo online](https://codepen.io/arthusliang/pen/wvajZJp)

### beforeEach

The function will be called before rendering css, attr and prop in each rendering.

### each

The function will be called after rendering css, attr and prop in each rendering.

### arg

You can pass and store arguments as that you do with css, attr and prop. The arg will not rendering the dom, it only help to generate the number, you can use it as the second argument in 'each' function.