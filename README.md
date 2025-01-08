[![npm](https://img.shields.io/npm/v/v3-clipboard)](https://img.shields.io/npm/v/v3-clipboard)


## Vue.js 3.x Clipboard Plugin

Thanks to [v-clipboard](https://github.com/euvl/v-clipboard) for inspiration!

If you want to support Vue 2.x, please use [v-clipboard](https://www.npmjs.com/package/v-clipboard) v2.x.

### Install

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

### Using

> When an element that contains `v-clipboard` directive is clicked, the value of `value` will be copied into clipboard.

Copying **static** value (directive should receive actual value):

```vue
<button v-clipboard="value">
  Copy to clipboard
</button>
```

Copying **dynamic** value (directive should recieve a function that returns value):

```vue
<button v-clipboard="() => value">
  Copy to clipboard
</button>
```

Copying **anything** in your methods:

```js
this.$clipboard(value)
```

### Events

```vue
<button v-clipboard="foo"
        v-clipboard:success="clipboardSuccessHandler" // Success event handler
        v-clipboard:error="clipboardErrorHandler">    // Error event handler
  Copy to clipboard
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

### Compatibility

[Document: execCommand() Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand#browser_compatibility)

<!-- <p align="center">
  <img src="https://user-images.githubusercontent.com/1577802/28269902-8ae0e01e-6afb-11e7-9981-d4965bac69d1.png">
</p> -->
