## 第二天学习笔记
1. WXML文件
* WXML（WeiXin Markup Language）是框架设计的一套标签语言，结合基础组件、事件系统，可以构建出页面的结构。[WXML语法参考](https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/)
* 主要功能：
    - 数据绑定: 
    ```html
        <!--wxml-->
        <view> {{ message }} </view>
    ```
    ```html
        //page.js
        Page({
                data: {
                    message: 'Hello MINA!'
                }
            })
    ```
    - 列表渲染：
        * 在组件上使用 `wx:for` 控制属性绑定一个数组，即可使用数组中各项的数据重复渲染该组件。
        * 默认数组的当前项的下标变量名默认为 `index`，数组当前项的变量名默认为 `item`
    - 条件渲染：
        * 在框架中，使用 `wx:if=""` 来判断是否需要渲染该代码块; 也可以用 `wx:elif` 和 `wx:else` 来添加一个 else 块
    ```html
        <view wx:if="{{length > 5}}"> 1 </view>
        <view wx:elif="{{length > 2}}"> 2 </view>
        <view wx:else> 3 </view>
    ```
2. WXSS选择器
    * WXSS (WeiXin Style Sheets)是一套样式语言，用于描述 WXML 的组件样式。WXSS 用来决定 WXML 的组件应该怎么显示。[WXSS技术文档](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html)
    * 定义在 app.wxss 中的样式为全局样式，作用于每一个页面。在 page 的 wxss 文件中定义的样式为局部样式，只作用在对应的页面，并会覆盖 app.wxss 中相同的选择器。
    ```html
        .title{
            font-size: 20px; 
            font-weight: 600;
            text-align: center;
        }
    ```
    * 通过 `.title` 这个选择器，我们就选择到了类class为 `title` 的 `<view>`组件，然后就可以精准地对它进行美化，且对它的美化代码不会用在其他组件上了。
    * 注意： `id` 对应的是 `#wxmlinfo`， `class` 对应的是 `.title`
3. 盒模型
    * 盒模型类似于秀米中的边框，用来限制一部分内容的位置，与其他组件之间的间距，属性包括度、高度、也有边框，以及内边距与外边距。[CSS padding属性](https://www.w3school.com.cn/cssref/pr_padding.asp)
    ```html
        #wxmlinfo,#studyweapp{
            padding-top:20px;
            padding-right:15px;
            padding-bottom:20px;
            padding-left:15px;
        }
        <--调整标题与下方文字距离-->
        .title,.item-title{
            margin-bottom:0.9em;
        }
    ```
    * em是相对于当前字体尺寸而言的单位，如果当前你的字体大小为16px，那1em为16px
    