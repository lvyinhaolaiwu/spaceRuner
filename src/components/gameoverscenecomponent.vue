<template>
  <div id="gameover-scene" :class="{'scene in': show,'scene out':!show}">
    <p><a href="#" id="back-to-menu-button" class="button"
    @click="backToStartScene()"></a></p>
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
      show: false
    }
  },
  mounted () {
    Constant.Event.$on(Constant.MSG_SHOW_GAMEOVER_SCENE, function () {
      this.show = true
    }.bind(this))
  },
  methods: {
    backToStartScene () {
      console.log('back to start scene')
      this.show = false
      Constant.Event.$emit(Constant.MSG_SHOW_START_SCENE)
    }
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
  #gameover-scene{
    background: rgba(0,0,0,.5) url("../../static/images/gameover.png");
  }
</style>
