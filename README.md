# vue-components-button

## 项目运行
```
yarn add
yarn serve
```

## 说明

`src / components / button / index.vue` 中定义 `Button` 组件：

```html
<template>
  <button class="container_button" @click="btnClick" :style="getStyle()">
    <slot></slot>
  </button>
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
  text-rendering: auto;
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  box-shadow: none;
  text-shadow: none;
  display: inline-block;
  text-align: center;
  align-items: flex-start;
  border: none;

  margin: 0em;
  font: 400 13.3333px Arial;
  padding: 1px 6px;
  border-width: 2px;
  border-radius: 10px;
  border-image: initial;
}
</style>
```

在 `home.vue` 页面中使用

```html
<template>
  <div class="home">
    <img class="img" alt="Vue logo" src="../assets/logo.png" />
    <h1>这是h1</h1>
    <span style="margin-right:20px">这是span1</span>
    <Button @click="btnClcik" class="btnstyle">按钮</Button>
    <span style="border:1px solid #000;margin-left:20px">这是span2</span>
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
  width: 200px;
  height: 200px;
  // background-image: url('../assets/logo.png');
  border: 1px solid #000;
  font-size: 20px;
}
</style>

```

### 样式

可以通过在 `home.vue` 中引入的 `Button` 组件添加 类名 来控制按钮的大小颜色等样式，也可以在 `Button` 总添加属性 `buttonstyle="background-color:green"` 来控制 `Button` 的样式

### 方法

可以通过在 `home.vue` 中引入的 `Button` 组件添加事件 `click` 来定义点击按钮之后触发的事件

