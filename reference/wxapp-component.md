# 微信小程序组件说明

类似于页面，自定义组件拥有自己的 `wxml` 模版和 `wxss` 样式。

>目录
* [制作组件](#制作组件)
    * [编写JS文件](#[编写js文件])
    * [编写JSON文件](#[编写json文件])
    * [编写WXML文件](#[编写wxml文件])
    * [编写WXSS文件](#[编写WXSS文件])
    
* [使用组件](#使用组件)
    * [JSON中引用](#json中引用)
    * [WXSS中引用](#wxss中引用)
    
* 小技巧
    * [组建必须引用App.wxss](组建必须引用App.wxss)  


* 官方参考文档
    * [组件component](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/custom-component/)
    * [模版template](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/template.html)
    * [WXS脚本语言](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxs/)
    
    
## 制作组件

> 在建立一个目录，例如pk-line,下面生成微信用的4个文件

### 编写JS文件

> 必须要写代码，下面是一个空的

```js
Component({

})
```
### 编写JSON文件

> 必须要写，下面是一个最简单的

```json
{
  "component": true, 
  "usingComponents": {} 
}
```

### 编写WXML文件

> 必须要写

````xml
<view>这是一个模版</view>
````

### 编写WXSS文件

> 这个可以不写，但是在实际项目中，还是要写的

<br>


## 使用组件

### JSON中引用

> 可以引用一个或多个

```json
{
  "navigationBarTitleText": "求租车位"
,"usingComponents": {
  "wxc-avatar": "/vendor/minui/dist/wxc-avatar/dist/index"
  ,"wxc-price": "/vendor/minui/dist/wxc-price/dist/index"
  ,"wk-pk-line": "/vendor/wk-weapp/pk-line/pk-line"
  }
}
```

### WXSS中引用

> 按照定义的名称使用

```xml
<wk-pk-line/>
```
    