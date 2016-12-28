地图
====
Map组件
-----
#####地图组件，封装了地图的属性设置、事件交互等接口的组件,通过引用不同的地图组件,可使用相同的组件调用方法灵活使用谷歌,高德,百度,腾讯四种地图。
#####AMap标签的子节点,子节点均可获得该map对象,以map属性的方式传递给子组件
    import AMap from '../AMap';  //使用Amap
    <AMap id="id">
    </AMap>

组件静态属性
-----
######仅且可以初始化配置，不支持响应式。
名称 | 类型 | 说明
---- | --- |---
[loadConfig](./loadConfig.md) | Object | 地图加载时用到的key,版本号等
[mapConfig](./mapConfig.md) | Object | 初始化地图参数
style | Object | 地图元素的style
className | String | 地图容器节点的className
id | String | 地图容器节点的id

事件(待整理)
-----

示例代码
-----
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