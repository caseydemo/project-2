<!-- this component will hold all the data about the houses and assign a house to the child component "house" -->



<template>
  <!-- everything inside this div will be displayed in "stats" -->
  <div class="stats">

    <!-- welcome message -->
    <h1>Welcome to house {{ houseName }}, ya muggle!</h1>
     
     <!-- sorting hat picture -->
     <img id="hat-img" src='docs/sorting-hat.png'>

        <!-- for styling -->
        <div class="description-wrapper">

          <!-- inner styling box -->
          <div class="description-box">

            <!-- description of house -->
            <h3>a little info about {{ houseName }}, </h3>
            <p class="descrition">{{ houseDescription }}</p>
            
            <!-- dynamic image based on the house chosen -->
            <img v-bind:src="houseImage">
      </div>
    </div>
  </div>
</template>


<script>

	export default {
		stats : 'stats',

    // automatically called on page load
  beforeMount(){
    this.getRandomNum(),
    this.getHouseInfo()
  },
    	
      // METHODS
		methods: {

      // this creates a random number 
      getRandomNum: function(){
       this.randomNum = Math.floor((Math.random() * 4));
       this.random = this.randomNum;
      },
		
      // this pulls information out of the house data object
      getHouseInfo: function(){

        // console.log("this is the house info function");
        
        // pulls out the house name
        this.houseName = this.houseData['Houses'][this.randomNum]['name'];

        // pulls out the house description
        this.houseDescription = this.houseData['Houses'][this.randomNum]['description'];

        // pulls out the house image
        this.houseImage = this.houseData['Houses'][this.randomNum]['image'];
        // console.log("houseName: " + this.houseName);
        // console.log("houseDescription: " + this.houseDescription);
        // console.log("houseImage: " + this.houseImage);
        
      },

		},
		

    // DATA
		data () {
     return {
      
      houseName: '',  
      houseDescription: '',
      houseImage: '',
      randomNum: 0,
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
  border-style: solid;
  border-color: black;
  width: 800px;
  display: block;
  margin: auto;
  /*background-color:blue;*/
}
img{
  display: block;
  margin: auto;
  width:30%;
  padding-bottom: 50px;
}
#hat-img{
  width: 20%;
  height: auto;

}
.description-wrapper{
  padding: 50px;
  border-style: solid;
  border-color: red;
}
</style>