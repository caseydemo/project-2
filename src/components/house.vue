<template>

<div class="house">

<div class="wrapper">


    
  
  </div>
</div>
  
</template>

<script>



	export default {
		name : 'house',
    props : [ 'houseID' ],
    data: function() {
      
      return{

      flip: false,
      house: 'house'
        }
      
    },
		
    // reportClickToParent : function( colorClicked ) {
    //         this.$emit( 'bulbClicked', colorClicked );

		methods: {
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