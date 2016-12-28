# 地图

## Marker组件

###### 点标记

```
import AMap from '../AMap';  //使用Amap
const Marker = AMap.Marker;  //Marker组件
<AMap id="id">
  <Marker></Marker>
</AMap>
```

## 组件静态属性

###### 仅且可以初始化配置，不支持响应式。

| 名称 | 类型 | 说明 |
| --- | --- | --- |
| [config](./config.md) | Object | 设置点标记对象的属性 |
| map | Map | 要显示该marker的地图对象,一般为外层AMap生成的地图实例,自动获取 |

## 事件\(待整理\)

## 示例代码

```
import React, { Component } from 'react';
import { provinces } from './consts';
import AMap from '../AMap';
const Marker = AMap.Marker;  //Marker组件

const renderMarker = (markers) => {
  let result = null;
  if (Array.isArray(markers) && markers.length > 0) {
    result = markers.map((marker, index) => <Marker key={index} options={marker} />);
  }
  return result;
};

export default class AMapView extends Component {
  constructor() {
    super();
    this.state = {
      markers: null,
    };
    this.getMap = this.getMap.bind(this);
  }

  getMap() {
    const markers = provinces.map(pro => ({
      position: pro.center.split(','),
      offset: { x: -12, y: -12 },
    }));
    this.setState({
      markers,
    });
  }

  render() {
    return (
      <div>
        <AMap>
          {renderMarker(this.state.markers)}
        </AMap>
        <button onClick={this.getMap}>点我</button>
      </div>
    );
  }
}
```



