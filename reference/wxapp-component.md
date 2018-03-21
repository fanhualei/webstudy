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
    
* [高级篇](#高级篇)
    * [给组件添加属性](#给组件添加属性)
    * [给组件添加事件](#给组件添加事件)    
    
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
    
    
## 高级篇    

### 给组件添加属性

> 属性可以用来传值，见下面的代码

* wk-pk-line组件中的price等属性，都是自己定义的

```xml
<!-- 列表页面 -->
<view class='wk-search-content-wrapper ' >
  <block wx:for="{{pkList}}" wx:key="item" wx:for-index="idx">  
      <wk-pk-line  price='{{item.price}}' 
                         avatar='{{item.avatar}}'    
                         community='{{item.community}}' 
                         strDistance='{{item.strDistance}}' 
                         strAddress='{{item.strAddress}}' 
                         strTime='{{item.strTime}}' 
                         strLimit='{{item.strLimit}}' 
       />
  </block> 
</view>
```
<br>

> 怎么定义属性

* 在组件的js定义属性

````js
Component({

  options: {
    multipleSlots: true // 在组件定义时的选项中启用多slot支持
  },

  /**
   * 组件的属性列表
   * 用于组件自定义设置
   */

  properties: {
    //头像
    avatar: { // 属性名 
      type: String, // 类型（必填），目前接受的类型包括：String, Number, Boolean, Object, Array, null（表示任意类型） 
      value: 'https://s11.mogucdn.com/p2/170413/upload_86dkh4e886991g9lji7a6g5c530ji_400x400.jpg' // 属性初始值（可选），如果未指定则会根据类型选择一个
     },

    //小区名
    community: { 
      type: String, 
      value: '小区名称' 
    },

    //价格
    price: {
      type: Number,
      value: 0
    },

    //距离
    strDistance: {
      type: String,
      value: '0m'
    },

    //详细地址
    strAddress: {
      type: String,
      value: '详细地址'
    },

    //初祖时间
    strTime:{
      type:String,
      value:'可租时间**:**到**:**'
    },

    //限制条件
    strLimit: {
      type: String,
      value: '限制条件'
    }
  } 

})
````
<br>

* 在组件的wxml中使用属性

```xml
 <view class="wk-pk-list zan-panel zan-panel--without-margin-top">
  <view class='wk-pk-list-left' >
   <wxc-avatar class="avatar" src="{{avatar}}" /> 
  </view>
  <view class='wk-pk-list-right' >
      <view class='wk-pk-list-right-line0'>
        <view  class='wk-pk-list-right-line0-left  zan-ellipsis' >{{community}}</view>
        <view  class='wk-pk-list-right-line0-right zan-c-gray-dark ' >
          <text class='wk-font-color-main'>￥{{price}}</text>/月
        </view>

      </view>
      <view class='wk-pk-list-right-line zan-font-12 zan-c-gray-dark'>
        {{strDistance}}•{{strAddress}}
      </view>
      <view class='wk-pk-list-right-line zan-font-12 zan-c-gray-dark'>
       {{strTime}}•{{strLimit}}
      </view>
  </view>
</view> 
```

### 给组件添加事件







