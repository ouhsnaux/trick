# require.context

批量导入。

## 全局注册组件

```js
import Vue from 'vue';

const requireComponents = require.context('.', true, /\.vue$/);
requireComponents.keys().forEach((key) => {
  const component = requireComponents(key).default;
  Vue.component(component.name, component);
});
```

## store 引入

```js
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

const files = require.context('./modules', false, /\.js$/);
export default new Vuex.Store({
  modules: files.keys().reduce((acc, cur) => {
    // 去除 './'前缀 和 '.js' 后缀
    acc[cur.slice(2, -3)] = files(cur).default;
    return acc;
  }, {}),
});
```
