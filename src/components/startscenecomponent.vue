<template>
  <div id="game-scene" :class="{'scene in': show,'scene out':!show}">
    <p><a href="#" id="start-btn" class="button"></a></p>
    <!--
    <img src="./assets/logo.png">
    <router-view/>
    -->
  </div>
</template>

<script>
import Constant from './Constant'
export default {
  data () {
    return {
      show: true
    }
  },
  mounted () {
    console.log('start scene mounted')
    setTimeout(function () {
      console.log('time out')
      this.show = false
      Constant.Event.$emit(Constant.MSG_SHOW_GAMEOVER_SCENE)
    }.bind(this), 3000)

    Constant.Event.$on(Constant.MSG_SHOW_START_SCENE, function () {
      this.show = true
    }.bind(this))
  }

}
</script>

<style scoped>
  /*
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
  .button {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
  }
</style>
