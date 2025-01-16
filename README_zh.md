[![npm](https://img.shields.io/npm/v/v3-clipboard)](https://img.shields.io/npm/v/v3-clipboard)


## Vue.js 3.x 剪切板插件

该插件灵感来源于 [v-clipboard](https://github.com/euvl/v-clipboard)，感谢。

如果你想要支持 Vue 2.x，请使用 [v-clipboard](https://www.npmjs.com/package/v-clipboard) v2.x 版本。

### 安装

```bash
npm install --save v3-clipboard
```

```javascript
import { createApp } from 'vue'
import Clipboard from 'v3-clipboard'

const app = createApp(App)
app.use(Clipboard)
app.mount('#app')
```

### 使用

> 当一个包含`v-clipboard`指令的元素被点击时，元素的 `value` 的值会被复制到剪切板。

复制 **静态** 值 (指令应该接受一个实际的值):

```vue
<button v-clipboard="value">复制到剪切板</button>
```

复制 **动态** 值 (指令应该接受一个带返回值的函数):

```vue
<button v-clipboard="() => value">复制到剪切板</button>
```

在你的方法里复制**任何东西**：

```js
this.$clipboard(value)
```

### 事件

```vue
<button v-clipboard="foo"
        v-clipboard:success="clipboardSuccessHandler" // 执行成功的回调函数
        v-clipboard:error="clipboardErrorHandler">    // 执行失败的回调函数
  复制到剪切板
</button>
```

```js
{
  methods: {
    clipboardSuccessHandler ({ value, event }) {
      console.log('success', value)
    },

    clipboardErrorHandler ({ value, event }) {
      console.log('error', value)
    }
  }
}
```

### 兼容性

[Document: execCommand() Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand#browser_compatibility)

<!-- <p align="center">
  <img src="https://user-images.githubusercontent.com/1577802/28269902-8ae0e01e-6afb-11e7-9981-d4965bac69d1.png">
</p> -->
