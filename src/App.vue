<template>
  <div id="app">
    {{ random }}
    <h2>Sorting Hat</h2>
    
    <div class="display">This is where the random value will go</div>

  <stats random=random></stats>

  </div>

</template>

<script>
import stats from './components/stats.vue' // imports the "stats" component



export default {
  name: 'app',




  // DATA
  data () {
    return {
      randomNum: 0,
      randomHouse: ''
    }
  },




  // COMPONENTS
  components: {
  'stats': stats
  },


  // BEFORE MOUNT
  beforeMount(){
    this.getRandomNum()
  },



  // METHODS
  methods: {
   getRandomNum: function(){
       this.randomNum = Math.floor((Math.random() * 4) + 1);
       // this.$emit('getRandom', this.random);
       // alert('random num: ' + this.random);
      return this.randomNum;
      }

  },


  // COMPUTED
  computed: {
    
    
    },
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
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
