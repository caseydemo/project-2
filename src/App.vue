<template>
  <div id="app">
    <div class="wrapper">
  
  <stats></stats>

  </div>
</div>
</template>



<script>
import stats from './components/stats.vue' // imports the "stats" component
export default {
  name: 'app',
  components: {
  'stats': stats
  },
 }
</script>




<style>
#app {
  font-family: 'Nunito', sans-serif;
  font-size: 20px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1, h2 {
  color:white;
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
