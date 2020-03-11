## 第三天学习笔记
1. navigator组件
* 通过navigator组件来给页面添加链接，链接到新的页面。 [navigator组件技术文档](https://developers.weixin.qq.com/miniprogram/dev/component/navigator.html)
* 通过点击链接进入的页面称作 二级页面，在链接所在的页面下新建新的页面。
```html
    <-app.json->
    "pages/home/imgshow/imgshow"

    <-home.wxml->
    <view class="index-link">
         <navigator url="./../home/imgshow/imgshow" class="item-link">让小程序显示图片</navigator>
    </view>
```
* navigator组件嵌套在view组件里，引用时使用 `class = "item-link"`
* 如果把路径写成 `/pages/home/imglist`，则链接的页面路径为`/pages/home/imglist.wxml`，会与 `home` 本身的文件混在一起，代码目录不整洁。
---
2. 相对路径与绝对路径
*  "./" 代表当前目录 `<img src="./img/icon.jpg" />` 等同于 `<img src="img/icon.jpg" />`
* “../” 代表上一级目录
* "/"   当前根目录，是相对目录；`<img src="/img/icon.jpg" />`
* `/pages/home/imgshow/imgshow` 和 `./../home/imgshow/imgshow` 表示内容相同，因为引用在 `home.wxml` 发生在 `home` 目录下，第一种说法是从根目录开始索引，第二种写法从当前目录返回上一级目录，再索引 `home` 目录，感觉是多次一举，尝试 `./imgshow/imgshow` 与 `imgshow/imgshow` 均可。
---
3. image组件
* 小程序添加图片是通过image组件的方式。 [image组件技术文档](https://developers.weixin.qq.com/miniprogram/dev/component/image.html)
* Tips：
    * image组件默认宽度300px、高度240px。
    * image组件中二维码/小程序码图片不支持长按识别, 仅在 `wx.previewImage` 中支持长按识别。
    