## 第四天学习笔记
### WeUI框架
1. WeUI 是微信官方设计团队设计的一套同微信原生视觉体验一致的基础样式库。[小程序设计指南](https://developers.weixin.qq.com/miniprogram/design/)
2. WeUI的使用
    * 新建 `style` 目录，并添加 `weui.wxss` 文件，在 `app.wxss` 文件中添加以下代码：
    ```
        @import 'style/weui.wxss';
    ```
3. Flex布局
    * 小程序的布局采用的是Flex布局。Flex是Flexible Box的缩写，意为”弹性布局”。
    * 在 `.wxml` 中布局文字，在 `.wxss` 选择格式。
    * 在父结构中加入 `display: flex` ，`flex:1` 各组件长宽之比为1。
    * 使用WeUI框架时需要把组件的选择器如class、id和WeUI框架的保持一致。
4. 使用WeUI美化文章排版
    * 使用已有的选择器，如需修改，可以命名两个 `id`，在对应页面下修改。
---
### 渐变与动画
1. CSS的渐变Gradient
    * CSS linear-gradient() 函数用于创建一个表示两种或多种颜色线性渐变的图片。
    ```
        .gradient-display{
            background: radial-gradient(#e66465, #9198e5);
            width: 100vw;
            height: 100vh;
        }
    ```
2. Filter滤镜
    * 对图片进行高斯模糊、调整对比度、转换为灰度图像、色相旋转、图片透明等操作。

3. 变形属性Transform、过渡属性Transition、动画属性Animation。
---
### 数据绑定
* 把 `WXML` 中的一些动态数据分离出来放到对应的js文件的 Page 的 data。
1. 数据类型：字符串String，数字Number，布尔值Boolean，对象Object，数组Array
    * 数字类型直接运算，字符串拼接
    * 复杂数据的嵌套，基本上使用 { }， 实现多个object并列。