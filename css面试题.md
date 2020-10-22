# css面试题

### 1：css3新特性

1.过渡 2.动画 3.形状装换 4.选择器 5.阴影 6.边框

7.背景 8.渐变 9.弹性布局（Flex） 10.盒模型定义（border-box,content-box） 11.媒体查询 ...

### 2：如何让两行文本对齐

### 3：如何让一个元素在另一个元素中水平垂直居中。

1.定位
2.弹性盒模型

### 4：rem和em的区别。如何用em做媒体查询。

rem和em都是一个相对单位

em相对于父元素的font-size的单位

rem相对于文档根元素HTML的font-size的单位

### 5：行内快怎么在盒子中垂直居中

1.定位
2.弹性盒模型
3.text-align: center; line-height: 父元素高度; vertical-align: middle

### 6：外边距塌陷。

塌陷只存在与相邻的垂直外边距，即只涉及到margin-top/bottom，水平（margin-left/rignt无）

解决方法：
1.border:1px solid transparent;
2.padding:1px;
3.float:left/right;
4.position:absolute;
5.display:inline-block;
6.overflow:hidden/auto;

### 7：弹性盒模型使用

display: flex

### 8：如何用样式写三角形

### 9：flex的容器和项目的样式有哪些

容器：6个
flex-direction （设置主轴方向）
justify-content （设置主轴上的子元素排列方式）
flex-wrap （设置是否换行）
align-item （设置侧轴上的子元素排列方式---单行）
align-content （多行）
flex-flow （复合属性）

项目：6个
align-self （控制子项自己在侧轴上的排列方法）
order: number （属性定义项目的排列顺序）
flex-grow: number （会得到一个额外的宽---父元素剩余的宽*grow的比列）
flex-shrink: number （当前方向的尺寸不能小于number的数值）
flex-basis: xxpx （设置项目在当前方向上的尺寸）
flex （复合属性）

### 10：定位有多少种

position: static （静态定位 默认）

position: sticky （粘性定位）

position: relative （相对定位）

position: absolute （绝对定位）

position: fixed （固定定位）

### 11：盒模型的相关样式

标准盒模型（box-sizing: content-box）
1.宽（width） 2.高（height） 3.内边距（padding） 4.边框（border） 5.外边距（margin）

怪异盒模型（box-sizing: border-box）