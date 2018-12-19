<template>
  <div class="container">
    <!--
    <img src="./assets/logo.png">
    <router-view/>
    -->

    <header>
      <div class="row">
        <h1>Space Runner!</h1>
      </div>
    </header>

    <section id="game" class="row">
      <start-scene class="scene"></start-scene>
      <game-over-scene class="scene"></game-over-scene>
    </section>
  </div>
</template>

<script>
import StartScene from './startscenecomponent'
import GameOverScene from './gameoverscenecomponent'
export default {
  components: {
    StartScene,
    GameOverScene
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
}
*/
  .container{
    margin:0;
    padding: 0;
    color: #2e3b3d;
    background:#a3d7df;
  }
  * {
    box-sizing: border-box;
  }
  p{
    margin:0;
    padding: 1em 0;
  }
  #game {
    width: 480px;
    height: 600px;
    margin: 0 auto;
    border-radius: 8px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .row {
    width: 480px;
    margin:0 auto;
  }
  .scene {
    background: #f9f9f9;
    width: 100%;
    height: 100%;
    position: absolute;
    overflow: hidden;
    border-radius:8px;
    -webkit-transition: all .3s ease-out;
  }
  .scene.out{
transform: translate3d(100%,0,0);
  }
  .scene.in{
    transform: translate3d(0,0,0);
  }
  .hidden {
    display: none;
  }
</style>
