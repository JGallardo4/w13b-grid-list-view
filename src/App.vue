<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <tweet-container></tweet-container>
  </div>
</template>

<script>
import TweetContainer from './components/tweet-container.vue';

export default {
  name: "App",
  components: {
    TweetContainer
  },
};
</script>

<style>
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

#app {	
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
