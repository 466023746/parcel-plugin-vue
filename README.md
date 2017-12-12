

# parcel-plugin-vue

> Stability: 1 - Experimental This feature is still under active development and subject to non-backwards compatible changes, or even removal, in any future version. Use of the feature is not recommended in production environments.

<img src="https://img.souche.com/f2e/b1f71b545619350ff92458bbcfa01056.png" align="right" width="140">

Make Parcel surports [Vue single file components](https://vuejs.org/v2/guide/single-file-components.html).

[【What's the Parcel】](https://parceljs.org/)[【What's the Vue】](https://vuejs.org/)

## Using Plugin

> Using plugins in Parcel could not be any simpler. All you need to do is install them and save in your package.json. Plugins should be named with the prefix parcel-plugin-, e.g. parcel-plugin-foo. Any dependencies listed in package.json with this prefix will be automatically loaded during initialization.

```
npm i parcel-plugin-vue -D
```

## Make some issues clear 

### This Plugin only support '*.vue'

When you meet this:

> [Vue warn]: You are using the runtime-only build of Vue where the template compiler is not available. Either pre-compile the templates into render functions, or use the compiler-included build.

Maybe in your code:

```
import Vue from 'vue';

new Vue({
  el: '#app',
  template: '...', // This is reason for Error 
  ...
})
```

You should change to:

```
import Vue from 'vue/dist/vue.esm.js';

new Vue({
  template: '...',
  ...
})
```

__or We recommend more__:

```
import Vue from 'vue';
import YourVue from 'YourVue.vue';

const app = new Vue(YourVue);

app.$mount('#app'); // Use '$mount' function take the place of 'el' property
```
