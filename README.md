# Vuikit

> UIkit with all the power of Vue

Vuikit is a collection of native Vue components that embrace and extend the UIkit framework. While it is possible to use UIkit by its own when building Vue components, you may find yourself building a wrapper around it to fill the missing logic gap or to make it behave more naturally with Vue. Vuikit solves all that by providing a precise, documented API.

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
    VkAlert: Alert,
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

### Browser

Make sure UIkit and Vue latest version assets are loaded upfront and then load `dist/vuikit.css` and `dist/vuikit.js`.

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
npm run dist

# build docs
npm run docs
```

## License

Vuikit is open source and released under the [MIT License](LICENSE.md).

Copyright (c) 2016 ZOOlanders.com
