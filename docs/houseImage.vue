<template>

<div class="house">

<div class="wrapper">
 


</div>
  
</template>

<script>



	export default {
		name : 'houseImage',
    props : [ 'houseImage' ],
    data: function() {
      
      return{

      flip: false,
      house: 'house'
        }
      
    },
		
    
		methods: {

      getHouseImage: function(){

        this.houseImage = this.houseData['Houses'][this.randomNum]['image'];
        this.changeImage();
      },

      changeImage: function(){
        if(this.houseImage==='docs/Gryffendore.jpg'){
          // change to gryff picture
          this.houseImage="<img src='docs/Gryffendore.jpg'>";
        }
        else if(this.houseImage==='docs/hufflepuff.jpg'){
          // change to huffle picture
          this.houseImage="<img src='docs/Gryffendore.jpg'>";
        }
        else if(this.houseImage==='docs/ravenclaw.jpg'){
          // change to raven picture
          this.houseImage="<img src='docs/Gryffendore.jpg'>";
        }
        else if(this.houseImage==='docs/slytherin.jpg'){
          // change image to slytherin
          this.houseImage="<img src='docs/Gryffendore.jpg'>";
        }
        else{
          alert('this shouldn\'t ever happen');
        }
      },
			reportClickToParent: function(panelID){
				
				this.flip = !this.flip; // reverses the card's class
        this.$emit('cardFlipped', panelID); // this "emits" out the custom event "cardFlipped"
                                            // this triggers when a card is clicked
          },
          flipClass: function(){
            // this.flip=!this.flip;
          }    
			},  		
	};

</script>

<style scoped>

</style>