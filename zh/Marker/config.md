Map组件
====
config参数列表
-----

名称 | 类型 | 说明
---- | --- |---
position | Array | 点标记显示的位置[x,y]
offset | Object | 点标记显示位置偏移量{ x: -12, y: -12 }
animation | String | 点标记的动画效果 可选值:NONE,DROP,BOUNCE
title | String | 鼠标滑过点标记时的文字提示，不设置则鼠标滑过点标无文字提示
cursor | String | 指定鼠标悬停时的鼠标样式
zIndex | Number | 点标记的叠加顺序
clickable | Boolean | 点标记是否可点击, 默认为true
draggable | Boolean | 设置点标记是否可拖拽移动，默认为false
visible | Boolean | 点标记是否可见，默认为true