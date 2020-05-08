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
