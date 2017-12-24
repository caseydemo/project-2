<template>
  <div class="stats">
    <!-- <img class="hat" src="docs/sorting-hat.png" alt="Card image cap"> -->
    <h1 class="house-title">Welcome to house {{ houseName }}</h1>
    <h6 class="house-subtitle"> ya muggle</h6>
    
    <div class="card" style="margin:auto; width: 75%;">
      
      <div class="card-body">
        <h4 class="card-title">{{ houseName }}</h4>
        <img class="house-img" v-bind:src="houseImage">
        <a v-on:click="descriptionBool()" class="btn btn-primary">Show Description</a>
      <a v-on:click="getRandomNum" class="btn btn-primary">try a new house</a>
        <p v-show="showDescription" class="card-text">{{ houseDescription }}</p>
      </div>
    </div>

    <div class="description-wrapper">
      <div class="description-box">
        
      </div>
    </div>
  </div>
</template>


<script>

	export default {
		stats : 'stats',


    // automatically called on page load
  beforeMount(){
    
      this.getRandomNum()
    
  },
    	
		methods: {

      getRandomNum: function(){
       this.randomNum = Math.floor((Math.random() * 4));
       this.random = this.randomNum;
       this.getHouseInfo();
      },
		
      getHouseInfo: function(){
        console.dir(this.houseData['Houses'][this.randomNum]['name']);
        this.houseName = this.houseData['Houses'][this.randomNum]['name'];
        this.houseDescription = this.houseData['Houses'][this.randomNum]['description'];
        this.houseImage = this.houseData['Houses'][this.randomNum]['image'];
        localStorage.setItem('houseName', this.houseName);
      },
      descriptionBool: function(){
        this.showDescription = !this.showDescription;
      },
		},
		

    // DATA
		data () {
     return {
      
      houseName: '',  
      houseDescription: '',
      houseImage: '',
      randomNum: 0,
      showDescription:false,
      houseData: {
  
      'Houses': [

        {
          name: 'Gryffindor',
          description: 'Gryffindor corresponds roughly to the element of fire, and it is for that reason that the colours scarlet and gold were chosen to represent the House[1]. The colour of fire corresponds to that of a lion as well, with scarlet representing the mane and tail and gold representing the coat.',
          image: 'docs/Gryffendore.jpg'
        },
        {
          name: 'Hufflepuff',
          description: 'Hufflepuff corresponds roughly to the element of earth,[3] and it is for that reason that the House colours were chosen: yellow represented wheat, while black was emblematic of soil.[4] The Hufflepuff points hourglass contains yellow diamonds.[5] Students sorted into Hufflepuff often demonstrate exceptional abilities in Herbology, owing to their correspondence to earth.',
          image: 'docs/hufflepuff.jpg'
        },
        {
          name: 'Ravenclaw',
          description: 'Ravenclaw House prizes learning, wisdom, wit, and intellect in its members.[4] Thus, many Ravenclaws tend to be academically motivated and talented students. Ravenclaws also pride themselves in being original in their ideas, and methods. It\'s not unusual to find Ravenclaw students practising especially different types of magic that other houses might shun. Hermione Granger, an extremely intelligent witch and the top student in her year, was sorted into Gryffindor, though she admitted that the Sorting Hat had seriously considered placing her in Ravenclaw.',
            image: 'docs/ravenclaw.jpg'
        },
        {
          name: 'Slytherin',
          description: 'Slytherin corresponds roughly with the element of water due to serpents being commonly associated with the sea and lochs in western European mythology, as well as serpents being physically fluid and flexible animals.[6] The colours also correspond with waters around lakes and lochs often being green, and silver being often associated with grey rain water.',
          image: 'docs/slytherin.jpg'
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
  /*border-style: solid;
  border-color: black;*/
  width: 800px;
  display: block;
  margin: auto;
  /*background-color:blue;*/
}

.house-img{
  display: block;
  margin: auto;
  max-width:600px;
  height: 400px;
  padding-top: 10px;
  padding-bottom: 10px;
}

.description-wrapper{
  padding-bottom: 50px;
  color:white;
  font-family: 'Nunito', sans-serif;
/*border-style: solid;
  border-color: black;*/
}
.btn{
  cursor: pointer;
}
.hat{
  display: inline-block;
  width: 25%;
  height: auto;
  margin:auto;
}
.house-title{
  display: inline-block;
}
.house-subtitle{
  display: inline-block;
}
</style>