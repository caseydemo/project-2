<template>
  <div id="app">
    
    <!-- {{ selectedHouse }} -->
    <h2>Sorting Hat</h2>
    
    <!-- <div class="display">This is where the random value will go</div> -->
    <!-- <button class="houseName" v-on:click="this.getHouseName">click this button</button> -->

  <stats random=5></stats>

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
      random:0,
      selectedHouse: '',
      chicken: 'yolo',
      houseData: {
  
      'Houses': [

        {
          name: 'Gryffindor',
          description: ''
        },
        {
          name: 'Hufflepuff',
          description: ''
        },
        {
          name: 'Ravenclaw',
          description: ''
        },
        {
          name: 'Slytherin',
          description: ''
        }

      ],

      'Questions': [

        { 
          text: 'What is your favorite color?',
          answers: [
            {
              text: 'Scarlet',
              house: 'Gryffindor'
            },
            {
              text: 'Yellow',
              house: 'Hufflepuff'
            },
            {
              text: 'Blue',
              house: 'Ravenclaw'
            },
            {
              text: 'Green',
              house: 'Slytherin'
            }
          ]
        },
        { 
          text: 'What is your favorite animal?',
          answers: [
            {
              text: 'Lion',
              house: 'Gryffindor'
            },
            {
              text: 'Badger',
              house: 'Hufflepuff'
            },
            {
              text: 'Eagle',
              house: 'Ravenclaw'
            },
            {
              text: 'Snake',
              house: 'Slytherin'
            }
          ]
        },
        { 
          text: 'What kind of person do you try to be?',
          answers: [
            {
              text: 'Brave',
              house: 'Gryffindor'
            },
            {
              text: 'Loyal',
              house: 'Hufflepuff'
            },
            {
              text: 'Witty',
              house: 'Ravenclaw'
            },
            {
              text: 'Cunning',
              house: 'Slytherin'
            }
          ]
        },
        { 
          text: 'Who is your favorite witch or wizard?',
          answers: [
            {
              text: 'Albus Dumbledore',
              house: 'Gryffindor'
            },
            {
              text: 'Newt Scamander',
              house: 'Hufflepuff'
            },
            {
              text: 'Garrick Ollivander',
              house: 'Ravenclaw'
            },
            {
              text: 'Tom Riddle',
              house: 'Slytherin'
            }
          ]
        },
        { 
          text: 'What is your favorite Berty Bott\'s flavor?',
          answers: [
            {
              text: 'Grape',
              house: 'Gryffindor'
            },
            {
              text: 'Horseradish',
              house: 'Hufflepuff'
            },
            {
              text: 'Roast Beef',
              house: 'Ravenclaw'
            },
            {
              text: 'Spinach',
              house: 'Slytherin'
            }
          ]
        }

      ]

    }
    }
  },




  // COMPONENTS
  components: {
  'stats': stats
  },


  // BEFORE MOUNT
  // 



  // METHODS
  methods: {
   

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
