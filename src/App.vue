<template>
  <div id="app">
    <h1>测试用页面</h1>
    <to-top :position="pos"/>
    <to-top position-class="TB-LB" color="color-green"/>
    <to-top position-class="TB-RB" color="color-blue"/>
    <to-top position-class="TB-LT" color="color-red"/>
    <to-top position-class="TB-RT" color="color-yellow"/>
  </div>
</template>

<script>
  import ToTop from './components/ToTop.vue'
  export default {
    components: {
      ToTop
    },
    data(){
      return {
        pos: {
          bottom: '10rem',
          right: '10rem'
        }
      }
    }
  }
</script>

<style lang="stylus">
  html, body
    margin 0
    padding 0
  #app

    font-family 'Avenir', Helvetica, Arial, sans-serif
    -webkit-font-smoothing antialiased
    -moz-osx-font-smoothing grayscale
    min-height 200vh
    background-color  #9ed3ff
    margin 0
    padding 2rem
</style>
