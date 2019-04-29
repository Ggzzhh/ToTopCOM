<template>
  <div id="toTopCOM">
    <div class="toTopButton" :class="[positionClass, color]" @click="toTop" :style="position">
      <div class="triangle-up triangle-bc-gray"></div>
      <div class="text">
        Top
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "ToTop",
    props: {
      duration: {
        type: Number,
        default: 500
      },
      position: {
        type: Object,
        default: {
          style: {}
        }
      },
      positionClass: {
        type: String,
        default: ''
      },
      color: {
        type: String,
        default: 'color-default'
      }
    },
    computed: {

    },
    methods: {
      toTop(){
        const pageY = document.documentElement.scrollTop
            || window.pageYOffset
            || document.body.scrollTop;
        const startTime = +new Date();
        const duration = this.duration;

        function run() {
          const time = +new Date() - startTime;
          window.scrollTo(0, pageY - pageY * (time / duration));

          run.timer = window.requestAnimationFrame(run);
          if (time >= duration){
            window.scrollTo(0, 0);
            window.cancelAnimationFrame(run.timer);
          }
        }

        window.requestAnimationFrame(run);
      }
    },
    data(){
      return {
      }
    }
  }
</script>

<style scoped>
  #toTopCOM {
    position: relative;
    width: 0;
    height: 0;
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

  .triangle-up{
    width: 0;
    height: 0;
    border-width: 0 .5rem .5rem;
    border-style: solid;
  }

  .triangle-bc-gray{
    border-color: transparent transparent #333;
  }

  .toTopButton {
    width: 2rem;
    height: 2rem;
    font-size: .8rem;
    font-weight: 600;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    padding: .5rem;
    cursor: pointer;
    border: 1px solid black;
    position: fixed;
    z-index: 2002;
    transition: .2s all;
  }

  .toTopButton:active {
    transform: scale(1.3);
  }

  .color-default{
    color: black;
    border-color: black;
    background-color: transparent;
  }

  .color-default:hover {
    background-color: aliceblue;
  }

  .color-red{
    color: #fbfbfb;
    border-color: #fbfbfb;
    background-color: #ff4b52;
  }

  .color-red > div {
    border-color: #fbfbfb transparent;
  }

  .color-red:hover {
    background-color: #fbfbfb;
    color: #ff4b52;
    border-color: #ff4b52;
  }

  .color-red:hover > div {
    border-color: #ff4b52 transparent;
  }

  .color-yellow{
    color: #232323;
    border-color: #232323;
    background-color: #ffe956;
  }

  .color-yellow > div {
    border-color: #232323 transparent;
  }

  .color-yellow:hover {
    background-color: #232323;
    color: #ffe956;
    border-color: #ffe956;
  }

  .color-yellow:hover > div {
    border-color: #ffe956 transparent;
  }

  .color-green{
    color: #232323;
    border-color: #232323;
    background-color: #61d65c;
  }

  .color-green > div {
    border-color: #232323 transparent;
  }

  .color-green:hover {
    background-color: #232323;
    color: #61d65c;
    border-color: #61d65c;
  }

  .color-green:hover > div {
    border-color: #61d65c transparent;
  }

  .color-blue{
    color: #fbfbfb;
    border-color: #fbfbfb;
    background-color: #63acdb;
  }

  .color-blue > div {
    border-color: #fbfbfb transparent;
  }

  .color-blue:hover {
    background-color: #fbfbfb;
    color: #63acdb;
    border-color: #63acdb;
  }

  .color-blue:hover > div {
    border-color: #63acdb transparent;
  }

  .TB-LB {
    top: unset;
    left: 1rem;
    right: unset;
    bottom: 1rem;
  }

  .TB-LT {
    top: 1rem;
    left: 1rem;
    right: unset;
    bottom: unset;
  }

  .TB-RT {
    top: 1rem;
    right: 1rem;
    left: unset;
    bottom: unset;
  }

  .TB-RB {
    top: unset;
    right: 1rem;
    left: unset;
    bottom: 1rem;
  }
</style>
