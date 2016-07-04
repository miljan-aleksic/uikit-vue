<p align="center">
  <a href="https://vuikit.github.io/vuikit/#!/alert">
    <img width="150" src="https://cdn.rawgit.com/vuikit/vuikit/master/static/logo-vuikit.svg">
  </a>
</p>

> UIkit with all the power of Vue

Vuikit is a collection of Vue components built on top of the awesome UIkit framework. While it is possible to use UIkit by its own when building Vue components, you may find yourself building a wrapper around it to fill the missing logic gap or to make it behave more naturally with Vue. Vuikit solves all that by providing a precise, documented API.

## Dependencies

- [Vue](http://vuejs.org/) (^1.0.24)
- [UIkit](http://getuikit.com/) (^2.26.0)
- [jQuery](https://jquery.com//) (Inherited UIkit dependency)

## Code Samples
> Note that all code examples are using ES6 syntax

Vuikit components are registered globally by default and ready to use immediately.

```js
import Vue from 'vue'
import Vuikit from 'vuikit'

Vue.use(Vuikit)
```
```html
<template>
  <div>
    <vk-button-checkbox>
      <vk-button color="primary">Button</vk-button>
      <vk-button active>Button</vk-button>
      <vk-button>Button</vk-button>
    </vk-button-checkbox>
  </div>
</template>
```

Although is possible to load and register them individually.

```js
import Vue from 'vue'
import { Button, Alert } from 'vuikit'

// globally
Vue.component('VkButton', Button)
Vue.component('VkAlert', Alert)

// or locally
new Vue({
  components: {
    VkButton: Button,
    VkAlert: Alert
  }
})
```

Changing the output or adding specific features is straightforward by extending a component.

```js
import Vue from 'vue'
import { Button } from 'vuikit'

Vue.component('TmButton', {
  extends: Button,
  template: '', // the new output
  props: {} // new features
  ...
})
```

## Configuration and Usage

### NPM

```bash
npm install vuikit --save
```
```js
import Vue from 'vue'
import Vuikit from 'vuikit'

Vue.use(Vuikit) // or register individually
```

By default all dependencies will be retrieved from `node_modules`, but that will not work straightforward as *UIkit* expects *jQuery* to be loaded globally. To avoid this and other related issues is recommended to solve the dependencies loading externally. When building with *Webpack* or *Browserify* you can do so by setting the `externals` or `external` config property.

### Browser

Make sure *jQuery*, *UIkit* and *Vue* are loaded upfront and then load `dist/vuikit.js`.

If you are using vue-cli generated project, please edit the file `build/webpack.base.conf.js` and add the following
block after the `vue:` property:

```
  plugins: [
    new webpack.ProvidePlugin({
      $: "jquery",
      jQuery: "jquery",
      "window.jQuery": "jquery"
    })
  ]
```

You will have to add the `var webpack = require('webpack');` at the top of the file.

## Documentation, Demo & Playground

We have setup a site with a live demo of each component listing its props, events and slots information. The props can be adjusted and the demo as the code example will update to reflect it. [Try it out!](http://vuikit.github.io/vuikit/).

Additionally there is a [codepen pen](http://codepen.io/miljan/pen/YWXVKj) for further testing.

## Developers

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for distribution
npm run build
```

## License

Vuikit is open source and released under the [MIT License](LICENSE.md).

Copyright (c) 2016 ZOOlanders.com
