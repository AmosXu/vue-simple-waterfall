# vue-simple-waterfall
### English | [中文](./chineseREADME.md)
I made some changes to resolve some problem and make it easily by vue-waterfall. vue-waterfall link is (https://www.npmjs.com/package/vue-waterfall)

# preview image
![preview](https://raw.githubusercontent.com/AmosXu/wx-custom-navigation/master/images/preview.png)
## Installation

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
## Props

### waterfall
| Name | Default | Description |
| :------| ------: | :------: |
| line-gap | - | Required. The standard space (px) between lines |
| item-width | - | Required. The width (px) of each item. |
| watch | [] | Watch something, reflow when it changes. |
| auto-resize | true | Reflow when window size changes. |


### waterfall-slot
| Name | Default | Description |
| :------| ------: | :------: |
| height | - | Required. The height of slot. |
| order | 0 | The order of slot, often be set to <code>index</code> in <code>v-for</code> . |
| key | <code>''</code> | The unique identification of slot, required for transition. |
