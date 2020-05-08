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