# Svg path

[![license](https://img.shields.io/github/license/momentum-design/momentum-ui.svg?color=blueviolet)](https://github.com/momentum-design/momentum-ui/blob/master/charts/LICENSE)

> mframe

This article will teach you how to create the animation for drawing path in Svg.

#### HTML

```
<body>
  <svg width="151px" height="150px" viewBox="0 0 151 150" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <!-- Generator: Sketch 61.1 (89650) - https://sketch.com -->
    <g id="id1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <g transform="translate(-1.000000, 0.000000)" stroke="#000000">
            <path id="momentum-logo" stroke-width="1" stroke-dashoffset='600' stroke-dasharray='600 600' d="M102.61,48.45 L102.61,0 L1,0 L1,101.61 L49.39,101.61 L49.39,150.000302 L100.19,150.000302 C127.841771,150.094354 150.490145,128.054631 151.148921,100.410548 C151.807697,72.7664643 130.234876,49.6729232 102.61,48.45 Z M51.81,47.39 L9.26,4.84 L94.35,4.84 L51.81,47.39 Z M97.81,8.26 L97.81,48.39 L57.65,48.39 L97.81,8.26 Z M54.27,53.26 L97.81,53.26 L97.81,96.8 L54.23,96.8 L54.27,53.26 Z M5.84,96.77 L5.84,8.26 L49.39,51.81 L49.39,96.81 L5.84,96.77 Z M100.19,145.16 L54.19,145.16 L54.19,101.61 L102.57,101.61 L102.57,53.29 C127.084598,55.0711029 145.867946,75.809667 145.220715,100.38036 C144.573485,124.951053 124.724371,144.671978 100.15,145.16 L100.19,145.16 Z" id="形状"></path>
        </g>
    </g>
</svg>
</body>
```

#### JAVASCRIPT

```
var motion = mframe([{
  dom: document.getElementById('momentum-logo'),
  frames: [
    { attr: { 'stroke-dashoffset': '600' }, time: 0 },
    { attr: { 'stroke-dashoffset': '0' }, time: 120, tween: 'easeInOut' },
    { attr: { 'stroke-dashoffset': '0' }, time: 150 },
  ]
}]);
motion.repeat(Infinity);
```

[Click here to try this demo online](https://codepen.io/arthusliang/pen/GRJWadP)

### attr

The 'attr' enables you to set up the attribution of dom.

### stroke-dasharray & stroke-dashoffset
