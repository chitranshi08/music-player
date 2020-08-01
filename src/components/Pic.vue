<template>
	<div class="mainContainer">
		<div class="leftContainer">
			<img  @click="zoom(index)" v-for="(image ,index ) of images"  :key="index" :src="image"/>
			</div>
				<div class="rightContainer">
					
					<img class="largePic" :src="images[imageIndex]"  alt=""/>
					<div v-if="large">
					abc
				</div>
				</div>
		
	</div>
</template>

<script>

	export default{
		name:'Pic',
		data:()=>({
			
				images: ["Desert.jpg","Koala.jpg", "Lighthouse.jpg","JellyFish.jpg", "Tulips.jpg","Kalimba.mp3"],
			
			large:true,
			imageIndex:0
		}),
			methods:{
				zoom(i){
					this.imageIndex = i
				},
			}

		}
	
</script>
<style scoped>
img{
	width:100px;
	height:100px;
}
.mainContainer{
	display:flex;
	height:100vh;
	width:100vw;
}
.leftContainer{
	outline:1px solid black;
	width:240px;
}
.rightContainer{
	outline:1px solid black;
	width:calc(100% - 240px;);
}
.largePic{
	width:500px;
	height:500px;
}

	
</style>