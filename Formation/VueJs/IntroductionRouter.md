# Vue Rooter

```shell
npm install vue-router --save
```

```json
"dependencies": {
    "vue": "^3.2.45",
    "vue-router": "^4.1.6"
}
```

```html
<router-link to="/">Go to Home</router-link>
<router-link to="/about">Go to About</router-link>
<rooter-view></router-view>

```

```javascript
import Home from './Home.vue';
import About from './About';

const router = new VueRouter({
    routes: [
        {component: Home, path: '/'},
        {component: About, path: '/about'},
    ]
})

import { createApp } from 'vue';

const app = createApp({})
app.use(router)
app.mount('#app')
```

