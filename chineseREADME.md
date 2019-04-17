# vue-simple-waterfall

在vue-waterfall的基础上改了写代码，因为它有些问题导致无法使用，vue-waterfall link is (https://www.npmjs.com/package/vue-waterfall)

# 展示图片
![preview](https://image3.ichuanyi.cn/ai-admin/fd5dd159226dae46178baf23ca802aa9.png)
## 安装

  ```shell

npm install --save vue-simple-waterfall

```
### Import
#### ES6
```js
/* in xxx.vue */
import { Waterfall, WaterfallSlot } from  'vue-simple-waterfall'

export default {
...
components: {
  Waterfall,
  WaterfallSlot
},
...
}
```
### HTML structure

```html
<waterfall :line-gap="10" :item-width="160" :watch="imageList">
  <waterfall-slot
    v-for="(item, index) in  imageList" 
   :height="item.height  *  160  /  item.width"
   :order="index"
   :key="index"
  >
  <!--
    your component
  -->
  </waterfall-slot>
</waterfall>
```
## 组件参数

### waterfall
| Name | Default | Description |
| :------| ------: | :------: |
| line-gap | - | 必须，每项的间隔 |
| item-width | - | 必须，每项的宽度 |
| watch | [] | 检测对象变化时，发生重绘 |
| auto-resize | true | 窗口变化时，发生重绘 |


### waterfall-slot
| Name | Default | Description |
| :------| ------: | :------: |
| height | - | 必须. 当前项的高度 |
| order | 0 | 排序, 经常设置 <code>index</code> in <code>v-for</code> . |
| key | <code>''</code> | 唯一的key |
