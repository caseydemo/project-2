<!-- this component will hold all the data about the houses and assign a house to the child component "house" -->



<template>

<div class="stats">


<!-- <button class="houseName" v-on:click="getHouseName">click this button</button> -->
  <!-- <house></house> -->

  
  {{ houseName }}

  <!-- {{ random }} -->
</div>
</template>

<script>
import house from './house.vue'


// v-on:bulbClicked="catchBulbCLick" />


	export default {
		stats : 'stats',
    // props : [ 'random' ],


    components : {
      house
    
  },
  beforeMount(){
    this.getRandomNum(),
    this.getHouseName()
  },
    	
		methods: {
      getRandomNum: function(){
        alert('it ran');
       this.randomNum = Math.floor((Math.random() * 4));
       this.random = this.randomNum;
      },
		
      getHouseName: function(){
        
        this.houseName = this.houseData['Houses'][this.randomNum]['name'];
        // console.log(this.houseName['Houses'][0]['name']);
        // console.log("random number is: " + this.random);
      },
    
      // this is where the random number logic needs to go


		},
		
		data () {
    return {
      
      houseName: '',
      randomNum: 0,
      card2: '',
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
  		}
	}

</script>

<style>

</style>