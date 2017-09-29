# vue2-toast-styles
Toaster for Vue2 with styles
Based on: (https://github.com/lin-xin/vue-toast/blob/master/README_zh.md)

## screenshots
![image](https://raw.githubusercontent.com/AndresCL/vue-toast/master/screenshots/1.gif)

```$toast.center('This is a sample message...', 'success');```
![image](https://raw.githubusercontent.com/AndresCL/vue-toast/master/screenshots/success.png)

```$toast.center('This is a sample message...', 'info');```
![image](https://raw.githubusercontent.com/AndresCL/vue-toast/master/screenshots/info.png)

```$toast.center('This is a sample message...', 'warning');```
![image](https://raw.githubusercontent.com/AndresCL/vue-toast/master/screenshots/warning.png)

```$toast.center('This is a sample message...', 'error');```
![image](https://raw.githubusercontent.com/AndresCL/vue-toast/master/screenshots/error.png)

## Usage
Install:

```
npm install vue2-toast -S
```
Import:

```javascript
import 'vue2-toast/lib/toast.css';
import Toast from 'vue2-toast';
Vue.use(Toast);
```
or
```javascript
import 'vue2-toast/lib/toast.css';
import Toast from 'vue2-toast';
Vue.use(Toast, {
    defaultType: 'center',
    duration: 3000,
    wordWrap: true,
    width: '150px'
});
```

Use in component:

```javascript
<template>
    <div id="app">
        <button @click="openTop()">top</button>
        <button @click="openCenter()">center</button>
        <button @click="openBottom()">bottom</button>
		<button @click="openLoading()">loading</button>
    </div>
</template>
export default {
    methods:{
        openTop(){
            this.$toast.top('top', 'success');
        },
        openCenter(){
            this.$toast.center('center', 'info');
        },
        openCenter(){
            this.$toast('bottom', 'warning');  
        },
        openBottom(){
            this.$toast('bottom', 'danger');  
        },
        openLoading(){
            this.$loading('loading...');
			let self = this;
	        setTimeout(function () {
	          self.closeLoading()
	        }, 2000)
        },
        closeLoading(){
            this.$loading.close();
        }
    }
}
```
## work in Nuxt.js
config it in nuxt.config.js

```js
build: {
	vendor: ['vue2-toast'],
	extend (config, ctx) {
	  if (ctx.isClient) {
	    config.resolve.alias['vue'] = 'vue/dist/vue.js';
	  }
	}
}
```

## options

    Vue.use(Toast, [options])

- defaultType : position of Toast. | String | default: 'bottom' | possible 'top, center,bottom'
- duration : Number | default 2500ms
- wordWrap : word wrap. | Boolean | default: false
- width : width of Toast. | String | default: 'auto'

## source code
download in [Github](https://github.com/AndresCL/vue-toast-with-styles).