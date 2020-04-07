<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
  
    <button v-on:click="play">Play</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import $buzz from 'musquito';

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  methods:{
    play: function (event) {
			// var buzz = $buzz('https://raw.githubusercontent.com/Tonejs/Tone.js/master/examples/audio/FWDL.mp3');
			// console.log(buzz);
      // buzz.play();
      
      const buzz = $buzz({
      url: 'https://raw.githubusercontent.com/Tonejs/Tone.js/master/examples/audio/FWDL.mp3',
      onloadprogress: function(percentage) {
         console.log(percentage);
      }
      });

    }
    

    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
