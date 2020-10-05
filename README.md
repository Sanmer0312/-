# 原生JS无缝轮播图

## HTML部分

最外层是一个固定宽度且带有`overflow: hidden;`属性的盒子

盒子内是两个列表，一个图片列表，一个point列表

图片列表里的图片是水平排列`float: left;`的

points-list里的point数量等于需要轮播的图片的数量

每次轮播时会根据此时播放的图片，给对应的point添加`class='active'`

可以根据需要给`active`添加样式


## JS部分

封装了一个轮播的方法，其基本原理是：

将图片列表里的图1克隆到最后一个图片后面，创建图1副本

将图片列表里的最后一个图片克隆到图1前面，创建最后一个图片的副本

每次播放到最后一张图片时，接着播放最后一张图片到图1副本的动画

播放完最后一张图片到图1副本的动画后，立即跳转到真正的图1位置，接着播放图1到图2的动画

每次鼠标移到图1对应的point时，判断上一个active的point是否为最后一张图对应的point

如果是，则跳转到图1副本位置，紧接着播放图1副本到最后一张图的动画

每次鼠标移到最后一张图对应的point时，判断上一个active的point是否为图1对应的point

如果是，则跳转到最后一张图副本位置，紧接着播放最后一张图副本到图1的动画

### 代码内有详细注释  

[在线预览](https://sanmer0312.github.io/JS-Swiper/index.html)，如果无法打开预览，原因是部分运营商DNS污染（域名指往不正确的IP地址），可以通过 修改hosts文件 / 修改DNS服务器 / 代理 的方式访问
