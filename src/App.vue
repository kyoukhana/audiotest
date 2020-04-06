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
      
      var buzz = $buzz();
      $buzz.setup();
      
      $buzz.load('https://raw.githubusercontent.com/Tonejs/Tone.js/master/examples/audio/FWDL.mp3', function(evtData){
        console.log(evtData.url);
        console.log(evtData.percentageDownloaded);
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
