# 如果用本地JSON模拟数据

> 目录
* [建立测试数据](#建立测试数据)
    * [1:建立test目录放测试文件](#1:建立test目录放测试文件)
    * [2:生成数据文件.js](#2:生成数据文件.js)
* [使用测试数据](#使用测试数据)
    * [1:在js文件初始化数据](#1:在js文件初始化数据)
    * [2:在wxml中得到数据](#2:在wxml中得到数据)

<br>

## 建立测试数据

## 1:建立test目录放测试文件

* test目录下，建立pklist-data.js文件，并编辑 

## 2:生成数据文件.js

```js
// 本地模拟数据
var localData = [
  {
    "pkID":1,
    "avatar": "http://www.weixincm.com/Uploads/20160820/57b7e9bf8c46a.jpg",
    "community": "太阳园小区",
    "price": 230,

    "strDistance": "100m",
    "strAddress": "北京市海淀区大钟寺东路168号",
    "strTime": "可租时间19:00到8:00",
    "strLimit": "节假日不租 尾号5限行不租"
  },

  {
    "pkID": 2,
    "avatar": "http://www.weixincm.com/Uploads/20160324/56f3baf290151.jpg",
    "community": "太阳园小区",
    "price": 320,

    "strDistance": "100m",
    "strAddress": "北京市海淀区大钟寺东路168号",
    "strTime": "可租时间8:00到16:00",
    "strLimit": "节假日不租"
  }
]

// 定义数据出口
module.exports = {
  pkList: localData
}  
```

## 使用测试数据

### 1:在js文件初始化数据

```js
var pklistData = require('../../test/pklist-data.js');  
Page({
  data: {  
  },
  onLoad: function (options) {
    this.setData({//获取数据成功后的数据绑定  
      pkList: pklistData.pkList
    });  
  }
})
```

### 2:在wxml中得到数据

* 使用wx:for便利测试数据

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








> 参考网址
* [本地json数据解析渲染到小程序列表 ](http://blog.csdn.net/qiushi_1990/article/details/77949918)
