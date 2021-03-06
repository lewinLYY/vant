## Tabbar

<script>
export default {
  data() {
    return {
      active: 0,
      active2: 0,
      icon: {
        normal: 'https://img.yzcdn.cn/public_files/2017/10/13/c547715be149dd3faa817e4a948b40c4.png',
        active: 'https://img.yzcdn.cn/public_files/2017/10/13/793c77793db8641c4c325b7f25bf130d.png'
      }
    }
  }
}
</script>

### Install
``` javascript
import { Tabbar, TabbarItem } from 'vant';

Vue.component(Tabbar.name, Tabbar);
Vue.component(TabbarItem.name, TabbarItem);
```

### Usage

#### Basic Usage

:::demo Basic Usage
```html
<van-tabbar v-model="active">
  <van-tabbar-item icon="shop">Tab</van-tabbar-item>
  <van-tabbar-item icon="chat" dot>Tab</van-tabbar-item>
  <van-tabbar-item icon="records">Tab</van-tabbar-item>
  <van-tabbar-item icon="gold-coin">Tab</van-tabbar-item>
</van-tabbar>
```

```javascript
export default {
  data() {
    return {
      active: 0
    }
  }
}
```
:::

#### Custom icon
Use `icon` slot to custom icon

:::demo Custom icon
```html
<van-tabbar v-model="active2">
  <van-tabbar-item icon="shop">
    <span>Custom</span>
    <img slot="icon" :src="active2 === 0 ? icon.active : icon.normal" />
  </van-tabbar-item>
  <van-tabbar-item icon="chat">Tab</van-tabbar-item>
  <van-tabbar-item icon="records">Tab</van-tabbar-item>
</van-tabbar>
```

```javascript
export default {
  data() {
    return {
      active2: 0,
      icon: {
        normal: '//img.yzcdn.cn/1.png',
        active: '//img.yzcdn.cn/2.png'
      }
    }
  }
}
```
:::

### Tabbar API

| Attribute | Description | Type | Default | Accepted Values |
|-----------|-----------|-----------|-------------|-------------|
| v-model | Index of current tab | `Number` | - | - |

### Tabbar Event

| Event | Description | Attribute |
|-----------|-----------|-----------|
| change | Triggered when change active tab | active: index of current tab |

### TabbarItem API

| Attribute | Description | Type | Default | Accepted Values |
|-----------|-----------|-----------|-------------|-------------|
| icon | Icon name | `String` | - | Names from Icon Component |
| dot | Whether to show red dot | `Boolean` | - | - |
