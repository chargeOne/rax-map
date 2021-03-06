---
order: 1
title: 基本用法
---

要创建的一个图标，最简单的方式只要设置 Marker 组件的 `position` 属性就可以；高德地图中 Marker 的所有原生属性你都是可以配置的。

> [在线示例]演示内容:

> 1.创建四个简单 Marker ,只需要经纬度。

```jsx
import {Map,Marker} from 'rax-map';
import View from 'rax-view';
import {PureComponent, render} from 'rax';

class App extends PureComponent{
  constructor(){
    super();
    this.toolEvents = {
      created: (tool) => {
        this.tool = tool;
      }
    }
    this.mapPlugins = ['ToolBar'];
    this.mapCenter = {longitude: 115, latitude: 30};
    this.markerPosition = [
    {longitude: 115.01, latitude: 30.01},
    {longitude: 115.01, latitude: 29.09},
    {longitude: 114.09, latitude: 30.01},
    {longitude: 114.09, latitude: 29.09}
    ];
  }

  render(){
     return <View style={{width: '100%', height: '100%'}}>
              <Map plugins={this.mapPlugins}
                   center={this.mapCenter}
                   zoom={7}>
                   <Marker position={this.markerPosition[0]} />
                   <Marker position={this.markerPosition[1]} />
                   <Marker position={this.markerPosition[2]} />
                   <Marker position={this.markerPosition[3]} />
              </Map>
      </View>
  }
}

render(
  <App/>, mountNode
)
```
