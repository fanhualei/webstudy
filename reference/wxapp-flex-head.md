# 固定表头

> 目录

* [错误思路](#错误思路)
* [正确思路](#正确思路)
* [效果图](#效果图)


<br>

## 错误思路

* 用小程序scroll-view，是不行，无法计算scroll-view 高度

## 正确思路

* 使用 position: fixed; 将search框固定起来
* 在列表框加上个margin-top: 45px;把search框高度给让出来

> 代码示例

```css
/*浮动的搜索框*/
.wk-search-wrapper{
  position: fixed;/*悬停搜索框的关键样式*/  
  top: 0px;  
  left: 0px;  
  width: 100%;  
  z-index: 999; 
  background: #FFFFFF;
}

/* 列表框的样式 */
.wk-search-content-wrapper{
  margin-top: 45px;
}
```



## 效果图

要求头部的search不滚动

<img width="30%" height="30%" border="1" src="imgs/flex-head.jpg"/>

