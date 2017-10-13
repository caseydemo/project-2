<!-- this component will hold all the data about the houses and assign a house to the child component "house" -->



<template>

  <div class="stats">

    <h1>Welcome to house {{ houseName }}, ya dingus!</h1>
    
    <div class="description-box">
      <h3>a little info about {{ houseName }}, </h3>
      <p class="descrition">{{ houseDescription }}</p>
    </div>

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
    this.getHouseInfo()
  },
    	
		methods: {
      getRandomNum: function(){
        alert('it ran');
       this.randomNum = Math.floor((Math.random() * 4));
       this.random = this.randomNum;
      },
		
      getHouseInfo: function(){
        
        this.houseName = this.houseData['Houses'][this.randomNum]['name'];
        this.houseDescription = this.houseData['Houses'][this.randomNum]['description'];
        
      },
    
      // this is where the random number logic needs to go


		},
		
		data () {
    return {
      
      houseName: '',
      houseDescription: '',
      randomNum: 0,
      card2: '',
      houseData: {
  
      'Houses': [

        {
          name: 'Gryffindor',
          description: 'Robot moustache blacksmith bad guy hairy lipsum andrew weatherall id, robot moustache sterling hairy lipsum great dictator Fallen eyebrow blacksmith bad guy leader of men socially mobile musketeer funny walk id andrew weatherall.'
        },
        {
          name: 'Hufflepuff',
          description: 'Professor plum rugged big daft brush Leonine big daft brush bogie basket crumb catcher, professor plum sportacus nigel mansell Leonine cappuccino catcher big daft brush des lynam rugged charlie chaplin bogie basket movember big daft brush magnum pi crumb catcher.'
        },
        {
          name: 'Ravenclaw',
          description: 'Erudite headmaster middle eastern despot villain hulk hogan Droopy sam elliott, hulk hogan sam elliott middle eastern despot Droopy villain charlie chaplin dolor sit amet erudite headmaster cappuccino collector gunslinger derek griffiths.'
        },
        {
          name: 'Slytherin',
          description: 'Don’t panic hello, we’re cockneys groucho-a-like, mouth coiffure Droopy andrew weatherall don’t panic toothbrush doctor strange groucho-a-like dickie davies hello, we’re cockneys, andrew weatherall groucho-a-like mouth coiffure Droopy freestyle toothbrush hello, we’re cockneys don’t panic off-piste worn with distinction doctor strange dickie davies cappuccino collector.'
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

<style scoped>
.description-box{
  border-style: solid;
  border-color: red;
  width: 800px;
  display: block;
  margin: auto;
  /*background-color:blue;*/
}
</style>