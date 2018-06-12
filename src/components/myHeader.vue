<template>
  <div class="myHeader">
    <img src="../assets/logo.jpg"/>
  </div>
</template>

<script>
export default {
  name: 'myHeader',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.myHeader{
  height: 50px;
  width: 100%;
  background: #eee;
  img{
    height:50px;
    width: 50%;
    float: left;
  }
  p{
    font-size: 20px;
  }
 
}
</style>
