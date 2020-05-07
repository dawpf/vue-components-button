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