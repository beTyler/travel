<template>
  <div id="app">
    <button v-text="isShow ? 'show' : 'hide'" @click="isShow = !isShow"></button>
    <h1>{{ msg }}</h1>
    <transition tag="ul" name="fade">
      <img src="./assets/logo.png" v-show="isShow">
    </transition>
    <br/>
    <div class="youyouhuzhu" @click="events">游友互助</div>
    <div class="yiqiyou">一起游</div>
    <br/>
    <input type="text" @keyup="events($event)">
  </div>
</template>

<script>
  export default {
    name: 'app',
    data() {
      return {
        msg: '选择你想进入的版块',
        isShow: true
      }
    },
    methods: {
      events() {
      }
    }
  }
</script>

<style lang="scss" media="screen">
  $fontSize: 20px;
  .fade-enter {
    opacity: 0;
  }

  .fade-enter-active {
    transform: all 3s;
  }

  .fade-leave-acitive {
    opacity: 0;
    tranition: all 3s;
  }

  .youyouhuzhu, .yiqiyou {
    width: 100px;
    height: 100px;
    line-height: 100px;
    text-align: center;
    color: #fff;
    background: blueviolet;
    display: inline-block;
    font-size: $fontSize;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
  }
</style>
