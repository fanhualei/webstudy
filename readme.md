# html前端学习

> 目录

* [开发工具安装](#开发工具安装)
* [Flex布局](#flex布局)




## 开发工具安装

    建议使用webstorm这个工具很好用


## Flex布局

> 参考网址

* [Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
* [Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

### 基本语法

> 基本显示

    display:flex;
    
> 5个常用的元素

    * flex-direction:row | row-reverse | column | column-reverse ;   按照行还是列进行排序
    * flex-wrap: none | wrap | wrap-reverse ; 是否这行    
    * justify-content : flex-start | flex-end | center | space-between | space-around ; 主轴对齐的方法
    * align-item : flex-start | flex-end | center | baseline | stretch; 纵轴对齐方法 <br>
      （默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
    * align-content : flex-start | flex-end | center | space-between | space-around |stretch; 多轴对齐方法

> 6个子元素

    * order 顺序
    * item-grow 放大比例
    * item-shrink  缩小比例
    * flex-basis 不放缩
    * flex     flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选   
    * align-self：auto | flex-start | flex-end | center | baseline | stretch;                可覆盖align-items属性；
    
> 例子说明    

* [例子程序](flexbox/index.html)
* [例子说明](flexbox/readme.md)