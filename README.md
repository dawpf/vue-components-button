# vue-components-button

## 项目运行
```
yarn install
yarn serve
```

## 说明

`src / components / button / index.vue` 中定义 `Button` 组件：

```html
<template>
  <div class="container_button" @click="btnClick" :style="getStyle()">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    buttonstyle: {
      type: String,
      default: ''
    }
  },
  methods: {
    btnClick() {
      // 触发外部引入的按钮点击事件
      this.$emit('click')
    },
    getStyle() {
      // 返回自定义的样式
      // return 'background-color:red'
      return this.buttonstyle
    }
  }
}
</script>

<style lang="less" scoped>
.container_button {
  border-radius: 4px;
  background-color: pink;

  display: table-cell;
  vertical-align: middle;
  text-align: center;
}
</style>
```

在 `home.vue` 页面中使用

```html
<template>
  <div class="home">
    <img class="img" alt="Vue logo" src="../assets/logo.png" />
    <span>这是span</span>
    <Button @click="btnClcik" class="btnstyle">按钮</Button>
    <span style="border:1px solid #000">这是span1</span>
    <span style="border:1px solid #000">这是span2</span>
    <div style="border:1px solid #000">这是div</div>
  </div>
</template>

<script>
import Button from '@c/button/index.vue'
export default {
  name: 'Home',
  components: { Button },
  methods: {
    btnClcik() {
      console.log('父组件里面点击了按钮方法')
    }
  }
}
</script>


<style lang="less" scoped>
.img {
  display: block;
  margin: 0 auto;
}
.btnstyle {
  width: 100px;
  height: 100px;
}
</style>
```

### 样式

可以通过在 `home.vue` 中引入的 `Button` 组件添加 类名 来控制按钮的大小颜色等样式，也可以在 `Button` 总添加属性 `buttonstyle="background-color:green"` 来控制 `Button` 的样式

### 方法

可以通过在 `home.vue` 中引入的 `Button` 组件添加事件 `click` 来定义点击按钮之后触发的事件

### 问题

`Button` 组件属于块元素，使用时需注意按钮的位置

