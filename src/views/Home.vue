<template>
  <div class="home">
    <img class="img" alt="Vue logo" src="../assets/logo.png" />
    <span>这是span1</span>
    <Button @click="btnClcik" class="btnstyle" buttonstyle="background-color:green">按钮</Button>
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
